# ĐỀ 9 — GIỚI HẠN TẦN SUẤT GỌI API

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const rateLimit = require("express-rate-limit");

const app = express();

const limiter = rateLimit({
    windowMs: 60 * 1000,
    max: 5
});

app.use("/api/", limiter);

app.get("/api/data", (req, res) => {
    res.json({ message: "Dữ liệu API" });
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `windowMs`, `max`, `app.use("/api/", limiter)`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- khi vượt quá giới hạn thì trả JSON lỗi thay vì message mặc định,
- chỉ áp dụng rate limit cho route `/api/data`,
- thêm route `/health` không bị giới hạn.

## Phần C — Câu hỏi vấn đáp
1. Rate limiting là gì?
2. Vì sao API cần giới hạn tần suất gọi?
3. Nếu không có rate limit thì có thể bị tấn công kiểu gì?
4. `429 Too Many Requests` có ý nghĩa gì?
