```
Câu 12: Lấy blog được tạo bởi user mà user này không có bất kỳ comment ở blog

select * from blog inner join user on blog.user_id = user.id
left join comment on user.id = comment.user_id where comment.user_id is null
```
