# ĐỀ 59 — XỬ LÝ LỖI TẬP TRUNG TRONG EXPRESS

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const app = express();

app.get("/users/:id", async (req, res, next) => {
    try {
        const user = await findUser(req.params.id);
        if (!user) {
            const error = new Error("User not found");
            error.status = 404;
            throw error;
        }
        res.json(user);
    } catch (error) {
        next(error);
    }
});

app.use((error, req, res, next) => {
    res.status(error.status || 500).json({ error: error.message });
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `try/catch`, `next(error)`, error middleware, `status`, và `500`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- không trả stack trace cho client,
- chuẩn hóa response lỗi gồm `code`, `message`, `requestId`,
- thêm helper `createError(status, message)`,
- xử lý lỗi validation riêng với status `400`.

## Phần C — Câu hỏi vấn đáp
1. Error middleware trong Express có đặc điểm gì?
2. Vì sao cần xử lý lỗi tập trung?
3. `404` khác gì với `500`?
4. Vì sao không nên trả lỗi nội bộ quá chi tiết cho client?

