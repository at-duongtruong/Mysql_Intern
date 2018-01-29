```
(SELECT blog.id, 'blog' as type, blog.title, blog.content FROM blog
INNER JOIN(
	SELECT * FROM comment
	WHERE user_id = 1
	AND target_table = 'blog'
	ORDER BY RAND()
	LIMIT 2) as random2blog
ON blog.id = random2blog.target_id)
UNION ALL
(SELECT news.id, 'news' as type, news.title, news.content FROM news
INNER JOIN(
	SELECT * FROM comment
	WHERE user_id = 1
	AND target_table = 'news'
	ORDER BY RAND()
	LIMIT 2) as random2news
ON news.id = random2news.target_id)
```
