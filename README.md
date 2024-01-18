# zarf archive format
by [Charles Iliya Krempeaux](http://changelog.ca/)

The **zarf format** is an **archive format** and **container format** that can combine multiple files into a single aggregate file.

The **zarf format** is similar to other **archive formats**, such as the  **ar format**, the **cpio format**, the **shar format**, the **tar format**, and the **WARC format** — but is designed to be easier to understand and implement than all of the other **archive formats** and **container formats**.

In fact, one of the main points of the  **zarf format** existing, is that it was designed to be easy to understand and implement for programmers.

## Extension

Although **zarf** does _not_ require an extension (since it has magic-bytes), if a file-extension is used for a **zarf** file, it should use the `.zarf` extension (on systems where file-extensions are necessary).

## MIME Type

Although **zarf** does _not_ require a MIME-type (since it has magic-bytes), f a MIME-type is used for a **zarf** file, it should use the `multipart/zarf` extension (on systems where file-extensions are necessary).

## Name

The name “zarf” has 2 meanings:

* it is an acronym “**Z**arf **AR**chive **F**ormat”, and
* it also happens to be the Persian word for ‘container’.
