```
Câu 21 : Lấy blog được tạo trong 3 ngày gần nhất

select * from blog where (datediff(now(),blog.created_at) < 3)
```
