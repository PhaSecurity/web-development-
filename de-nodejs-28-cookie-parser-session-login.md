# ĐỀ 28 — ĐĂNG NHẬP BẰNG COOKIE

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const cookieParser = require("cookie-parser");
const app = express();

app.use(express.json());
app.use(cookieParser());

app.post("/login", (req, res) => {
    if (req.body.username === "admin" && req.body.password === "123") {
        res.cookie("user", "admin");
        return res.json({ loggedIn: true });
    }

    res.status(401).json({ error: "Invalid credentials" });
});

app.get("/me", (req, res) => {
    res.json({ user: req.cookies.user || null });
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của cookie, `cookie-parser`, `res.cookie`, và `req.cookies`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- đặt cookie có `httpOnly`, `sameSite`, và thời hạn 1 giờ,
- thêm route `POST /logout` để xóa cookie,
- route `/me` trả `401` nếu chưa đăng nhập,
- không lưu mật khẩu hoặc thông tin nhạy cảm trong cookie.

## Phần C — Câu hỏi vấn đáp
1. Cookie dùng để làm gì trong web?
2. `httpOnly` giúp bảo vệ cookie như thế nào?
3. Cookie khác gì với localStorage?
4. Vì sao cookie đăng nhập cần thời hạn hết hạn?

