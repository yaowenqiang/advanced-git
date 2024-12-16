The Value Blob

+ git store the compressed data in a blob, along with metadata in a header
+ the identifier blob
+ the size of the content
+ \0 delimiter (null string teminater in c)
+ content

> echo 'Hello ,World' | git hash-object --stdin

Generating the SHA1 of the content, with metadata:

> echo 'blob 14\0Hello ,World' | openssl shal


TREE 

+ tree contains pointers(using SHA1)
+ to blobs
+ to other trees

and meta data

+ type of pointers (blob or tree)
+ filename or directory name
+ mode(executable file, symboli link, ...)

Identical content is only stored once


Other optimizations - packfiles, deltas


+ Git objects are compressed
+ As files hange, their contens remain mostly similar,
+ Git optmizes for this by compressing these files together into a packfile
+ The Packfile stores the object, and 'deltas', or the differences between one version of the file and the next
+ Packfiles are generated when
  + You have too many objects, during gc, or during a push to a remote



