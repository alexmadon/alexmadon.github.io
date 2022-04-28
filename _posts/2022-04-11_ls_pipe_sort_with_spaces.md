https://stackoverflow.com/questions/4583801/listing-files-in-date-order-with-spaces-in-filenames


OIFS=$IFS
IFS=$'\n'

ls -las -t $(cat list-of-files.txt) | head -10
IFS=$OIFS

random sort of list of files with spaces in filename:

```
~/bin/0sel `ls *4 | sort -r`
```
