```
Câu 18 : Lấy số lượng Blog active của user có id là 1,2,4

select count(*) from blog inner join user on blog.user_id = user.id 
where (user.id in (1,2,4)) and (blog.is_active > 0)
```
