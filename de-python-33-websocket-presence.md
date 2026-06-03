# ĐỀ 33 — THEO DÕI ONLINE BẰNG WEBSOCKET TRONG FASTAPI

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```python
from fastapi import FastAPI, WebSocket

app = FastAPI()
online_users = {}

@app.websocket("/ws")
async def websocket_endpoint(websocket: WebSocket):
    await websocket.accept()
    user_id = await websocket.receive_text()
    online_users[user_id] = websocket
    await websocket.send_json({"online": list(online_users.keys())})
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của WebSocket, `accept`, `receive_text`, dictionary `online_users`, và `send_json`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- broadcast danh sách online cho tất cả client,
- xử lý khi client disconnect,
- một user có thể mở nhiều tab,
- kiểm tra `user_id` hợp lệ trước khi lưu.

## Phần C — Câu hỏi vấn đáp
1. WebSocket khác HTTP request như thế nào?
2. Presence trong ứng dụng chat là gì?
3. Vì sao cần xử lý disconnect?
4. Lưu connection trong RAM có hạn chế gì?

