```sql
create table export_table as
select id, name, city
from nyummy.cimory
where city = 'tokio'
```

```
$ pg_dump --table=export_table --data-only --column-inserts my_database > data.sql
```

[Source](https://stackoverflow.com/a/12816187/941257)
