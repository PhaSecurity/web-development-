# ĐỀ 56 — PHÂN TRANG VÀ SẮP XẾP API TRONG FASTAPI

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```python
from fastapi import FastAPI

app = FastAPI()

products = [
    {"id": 1, "name": "Laptop", "price": 1200},
    {"id": 2, "name": "Mouse", "price": 20},
]

@app.get("/products")
async def list_products(page: int = 1, limit: int = 10):
    start = (page - 1) * limit
    return products[start:start + limit]
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của query params `page`, `limit`, slicing list, và phân trang.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- validate `page` và `limit` là số dương,
- thêm sort theo `price` tăng hoặc giảm,
- trả thêm `total`, `page`, `limit`, và `items`,
- giới hạn `limit` tối đa là 100.

## Phần C — Câu hỏi vấn đáp
1. Vì sao API danh sách cần phân trang?
2. FastAPI validate query params như thế nào?
3. Offset pagination có hạn chế gì?
4. Vì sao cần giới hạn `limit` tối đa?

