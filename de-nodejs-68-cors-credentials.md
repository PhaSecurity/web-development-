# ĐỀ 68 — CORS VÀ COOKIE CREDENTIALS

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const cors = require("cors");
const app = express();

app.use(cors({
    origin: "http://localhost:5173",
    credentials: true
}));

app.get("/me", (req, res) => {
    res.json({ user: "admin" });
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của CORS, `origin`, `credentials`, cookie cross-origin, và route `/me`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- cho phép nhiều origin từ biến môi trường,
- từ chối origin không nằm trong allowlist,
- cấu hình cookie phù hợp với cross-site request,
- xử lý preflight request đúng cách.

## Phần C — Câu hỏi vấn đáp
1. CORS là gì?
2. Preflight request xảy ra khi nào?
3. `credentials: true` ảnh hưởng gì?
4. Vì sao không nên dùng `origin: "*"` với cookie?

