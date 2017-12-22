```
Câu 20 : Lấy blog và news có lượt view nhiều nhất

select blog.category_id,blog.title,blog.is_active from blog inner join 
(select max(blog.view) as max_view from blog) as maxviews
on blog.view = maxviews.max_view
union all
select news.category_id,news.title,news.is_active from news inner join 
(select max(news.view) as max_view from news) as maxviews
on news.view = maxviews.max_view
```
