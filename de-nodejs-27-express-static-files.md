# ĐỀ 27 — PHỤC VỤ FILE TĨNH BẰNG EXPRESS STATIC

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const path = require("path");
const app = express();

app.use("/public", express.static(path.join(__dirname, "public")));

app.get("/", (req, res) => {
    res.send("<h1>Home</h1><img src='/public/logo.png' />");
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `express.static`, `path.join`, `__dirname`, và prefix `/public`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- phục vụ thư mục `uploads` tại URL `/files`,
- chặn truy cập các file không phải `.jpg`, `.png`, `.pdf`,
- thêm cache header cho file tĩnh trong 1 ngày,
- trả `404` nếu file không tồn tại.

## Phần C — Câu hỏi vấn đáp
1. Static file là gì?
2. Vì sao không nên public toàn bộ thư mục project?
3. Cache static file giúp gì cho website?
4. Rủi ro khi cho người dùng upload rồi public file là gì?

