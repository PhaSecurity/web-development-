# ĐỀ 70 — RATE LIMIT CHO API ĐĂNG NHẬP

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const rateLimit = require("express-rate-limit");
const app = express();

const loginLimiter = rateLimit({
    windowMs: 15 * 60 * 1000,
    max: 5
});

app.post("/login", loginLimiter, (req, res) => {
    res.json({ message: "Login attempt" });
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `express-rate-limit`, `windowMs`, `max`, middleware, và route `/login`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- trả message rõ ràng khi vượt giới hạn,
- rate limit theo IP và email đăng nhập,
- không áp dụng cùng giới hạn cho route public bình thường,
- log các lần bị chặn.

## Phần C — Câu hỏi vấn đáp
1. Rate limit dùng để chống vấn đề gì?
2. Vì sao login cần giới hạn số lần thử?
3. Rate limit theo IP có hạn chế gì?
4. Khi chạy sau proxy cần cấu hình gì?

