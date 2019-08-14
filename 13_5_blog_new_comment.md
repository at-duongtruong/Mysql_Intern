```
Câu 13: Lấy 5 blog mới nhất và số lượng comment cho từng blog

select count(comment.id),target_id from comment where target_table = 'blog' group by target_id order by target_id desc limit 5

```
