# ĐỀ 25 — THÔNG BÁO REAL-TIME VỚI SOCKET.IO

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const http = require("http");
const { Server } = require("socket.io");

const app = express();
const server = http.createServer(app);
const io = new Server(server);

io.on("connection", socket => {
    console.log("Client connected", socket.id);

    socket.on("join-user-room", userId => {
        socket.join(`user:${userId}`);
    });
});

app.post("/notify/:userId", express.json(), (req, res) => {
    io.to(`user:${req.params.userId}`).emit("notification", {
        message: req.body.message
    });

    res.json({ sent: true });
});

server.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của Socket.IO, `connection`, `socket.join(...)`, room, và `io.to(...).emit(...)`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- kiểm tra `message` không được rỗng,
- chỉ cho user join room của chính mình sau khi xác thực token,
- thêm event `disconnect` để log khi client ngắt kết nối,
- API `/notify/:userId` trả `400` nếu thiếu message.

## Phần C — Câu hỏi vấn đáp
1. Real-time communication là gì?
2. Socket.IO khác gì với HTTP request thông thường?
3. Room trong Socket.IO dùng để làm gì?
4. Vì sao không nên để client tự ý join room của user khác?
