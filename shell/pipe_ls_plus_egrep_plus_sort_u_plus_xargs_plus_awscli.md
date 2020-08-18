The files are something like 2020-08-17-10.tsv.gz (one for each hour).

```sh
ls *.tsv.gz | egrep -o '[0-9]{4}-[0-9]{2}-[0-9]{2}' | sort -u | xargs -n1 -I {} aws s3 cp . s3://<bucket>/<path-one>/<path-two>={}/ --exclude '*' --include '{}-*' --recursive
```

Explain the script above, list all files with tsv.gz extension, grep with regex to return only the date without the hour part from the filename, sort and unique (sort -u), after pipe into `aws s3` to put into the right folder.
