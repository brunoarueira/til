```sql
pg_dump -Fc -f pg.dump db_name
pg_restore -l pg.dump | grep -v 'COMMENT - EXTENSION' > pg_restore.list
pg_restore -L pg_restore.list pg.dump
```

[Source](https://stackoverflow.com/a/53166518/941257)
