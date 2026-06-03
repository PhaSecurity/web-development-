# ĐỀ 53 — VALIDATION VỚI ZOD TRONG EXPRESS API

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const { z } = require("zod");
const app = express();

app.use(express.json());

const schema = z.object({
    email: z.string().email(),
    password: z.string().min(6)
});

app.post("/register", (req, res) => {
    const data = schema.parse(req.body);
    res.json({ email: data.email });
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của Zod, `z.object`, `email()`, `min(6)`, `parse`, và `req.body`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- dùng `safeParse` thay vì `parse`,
- trả `400` kèm danh sách lỗi nếu dữ liệu không hợp lệ,
- không trả password trong response,
- thêm trường `name` tối thiểu 2 ký tự.

## Phần C — Câu hỏi vấn đáp
1. Validation dữ liệu đầu vào quan trọng như thế nào?
2. `parse` khác gì với `safeParse`?
3. Vì sao không tin dữ liệu từ client?
4. Zod có thể dùng chung cho frontend và backend không?

