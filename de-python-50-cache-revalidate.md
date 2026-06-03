# ĐỀ 50 — CACHE DỮ LIỆU TRONG PYTHON

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```python
import time
import httpx
from fastapi import FastAPI

app = FastAPI()
cache = {"data": None, "expires_at": 0}

@app.get("/news")
async def news():
    if cache["data"] and cache["expires_at"] > time.time():
        return cache["data"]

    response = httpx.get("https://api.example.com/news")
    cache["data"] = response.json()
    cache["expires_at"] = time.time() + 60
    return cache["data"]
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của cache trong RAM, `expires_at`, thời gian 60 giây, và HTTP client.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- xử lý lỗi khi API bên ngoài thất bại,
- thêm route xóa cache,
- không cache dữ liệu realtime,
- giải thích hạn chế của cache trong RAM khi chạy nhiều server.

## Phần C — Câu hỏi vấn đáp
1. Cache giúp giảm tải như thế nào?
2. TTL là gì?
3. Khi nào cần invalidate cache?
4. Vì sao production thường dùng Redis thay vì dict trong RAM?

