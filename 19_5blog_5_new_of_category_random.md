```
Câu 19 : Lấy 5 blog và 5 news của 1 category bất kỳ
(select blog.category_id,blog.title,blog.view from blog
inner join
(select category.id from category order by rand() limit 1) as randomcategory
on blog.category_id = randomcategory.id
order by rand()
limit 5)
union all
(select news.category_id,news.title,news.view from news
inner join
(select category.id from category order by rand() limit 1) as randomcategory
on news.category_id = randomcategory.id
order by rand()
limit 5)


```
