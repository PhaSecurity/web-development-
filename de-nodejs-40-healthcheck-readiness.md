# ĐỀ 40 — HEALTH CHECK VÀ READINESS API

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const app = express();

let startedAt = new Date();

app.get("/health", (req, res) => {
    res.json({
        status: "ok",
        uptime: process.uptime(),
        startedAt
    });
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của health check, `process.uptime()`, và route `/health`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- thêm route `/ready` kiểm tra kết nối database,
- `/ready` trả `503` nếu database chưa sẵn sàng,
- không trả thông tin nhạy cảm trong health check,
- thêm trường `version` lấy từ biến môi trường.

## Phần C — Câu hỏi vấn đáp
1. Health check dùng để làm gì?
2. Health khác readiness như thế nào?
3. Vì sao load balancer cần endpoint kiểm tra trạng thái?
4. Khi nào API nên trả `503`?

