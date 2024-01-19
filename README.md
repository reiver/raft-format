# zarf archive format
by [Charles Iliya Krempeaux](http://changelog.ca/)

The **zarf format** is an **archive format** and **container format** that can combine multiple files into a single aggregate file.

The **zarf format** is similar to other **archive formats**, such as the  **ar format**, the **cpio format**, the **shar format**, the **tar format**, and the **WARC format** — but is designed to be easier to understand and implement than all of the other **archive formats** and **container formats**.

In fact, one of the main points of the  **zarf format** existing, is that it was designed to be easy to understand and implement for programmers.
The **zarf format** is meant to be both programmer-legible and programmer-friendly.

## Extension

Although **zarf** does _not_ require an extension (since it has magic-bytes), if a file-extension is used for a **zarf** file, it should use the `.zarf` extension (on systems where file-extensions are necessary).
For example:

`stuff.zarf`

## MIME Type

Although **zarf** does _not_ require a MIME-type (since it has magic-bytes), f a MIME-type is used for a **zarf** file, it should use the `multipart/zarf` extension (on systems where file-extensions are necessary).
For example:

```
Content-Type: multipart/zarf
```

## Name

The name “zarf” has 2 meanings:

* it is an acronym “**Z**arf **AR**chive **F**ormat”, and
* it also happens to be a Persian word for ‘container’.

## File Format

A **zarf** file is a single file that contain multiple other files.

Or said more formally, the **zarf format** is an **archive format** and **container format** that can combine multiple files into a single aggregate file.

One of the main points of the  **zarf format** is that it was designed to be easy to understand and implement for programmers.
The **zarf format** is meant to be both programmer-legible and programmer-friendly.

The common way to store and think about **multiple files** is as part of a directory system.
For example:

* readme.xhtml
* LICENSE
* images/logo.png
* images/banner.png
* images/figures/figure1.jpeg
* images/figures/figure2.jpeg
* images/figures/figure3.png

This type of thing (and the files' contents) is what is inside of a **zarf** file.

One way of thinking about this is that, it is a **hierarchical key-value format** similar to (**but not the same as**) JSON, INI, and other similar formats.

For example, in JSON the preceding file system would probably look like:

```json
{
	"readme.xhtml": "...",
	"LICENSE": "...",
	"images": {
		"logo.png": "...",
		"banner.png": "...",
		"figures": {
			"figure1.jpeg": "...",
			"figure2.jpeg": "...",
			"figure3.png": "..."
		}
	}
}
```

(Note that we are using `"..."` in the examples because we aren't listing the contents of the files.)

Also for example, in INI the preceding file system would look like:
```ini
readme.xhtml = ...

LICENSE = ...

[images]

logo.png = ...

banner.png = ...

[images.figures]

figure1.jpeg = ...

figure2.jpeg = ...

figure3.png = ...
```

(Again note that we are using `"..."` in the examples because we aren't listing the contents of the files.)

The same as a **zarf** file would be:

```
ZARF/1

readme.xhtml
14
...

LICENSE
1053
...

images/logo.png
17365
...

images/banner.png
5550
...

images/figures/figure1.jpeg
132441
...

images/figures/figure2.jpeg
814532
...

images/figures/figure3.png
28389
...
```

(And again note that we are using `"..."` in the examples because we aren't listing the contents of the files.)


