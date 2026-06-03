# ĐỀ 46 — MIDDLEWARE BẢO VỆ ROUTE TRONG EXPRESS

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const cookieParser = require("cookie-parser");
const app = express();

app.use(cookieParser());

function requireLogin(req, res, next) {
    const token = req.cookies.token;

    if (!token) {
        return res.redirect("/login");
    }

    next();
}

app.get("/dashboard", requireLogin, (req, res) => {
    res.send("Dashboard");
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của middleware, `req.cookies`, `res.redirect`, `next`, và route `/dashboard`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- chỉ cho phép token có giá trị hợp lệ,
- redirect về `/login?next=...`,
- không áp dụng middleware cho static assets,
- thêm logic chặn user chưa có role `admin` vào `/dashboard/admin`.

## Phần C — Câu hỏi vấn đáp
1. Middleware trong Express chạy khi nào?
2. Middleware phù hợp để xử lý việc gì?
3. Authentication khác authorization thế nào?
4. Vì sao không nên chỉ kiểm tra token có tồn tại?

