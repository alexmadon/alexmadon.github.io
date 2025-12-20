
# two methods to convert from PDF to doc

```
libreoffice --invisible --convert-to docx:"MS Word 2007 XML" nombre.pdf
```


```
abiword --to=doc nombre.pdf
```


Note that pandoc cannot convert FROM PDF
