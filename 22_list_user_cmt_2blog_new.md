```
Câu 22 : Lấy danh sách user đã comment trong 2 blog mới nhất
select user.id,user.fullname,user.email from comment inner join 
(select distinct(target_id) from comment
Where target_table = 'blog'
order by target_id desc
limit 2) as blog_2_new
on comment.target_id = blog_2_new.target_id 
inner join user on user.id = comment.user_id

```
