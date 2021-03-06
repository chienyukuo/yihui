---
title: qpdf()
subtitle: "A wrapper for the PDF toolkit qpdf"
date: '2017-04-04'
slug: qpdf
from_Rmd: yes
---


If the tool qpdf is available in the system, it will be called to manipulate
the PDF files (especially to compress the PDF files).

This is a wrapper to call `qpdf`. The path of `qpdf` should
be set via `ani.options(qpdf = 'path/to/qpdf')`.

See the reference for detailed usage of `qpdf`.
 

```r
library(animation)
pdf("huge-plot.pdf")
plot(rnorm(50000))
dev.off()

## Windows
ani.options(qpdf = "D:/Installer/qpdf/bin/qpdf.exe")
qpdf("huge-plot.pdf", output = "huge-plot0.pdf")

## Linux
ani.options(qpdf = "qpdf")
qpdf("huge-plot.pdf", output = "huge-plot1.pdf")

ani.options(qpdf = NULL)

file.info(c("huge-plot.pdf", "huge-plot0.pdf", "huge-plot1.pdf"))["size"]
```
