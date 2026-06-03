# ĐỀ 54 — FILTER BẰNG QUERY PARAMS TRONG EXPRESS

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const app = express();

app.get("/products", async (req, res) => {
    const keyword = req.query.q || "";
    const response = await fetch(`https://api.example.com/products?q=${keyword}`);
    const products = await response.json();

    res.json(products);
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `req.query`, query string, `q`, và việc filter dữ liệu.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- encode keyword trước khi đưa vào URL,
- thêm filter `category` và `page`,
- validate `page` là số dương,
- trả trạng thái không có kết quả khi danh sách rỗng.

## Phần C — Câu hỏi vấn đáp
1. Query params trong URL dùng để làm gì?
2. Vì sao cần `encodeURIComponent`?
3. Filter bằng URL có lợi ích gì cho UX?
4. Pagination nên xử lý ở client hay server?

