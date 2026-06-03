# ĐỀ 44 — FORM SUBMIT BẰNG FASTAPI

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```python
from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI()

class ContactRequest(BaseModel):
    email: str

@app.post("/contact")
async def contact(data: ContactRequest):
    return {"email": data.email}
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của FastAPI, Pydantic model, `@app.post`, JSON body, và async function.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- validate email không được rỗng,
- trả lỗi `400` hoặc `422` khi dữ liệu không hợp lệ,
- thêm frontend dùng `fetch` gửi form,
- hiển thị loading và lỗi ở phía client.

## Phần C — Câu hỏi vấn đáp
1. FastAPI đọc JSON body như thế nào?
2. Pydantic giúp validation ra sao?
3. Vì sao form submit mặc định reload trang?
4. Loading state giúp cải thiện UX như thế nào?

