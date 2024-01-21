# zarf archive format
by [Charles Iliya Krempeaux](http://changelog.ca/)

The **zarf format** is a very simple and easy to understand **archive format** and **container format** that can combine multiple files into a single aggregate file.

If you are _not_ familiar with **archive formats** and **container formats** — they have many use-case:
* backups,
* eBooks,
* file-systems,
* image galleries,
* journals,
* music albums,
* photo albums,
* software packages,
* website archives,
* _etc_.

Basically, any use-case where you need to combine multiple files into a single aggregate file.


The **zarf format** is similar to other **archive formats**, such as the  **ar format**, the **cpio format**, the **shar format**, the **tar format**, and the **WARC format** — but is designed to be easier to understand and implement than most (probably all) of the other **archive formats** and **container formats**.

In fact, one of the main points of the  **zarf format** existing, is that it was designed to be easy to understand and implement for programmers.
The **zarf format** is meant to be both programmer-legible and programmer-friendly.

## Sample

Here is an example **zarf** file with 3 files embedded in it.

```
ZARF/1

README.md
12
Hello world!

article.txt
1572
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Interdum velit laoreet id donec ultrices tincidunt arcu non sodales. Cras semper auctor neque vitae tempus quam pellentesque nec nam. Cursus turpis massa tincidunt dui ut. Diam vel quam elementum pulvinar etiam non quam. Gravida neque convallis a cras semper. Ornare massa eget egestas purus. Tempor id eu nisl nunc mi ipsum faucibus vitae aliquet. Fames ac turpis egestas maecenas pharetra. Arcu bibendum at varius vel pharetra vel turpis nunc. Integer quis auctor elit sed vulputate mi. Eget velit aliquet sagittis id consectetur purus ut faucibus. Sapien pellentesque habitant morbi tristique senectus.

Lorem mollis aliquam ut porttitor leo a diam sollicitudin tempor. Quis commodo odio aenean sed adipiscing. Commodo quis imperdiet massa tincidunt nunc. Quam quisque id diam vel quam elementum pulvinar etiam non. Elit ut aliquam purus sit amet luctus venenatis lectus. Sit amet mauris commodo quis. Placerat vestibulum lectus mauris ultrices eros in. Tristique sollicitudin nibh sit amet commodo nulla facilisi nullam vehicula. Augue interdum velit euismod in. Tellus pellentesque eu tincidunt tortor. Commodo viverra maecenas accumsan lacus vel facilisis. Venenatis a condimentum vitae sapien pellentesque habitant morbi. Et ligula ullamcorper malesuada proin libero nunc consequat interdum varius. Tellus integer feugiat scelerisque varius. Bibendum enim facilisis gravida neque convallis. Nisl nisi scelerisque eu ultrices vitae auctor eu.

images/logo.svg
1819
<svg width="512" height="512" viewBox="0 0 512 512" fill="none" xmlns="http://www.w3.org/2000/svg">
<path fill-rule="evenodd" clip-rule="evenodd" d="M175.394 91.7845L232.098 84.5849C259.535 81.1012 286.351 93.3871 301.711 115.881L278.501 121.263C254.24 126.889 237.063 148.515 237.063 173.433V179.987C237.063 204.42 253.591 225.755 277.238 231.848L304.335 238.829L302.58 256.702C299.132 291.83 326.715 322.273 361.992 322.273H394.259C419.619 322.273 441.619 302.514 434.989 283.157C442.141 292.886 446.063 304.703 446.063 316.918V324.433H435.466L426.867 352.433C414.687 392.098 374.274 415.933 333.667 407.403L291.049 398.45C279.438 396.011 267.68 401.907 262.691 412.671C255.052 429.148 233.12 432.573 220.821 419.21L88.7782 275.742C56.8167 241.015 57.1105 187.496 89.4511 153.122L121.182 119.396C135.499 104.178 154.666 94.4163 175.394 91.7845ZM406.977 249.724L412.346 241.577L338.408 186.901L350.873 173.753C354.233 170.208 356.678 165.897 357.997 161.194C358.795 158.346 359.058 155.478 358.849 152.695C356.653 157.774 351.916 161.358 346.358 162.037L319.725 165.29V154.395H274.298V195.25L319.725 207.878L366.145 249.724H406.977ZM166.564 243.076L175.628 243.076C180.01 243.076 183.563 239.524 183.563 235.142C183.563 230.76 187.115 227.207 191.497 227.207H197.254C204.816 227.207 210.946 233.337 210.946 240.899V251.49C210.946 264.901 200.074 275.773 186.663 275.773L160.214 275.773C145.106 275.773 132.198 264.881 129.656 249.988L121.321 201.152C119.327 189.472 124.167 177.676 133.79 170.762L134.477 170.269C143.116 164.061 154.334 162.717 164.195 166.708L180.397 173.265C185.637 175.385 189.066 180.472 189.066 186.124C189.066 193.786 182.855 199.997 175.193 199.997H169.316C158.408 199.997 149.566 208.839 149.566 219.747L149.566 226.078C149.566 235.465 157.176 243.076 166.564 243.076Z" fill="black"/>
</svg>


```

The files inside of this **zarf** file are named:

* `README.md`
* `article.txt`
* `images/logo.svg`

The **zarf** file also specifies the size of each of these embedded files.

| File Name         | File Size |
|-------------------|-----------|
| `README.md`       | 12        |
| `article.txt`     | 1572      |
| `images/logo.svg` | 1819      |

The content of the embedded file named `README.md` is only 12 bytes long, and is:

`Hello world!`

The content of the embedded file named `article.txt` is 1572 bytes long, and is:
```
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Interdum velit laoreet id donec ultrices tincidunt arcu non sodales. Cras semper auctor neque vitae tempus quam pellentesque nec nam. Cursus turpis massa tincidunt dui ut. Diam vel quam elementum pulvinar etiam non quam. Gravida neque convallis a cras semper. Ornare massa eget egestas purus. Tempor id eu nisl nunc mi ipsum faucibus vitae aliquet. Fames ac turpis egestas maecenas pharetra. Arcu bibendum at varius vel pharetra vel turpis nunc. Integer quis auctor elit sed vulputate mi. Eget velit aliquet sagittis id consectetur purus ut faucibus. Sapien pellentesque habitant morbi tristique senectus.

Lorem mollis aliquam ut porttitor leo a diam sollicitudin tempor. Quis commodo odio aenean sed adipiscing. Commodo quis imperdiet massa tincidunt nunc. Quam quisque id diam vel quam elementum pulvinar etiam non. Elit ut aliquam purus sit amet luctus venenatis lectus. Sit amet mauris commodo quis. Placerat vestibulum lectus mauris ultrices eros in. Tristique sollicitudin nibh sit amet commodo nulla facilisi nullam vehicula. Augue interdum velit euismod in. Tellus pellentesque eu tincidunt tortor. Commodo viverra maecenas accumsan lacus vel facilisis. Venenatis a condimentum vitae sapien pellentesque habitant morbi. Et ligula ullamcorper malesuada proin libero nunc consequat interdum varius. Tellus integer feugiat scelerisque varius. Bibendum enim facilisis gravida neque convallis. Nisl nisi scelerisque eu ultrices vitae auctor eu.
```

The content of the embedded file named `images/logo.svg` 1819 bytes long, and is:
```
<svg width="512" height="512" viewBox="0 0 512 512" fill="none" xmlns="http://www.w3.org/2000/svg">
<path fill-rule="evenodd" clip-rule="evenodd" d="M175.394 91.7845L232.098 84.5849C259.535 81.1012 286.351 93.3871 301.711 115.881L278.501 121.263C254.24 126.889 237.063 148.515 237.063 173.433V179.987C237.063 204.42 253.591 225.755 277.238 231.848L304.335 238.829L302.58 256.702C299.132 291.83 326.715 322.273 361.992 322.273H394.259C419.619 322.273 441.619 302.514 434.989 283.157C442.141 292.886 446.063 304.703 446.063 316.918V324.433H435.466L426.867 352.433C414.687 392.098 374.274 415.933 333.667 407.403L291.049 398.45C279.438 396.011 267.68 401.907 262.691 412.671C255.052 429.148 233.12 432.573 220.821 419.21L88.7782 275.742C56.8167 241.015 57.1105 187.496 89.4511 153.122L121.182 119.396C135.499 104.178 154.666 94.4163 175.394 91.7845ZM406.977 249.724L412.346 241.577L338.408 186.901L350.873 173.753C354.233 170.208 356.678 165.897 357.997 161.194C358.795 158.346 359.058 155.478 358.849 152.695C356.653 157.774 351.916 161.358 346.358 162.037L319.725 165.29V154.395H274.298V195.25L319.725 207.878L366.145 249.724H406.977ZM166.564 243.076L175.628 243.076C180.01 243.076 183.563 239.524 183.563 235.142C183.563 230.76 187.115 227.207 191.497 227.207H197.254C204.816 227.207 210.946 233.337 210.946 240.899V251.49C210.946 264.901 200.074 275.773 186.663 275.773L160.214 275.773C145.106 275.773 132.198 264.881 129.656 249.988L121.321 201.152C119.327 189.472 124.167 177.676 133.79 170.762L134.477 170.269C143.116 164.061 154.334 162.717 164.195 166.708L180.397 173.265C185.637 175.385 189.066 180.472 189.066 186.124C189.066 193.786 182.855 199.997 175.193 199.997H169.316C158.408 199.997 149.566 208.839 149.566 219.747L149.566 226.078C149.566 235.465 157.176 243.076 166.564 243.076Z" fill="black"/>
</svg>

```

## Motivation

There are many many use-cases where multiple files are combined into a single file.
For example:

* backups,
* eBooks,
* file-systems,
* image galleries,
* journals,
* music albums,
* photo albums,
* software packages,
* website archives,
* _etc_.

Many of these use-cases either use the **cpio format**, the **rar format**, **tar format**, or the **zip format**.

While all of these formats work acceptably as an **archive format** and a **container format** — none of them are **easy** for a programmer of 3 to 10 years of experience to implement a encoder and a decoder for it.
Also none of these supports a ‘**view-source**’ learning style (as none of them is text based, for some definition of "text").

That is why the **zarf format** exists.

The **zarf format** is a text-based format (in the same way HTTP/1.1 protocol is a text-based), so a programmer can look at **zarf** files (i.e., ‘**view-source**’) to understand it.

The **zarf format** is simple to create, thus making it easy to create an encoder.

The **zarf format** is simple to parse, thus making it easy to create a decoder.

## Extension

Although **zarf** does _not_ require an extension (since it has magic-bytes), if a file-extension is used for a **zarf** file, it should use the `.zarf` extension (on systems where file-extensions are necessary).
For example:

`stuff.zarf`

## MIME Type

Although **zarf** does _not_ require a MIME-type (since it has magic-bytes), if a MIME-type is used for a **zarf** file, it should use the `multipart/zarf` extension (on systems where file-extensions are necessary).
For example:

```
Content-Type: multipart/zarf
```

## Name

The name “**zarf**” has 2 meanings:

* it is a recursive acronym for “**Z**arf **AR**chive **F**ormat”, and
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

### Example

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

Now let's look at a **zarf** file that actually includes each file's contents (instead of `"..."`) so we can see a real example.
We are going to use a different directory structure for this example though.
We will use this one:

* README.md
* article.txt
* images/logo.svg

And here is the example **zarf** file that includes each of the file's contents (instead of `"..."`):

```
ZARF/1

README.md
12
Hello world!

article.txt
1572
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Interdum velit laoreet id donec ultrices tincidunt arcu non sodales. Cras semper auctor neque vitae tempus quam pellentesque nec nam. Cursus turpis massa tincidunt dui ut. Diam vel quam elementum pulvinar etiam non quam. Gravida neque convallis a cras semper. Ornare massa eget egestas purus. Tempor id eu nisl nunc mi ipsum faucibus vitae aliquet. Fames ac turpis egestas maecenas pharetra. Arcu bibendum at varius vel pharetra vel turpis nunc. Integer quis auctor elit sed vulputate mi. Eget velit aliquet sagittis id consectetur purus ut faucibus. Sapien pellentesque habitant morbi tristique senectus.

Lorem mollis aliquam ut porttitor leo a diam sollicitudin tempor. Quis commodo odio aenean sed adipiscing. Commodo quis imperdiet massa tincidunt nunc. Quam quisque id diam vel quam elementum pulvinar etiam non. Elit ut aliquam purus sit amet luctus venenatis lectus. Sit amet mauris commodo quis. Placerat vestibulum lectus mauris ultrices eros in. Tristique sollicitudin nibh sit amet commodo nulla facilisi nullam vehicula. Augue interdum velit euismod in. Tellus pellentesque eu tincidunt tortor. Commodo viverra maecenas accumsan lacus vel facilisis. Venenatis a condimentum vitae sapien pellentesque habitant morbi. Et ligula ullamcorper malesuada proin libero nunc consequat interdum varius. Tellus integer feugiat scelerisque varius. Bibendum enim facilisis gravida neque convallis. Nisl nisi scelerisque eu ultrices vitae auctor eu.

images/logo.svg
1819
<svg width="512" height="512" viewBox="0 0 512 512" fill="none" xmlns="http://www.w3.org/2000/svg">
<path fill-rule="evenodd" clip-rule="evenodd" d="M175.394 91.7845L232.098 84.5849C259.535 81.1012 286.351 93.3871 301.711 115.881L278.501 121.263C254.24 126.889 237.063 148.515 237.063 173.433V179.987C237.063 204.42 253.591 225.755 277.238 231.848L304.335 238.829L302.58 256.702C299.132 291.83 326.715 322.273 361.992 322.273H394.259C419.619 322.273 441.619 302.514 434.989 283.157C442.141 292.886 446.063 304.703 446.063 316.918V324.433H435.466L426.867 352.433C414.687 392.098 374.274 415.933 333.667 407.403L291.049 398.45C279.438 396.011 267.68 401.907 262.691 412.671C255.052 429.148 233.12 432.573 220.821 419.21L88.7782 275.742C56.8167 241.015 57.1105 187.496 89.4511 153.122L121.182 119.396C135.499 104.178 154.666 94.4163 175.394 91.7845ZM406.977 249.724L412.346 241.577L338.408 186.901L350.873 173.753C354.233 170.208 356.678 165.897 357.997 161.194C358.795 158.346 359.058 155.478 358.849 152.695C356.653 157.774 351.916 161.358 346.358 162.037L319.725 165.29V154.395H274.298V195.25L319.725 207.878L366.145 249.724H406.977ZM166.564 243.076L175.628 243.076C180.01 243.076 183.563 239.524 183.563 235.142C183.563 230.76 187.115 227.207 191.497 227.207H197.254C204.816 227.207 210.946 233.337 210.946 240.899V251.49C210.946 264.901 200.074 275.773 186.663 275.773L160.214 275.773C145.106 275.773 132.198 264.881 129.656 249.988L121.321 201.152C119.327 189.472 124.167 177.676 133.79 170.762L134.477 170.269C143.116 164.061 154.334 162.717 164.195 166.708L180.397 173.265C185.637 175.385 189.066 180.472 189.066 186.124C189.066 193.786 182.855 199.997 175.193 199.997H169.316C158.408 199.997 149.566 208.839 149.566 219.747L149.566 226.078C149.566 235.465 157.176 243.076 166.564 243.076Z" fill="black"/>
</svg>


```

It is a simple format.
You might even be able to figure out the format just by looking at this (and other) examples.

Now that we have a real example of a **zarf** file, let's look at the structure of it.

### Magic-Bytes

You can tell if a file is a **zarf** file or not just by looking at the first 5 bytes of at the beginning of the file.

For a file to be a **zarf** file is MUST begin with the byte bytes:

```go
"ZARF/"
```

I.e., in hexadecimal this would be:
```
0x5A 0x41 0x52 0x46 0x2F
```

### Version

What comes immediately after that is the version.

So with this first line of a **zarf** file:

```go
"ZARF/1"
```

What comes immediately after the `"ZARF/"` is"

```go
"1"
```

Or in hexadecimal this would be:
```
0x31
```

For now the only version of the **zarf format** is version 1.
So you should just look for the "1" character (i.e., hexadecimal `0x31`).

### Writing The First And Second Lines

If you are creating a **zarf** file, then you can create the first and second lines of a **zarf** file with code like the following —

In the Go programming language, it would look like:

```go
var writer io.Writer = os.Stdout // you can change this from os.Stdout to a file

// ...

fmt.Fprintln(writer, "ZARF/1")
fmt.Fprintln(writer)
```



