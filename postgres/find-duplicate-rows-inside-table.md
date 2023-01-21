```sql
select * from (
  SELECT id,
  ROW_NUMBER() OVER(PARTITION BY merchant_Id, url ORDER BY id asc) AS Row
  FROM Photos
) dups
where
dups.Row > 1
```

[Source](https://stackoverflow.com/a/14471928)
