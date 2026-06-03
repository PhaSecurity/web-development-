# ĐỀ 49 — LOADING VÀ ERROR KHI GỌI API BẰNG EXPRESS

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const app = express();

app.get("/dashboard", async (req, res) => {
    const response = await fetch("https://api.example.com/stats");
    const stats = await response.json();

    res.send(`<pre>${JSON.stringify(stats, null, 2)}</pre>`);
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của async route, `fetch`, `response.json`, và render dữ liệu ra HTML.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- kiểm tra `response.ok`,
- dùng `try/catch` để bắt lỗi,
- trả giao diện fallback khi dữ liệu rỗng,
- thêm middleware xử lý lỗi chung cho Express.

## Phần C — Câu hỏi vấn đáp
1. Vì sao cần kiểm tra `response.ok` sau khi fetch?
2. `try/catch` trong async function dùng để làm gì?
3. Error middleware của Express có bao nhiêu tham số?
4. Loading state nên xử lý ở client hay server?

