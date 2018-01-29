```
SELECT * FROM blog
WHERE user_id in (
SELECT to_user_id FROM follow
WHERE from_user_id = 1);
```
