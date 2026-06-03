# ĐỀ 57 — UPLOAD FILE VÀ VALIDATION TRONG FASTAPI

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```python
from fastapi import FastAPI, UploadFile, File

app = FastAPI()

@app.post("/avatar")
async def upload_avatar(avatar: UploadFile = File(...)):
    content = await avatar.read()
    with open(f"uploads/{avatar.filename}", "wb") as f:
        f.write(content)

    return {"filename": avatar.filename}
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `UploadFile`, `File`, `await avatar.read()`, và lưu file.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- chỉ cho phép upload ảnh `.png`, `.jpg`, `.jpeg`,
- giới hạn dung lượng file tối đa 2MB,
- đổi tên file tránh trùng,
- trả `400` nếu thiếu file hoặc file không hợp lệ.

## Phần C — Câu hỏi vấn đáp
1. `multipart/form-data` dùng để làm gì?
2. Vì sao cần kiểm tra loại file upload?
3. Rủi ro khi public file upload là gì?
4. Nên lưu file trong server hay object storage khi production?

