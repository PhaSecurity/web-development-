# ĐỀ 19 — ĐĂNG NHẬP VỚI ACCESS TOKEN VÀ REFRESH TOKEN

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const jwt = require("jsonwebtoken");

const app = express();
app.use(express.json());

const users = [{ id: 1, username: "admin", password: "123456" }];

app.post("/login", (req, res) => {
    const user = users.find(u =>
        u.username === req.body.username && u.password === req.body.password
    );

    if (!user) {
        return res.status(401).json({ message: "Invalid credentials" });
    }

    const accessToken = jwt.sign({ userId: user.id }, "access-secret", {
        expiresIn: "15m"
    });

    const refreshToken = jwt.sign({ userId: user.id }, "refresh-secret", {
        expiresIn: "7d"
    });

    res.json({ accessToken, refreshToken });
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của access token, refresh token, `jwt.sign(...)`, và `expiresIn`.

## Phần B — Sửa hoặc viết bổ sung
Viết thêm route `POST /refresh-token` để:
- nhận `refreshToken` từ body,
- kiểm tra token bằng `jwt.verify(...)`,
- nếu hợp lệ thì cấp access token mới,
- nếu token sai hoặc hết hạn thì trả `401`.

## Phần C — Câu hỏi vấn đáp
1. Vì sao access token thường có thời gian sống ngắn?
2. Refresh token dùng để làm gì?
3. Nếu refresh token bị lộ thì nguy hiểm như thế nào?
4. Vì sao không nên hard-code secret trong source code?
