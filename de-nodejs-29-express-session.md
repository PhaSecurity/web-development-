# ĐỀ 29 — QUẢN LÝ SESSION VỚI EXPRESS-SESSION

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const session = require("express-session");
const app = express();

app.use(express.json());
app.use(session({
    secret: "secret-key",
    resave: false,
    saveUninitialized: false
}));

app.post("/login", (req, res) => {
    req.session.user = { id: 1, username: req.body.username };
    res.json({ message: "Logged in" });
});

app.get("/profile", (req, res) => {
    res.json(req.session.user || null);
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `express-session`, `secret`, `req.session`, `resave`, và `saveUninitialized`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- route `/profile` trả `401` nếu chưa đăng nhập,
- thêm middleware `requireLogin`,
- thêm route `/logout` hủy session,
- cấu hình cookie session có `httpOnly`, `sameSite`, và `maxAge`.

## Phần C — Câu hỏi vấn đáp
1. Session-based authentication là gì?
2. Session lưu ở đâu, cookie lưu gì?
3. Vì sao không nên dùng MemoryStore trong production?
4. `req.session.destroy()` dùng để làm gì?

