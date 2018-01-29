```
(SELECT id, 'blog' as type, title, content FROM blog
WHERE is_active > 0
ORDER BY id DESC
LIMIT 5
)
UNION
(SELECT id, 'news' as type, title, content FROM news
WHERE is_active > 0
ORDER BY id DESC
LIMIT 5
);
```
