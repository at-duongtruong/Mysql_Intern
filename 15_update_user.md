```
Câu 15: Update rank user = 2 khi tổng số lượng comment của user > 20

update user set rank = 2 where user.id in (select count(comment.comment) 
from comment group by user_id having (count(comment.comment)>20))
```
