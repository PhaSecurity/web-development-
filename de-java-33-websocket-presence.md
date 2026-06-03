# ĐỀ 33 — THEO DÕI ONLINE BẰNG WEBSOCKET TRONG SPRING

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```java
@Component
public class PresenceHandler extends TextWebSocketHandler {
    private final Map<String, WebSocketSession> onlineUsers = new ConcurrentHashMap<>();

    @Override
    protected void handleTextMessage(WebSocketSession session, TextMessage message) {
        String userId = message.getPayload();
        onlineUsers.put(userId, session);
    }

    @Override
    public void afterConnectionClosed(WebSocketSession session, CloseStatus status) {
        onlineUsers.entrySet().removeIf(e -> e.getValue().equals(session));
    }
}
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `TextWebSocketHandler`, `WebSocketSession`, `ConcurrentHashMap`, và `afterConnectionClosed`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- broadcast danh sách online sau mỗi thay đổi,
- một user có thể mở nhiều tab,
- chỉ xóa user khi tất cả session đã đóng,
- kiểm tra `userId` hợp lệ.

## Phần C — Câu hỏi vấn đáp
1. WebSocket phù hợp với bài toán nào?
2. Vì sao cần `ConcurrentHashMap`?
3. User mở nhiều tab ảnh hưởng đến presence thế nào?
4. Lưu trạng thái online trong RAM có hạn chế gì?

