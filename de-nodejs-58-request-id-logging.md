# ĐỀ 58 — REQUEST ID VÀ LOGGING MIDDLEWARE

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const crypto = require("crypto");
const app = express();

app.use((req, res, next) => {
    req.requestId = crypto.randomUUID();
    console.log(`[${req.requestId}] ${req.method} ${req.url}`);
    next();
});

app.get("/ping", (req, res) => {
    res.json({ requestId: req.requestId, message: "pong" });
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của middleware, `crypto.randomUUID`, `req.requestId`, log request, và `next`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- nhận request id từ header `x-request-id` nếu có,
- thêm header `x-request-id` vào response,
- log thời gian xử lý request,
- không log thông tin nhạy cảm như token hoặc password.

## Phần C — Câu hỏi vấn đáp
1. Request ID dùng để làm gì?
2. Vì sao logging quan trọng khi debug production?
3. Middleware đo thời gian request hoạt động như thế nào?
4. Log dữ liệu nhạy cảm có rủi ro gì?

