```
Câu 17 : Select 10 blog mới nhất được tạo bởi các user active

select * from blog inner join user on blog.user_id = user.id
where blog.is_active <> 0 order by blog.id desc limit 10
```
