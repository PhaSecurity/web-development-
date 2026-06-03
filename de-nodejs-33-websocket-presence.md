# ĐỀ 33 — THEO DÕI TRẠNG THÁI ONLINE BẰNG SOCKET.IO

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const { Server } = require("socket.io");
const io = new Server(3000);
const onlineUsers = new Map();

io.on("connection", socket => {
    socket.on("online", userId => {
        onlineUsers.set(userId, socket.id);
        io.emit("presence", Array.from(onlineUsers.keys()));
    });

    socket.on("disconnect", () => {
        for (const [userId, socketId] of onlineUsers.entries()) {
            if (socketId === socket.id) onlineUsers.delete(userId);
        }
        io.emit("presence", Array.from(onlineUsers.keys()));
    });
});
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `Map`, event `online`, `disconnect`, và `io.emit`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- một user có thể mở nhiều tab cùng lúc,
- chỉ xóa user khỏi danh sách online khi tất cả tab đã disconnect,
- kiểm tra `userId` hợp lệ trước khi lưu,
- emit danh sách online sau mỗi thay đổi.

## Phần C — Câu hỏi vấn đáp
1. Presence trong ứng dụng chat là gì?
2. Vì sao một user có thể có nhiều socket?
3. `io.emit` khác gì với `socket.emit`?
4. Dữ liệu online lưu trong RAM có hạn chế gì?

