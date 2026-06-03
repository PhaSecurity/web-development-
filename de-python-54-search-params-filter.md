# ĐỀ 54 — FILTER BẰNG QUERY PARAMS TRONG FASTAPI

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```python
from fastapi import FastAPI

app = FastAPI()

products = [
    {"id": 1, "name": "Laptop", "category": "tech"},
    {"id": 2, "name": "Mouse", "category": "tech"},
]

@app.get("/products")
async def list_products(q: str = ""):
    return [p for p in products if q.lower() in p["name"].lower()]
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của query param `q`, default value, list comprehension, và filter dữ liệu.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- thêm filter `category` và `page`,
- validate `page` là số dương,
- giới hạn mỗi trang 10 sản phẩm,
- trả `total`, `page`, và `items`.

## Phần C — Câu hỏi vấn đáp
1. Query params dùng để làm gì?
2. FastAPI tự parse query params như thế nào?
3. Pagination nên xử lý ở đâu?
4. Vì sao cần encode keyword khi gọi API từ client?

