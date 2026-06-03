# ĐỀ 60 — JWT REFRESH TOKEN ROTATION

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const jwt = require("jsonwebtoken");
const express = require("express");
const app = express();

app.use(express.json());

app.post("/refresh", (req, res) => {
    const { refreshToken } = req.body;
    const payload = jwt.verify(refreshToken, process.env.REFRESH_SECRET);

    const accessToken = jwt.sign(
        { userId: payload.userId },
        process.env.ACCESS_SECRET,
        { expiresIn: "15m" }
    );

    res.json({ accessToken });
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của refresh token, access token, `jwt.verify`, `jwt.sign`, và `expiresIn`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- lưu refresh token hợp lệ trong database hoặc Redis,
- sau mỗi lần refresh tạo refresh token mới,
- vô hiệu hóa refresh token cũ,
- trả `401` nếu token hết hạn hoặc không còn hợp lệ.

## Phần C — Câu hỏi vấn đáp
1. Access token khác refresh token thế nào?
2. Token rotation giúp giảm rủi ro gì?
3. Vì sao refresh token nên có thời gian sống dài hơn access token?
4. Khi logout cần xử lý refresh token như thế nào?

