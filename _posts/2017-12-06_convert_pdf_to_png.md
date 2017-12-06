---
date: '2017-12-03T03:10:00.001-0700'
tags: linux 
---


# xubuntu Xenial 16.04 on HP ZBook 15 G4 (1RQ75ET#ABF)
{:.no_toc}

* TOC
{:toc}

## use of pdftoppm



You can use pdftoppm to convert a PDF to a PNG:

```bash
pdftoppm input.pdf outputname -png
```

This will output each page in the PDF using the format outputname-01.png, with 01 being the index of the page.
Converting a single page of the PDF

```bash
pdftoppm input.pdf outputname -png -f {page} -singlefile
```

Change {page} to the page number. It's indexed at 1, so -f 1 would be the first page.
Specifying the converted image's resolution

The default resolution for this command is 150 DPI. Increasing it will result in both a larger file size and more detail.

To increase the resolution of the converted PDF, add the options -rx {resolution} and -ry {resolution}. For example:

```bash
pdftoppm input.pdf outputname -png -rx 300 -ry 300
```

