```
Câu 10: Lấy Category có tồn tại blog hoặc news đã active (không được lặp lại category)

SELECT distinct(title) FROM category 
where (id in (SELECT blog.id FROM blog where is_active <> 0)) 
or (id in (SELECT news.id FROM news where is_active <> 0))

```
