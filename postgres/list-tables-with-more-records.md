```sql
SELECT
  schemaname,
  relname,
  n_live_tup
FROM
  pg_stat_user_tables
ORDER BY n_live_tup DESC;
```

[Source](https://stackoverflow.com/a/2611745/941257)
