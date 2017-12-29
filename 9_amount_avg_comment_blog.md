```
Câu 9: Lấy số lượng comment trung bình trên mỗi blog (Update: Lấy số lượng comment trung bình của tất cả blog)

SELECT CEIL(AVG(total)) avg_total FROM (SELECT COUNT(*) total FROM comment WHERE target_table = 'blog' GROUP BY target_id) asd
```
