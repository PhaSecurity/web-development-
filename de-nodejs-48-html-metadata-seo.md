# ĐỀ 48 — METADATA VÀ SEO KHI RENDER HTML BẰNG EXPRESS

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const app = express();

app.get("/blog", (req, res) => {
    res.send(`
        <!doctype html>
        <html>
            <head>
                <title>Blog</title>
                <meta name="description" content="Latest posts" />
            </head>
            <body>
                <h1>Blog</h1>
                <p>Latest posts</p>
            </body>
        </html>
    `);
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của thẻ `title`, `meta description`, HTML content, và SEO.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- thêm Open Graph metadata,
- thêm canonical URL,
- tạo route `/blog/:slug` có metadata theo bài viết,
- xử lý trường hợp không tìm thấy bài viết.

## Phần C — Câu hỏi vấn đáp
1. Metadata trong HTML dùng để làm gì?
2. SEO là gì?
3. Open Graph dùng trong trường hợp nào?
4. Vì sao mỗi trang nên có title và description riêng?

