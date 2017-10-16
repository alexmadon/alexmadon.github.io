---
date: '2017-10-16T03:10:00.001-0700'
tags: linux print
---

You can use mutool (which comes as part of mupdf):

 mutool poster -x 2 input.pdf output.pdf

You can also use -y if you want to perform a vertical split.


 mutool poster -x 2 -y 2 CloudNativeLandscape_latest.pdf out.pdf
