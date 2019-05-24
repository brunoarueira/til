```sql
WITH RECURSIVE pops (id, level, name, name_path) AS (
    SELECT  id, 0, name, ARRAY[name]
    FROM    populations
    WHERE   parent_id is null

    UNION ALL

    SELECT  p.id, t0.level + 1, p.name, ARRAY_APPEND(t0.name_path, p.name)
    FROM    populations p
            INNER JOIN pops t0 ON t0.id = p.parent_id
)

SELECT  id, level, name_path[1] AS category, ARRAY_TO_STRING(name_path, ' > ')
FROM    pops
```

https://coderwall.com/p/fmdewq/postgresql-flatten-hierarchy-in-one-query
