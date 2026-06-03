# ĐỀ 42 — DYNAMIC ROUTE TRONG EXPRESS

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const app = express();

app.get("/posts/:id", async (req, res) => {
    const response = await fetch(`https://api.example.com/posts/${req.params.id}`);
    const post = await response.json();

    res.send(`
        <article>
            <h1>${post.title}</h1>
            <p>${post.content}</p>
        </article>
    `);
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `:id`, `req.params`, dynamic route, và template string.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- trả `404` nếu bài viết không tồn tại,
- validate `req.params.id` là số,
- xử lý lỗi khi API bên ngoài thất bại,
- thêm link quay lại danh sách bài viết.

## Phần C — Câu hỏi vấn đáp
1. Route parameter trong Express dùng để làm gì?
2. `req.params` khác gì với `req.query`?
3. Vì sao cần validate id trước khi query?
4. Khi nào API nên trả `404`?

