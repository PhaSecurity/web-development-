# ĐỀ 33 — THEO DÕI ONLINE BẰNG WEBSOCKET TRONG PHP

## Phần A — Đọc và giải thích code
Cho đoạn mã Ratchet PHP sau:

```php
use Ratchet\MessageComponentInterface;
use Ratchet\ConnectionInterface;

class PresenceServer implements MessageComponentInterface {
    private array $users = [];

    public function onOpen(ConnectionInterface $conn) {}

    public function onMessage(ConnectionInterface $from, $msg) {
        $data = json_decode($msg, true);
        if ($data["type"] === "online") {
            $this->users[$data["userId"]] = $from;
            $this->broadcast();
        }
    }

    public function onClose(ConnectionInterface $conn) {
        foreach ($this->users as $userId => $client) {
            if ($client === $conn) unset($this->users[$userId]);
        }
        $this->broadcast();
    }

    private function broadcast() {}
}
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của WebSocket, `onMessage`, `onClose`, mảng `$users`, và broadcast.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- một user có thể mở nhiều tab cùng lúc,
- chỉ xóa user khi tất cả connection đã đóng,
- kiểm tra `userId` hợp lệ,
- gửi danh sách user online cho tất cả client.

## Phần C — Câu hỏi vấn đáp
1. Presence trong ứng dụng chat là gì?
2. WebSocket khác HTTP request thông thường thế nào?
3. Vì sao user có thể có nhiều connection?
4. Lưu danh sách online trong RAM có hạn chế gì?

