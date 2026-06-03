# ĐỀ 57 — UPLOAD FILE VÀ VALIDATION BẰNG MULTER

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const multer = require("multer");
const app = express();

const upload = multer({ dest: "uploads/" });

app.post("/avatar", upload.single("avatar"), (req, res) => {
    res.json({
        originalName: req.file.originalname,
        path: req.file.path
    });
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của Multer, `dest`, `upload.single`, field `avatar`, và `req.file`.

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

