```
(SELECT target_id as id, 'blog' as type, count(target_id) as count FROM comment
WHERE target_table = 'blog'
GROUP BY target_id
ORDER BY count DESC
LIMIT 1
)
UNION
(SELECT target_id as id, 'news' as type, count(target_id) as count FROM comment
WHERE target_table = 'news'
GROUP BY target_id
ORDER BY count DESC
LIMIT 1
);
```
