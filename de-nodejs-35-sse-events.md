# ĐỀ 35 — SERVER-SENT EVENTS TRONG EXPRESS

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const app = express();

app.get("/events", (req, res) => {
    res.setHeader("Content-Type", "text/event-stream");
    res.setHeader("Cache-Control", "no-cache");

    const timer = setInterval(() => {
        res.write(`data: ${new Date().toISOString()}\n\n`);
    }, 1000);

    req.on("close", () => clearInterval(timer));
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `text/event-stream`, `res.write`, `setInterval`, và event `close`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- gửi event tên `time`,
- gửi thêm event `heartbeat` mỗi 10 giây,
- dừng interval khi client ngắt kết nối,
- thêm route `/notify` để broadcast một message tới tất cả SSE clients.

## Phần C — Câu hỏi vấn đáp
1. Server-Sent Events là gì?
2. SSE khác gì với WebSocket?
3. SSE phù hợp với loại ứng dụng nào?
4. Vì sao cần xử lý khi client đóng kết nối?

