# ĐỀ 56 — PHÂN TRANG VÀ SẮP XẾP API TRONG EXPRESS

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const app = express();

const products = [
    { id: 1, name: "Laptop", price: 1200 },
    { id: 2, name: "Mouse", price: 20 }
];

app.get("/products", (req, res) => {
    const page = Number(req.query.page || 1);
    const limit = Number(req.query.limit || 10);
    const start = (page - 1) * limit;

    res.json(products.slice(start, start + limit));
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `req.query`, `page`, `limit`, `slice`, và phân trang.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- validate `page` và `limit` là số dương,
- thêm sort theo `price` tăng hoặc giảm,
- trả thêm `total`, `page`, `limit`, và `items`,
- giới hạn `limit` tối đa là 100.

## Phần C — Câu hỏi vấn đáp
1. Vì sao API danh sách cần phân trang?
2. Offset pagination có hạn chế gì?
3. Sort dữ liệu nên xử lý ở server hay client?
4. Vì sao cần giới hạn `limit` tối đa?

