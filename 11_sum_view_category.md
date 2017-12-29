```
Câu 11: Lấy tổng lượt view của từng category thông qua blog và news

select sum(total) total_view from(
select sum(view) total,blog.category_id from blog group by category_id 
union 
select sum(view),news.category_id from news group by category_id) ddd group by category_id
```
