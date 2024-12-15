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



