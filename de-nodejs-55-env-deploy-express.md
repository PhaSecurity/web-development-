# ĐỀ 55 — BIẾN MÔI TRƯỜNG VÀ DEPLOY NODE.JS

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
require("dotenv").config();
const express = require("express");
const app = express();

app.get("/health", async (req, res) => {
    const response = await fetch(`${process.env.API_URL}/health`);
    const data = await response.json();

    res.json({ status: data.status, appName: process.env.APP_NAME });
});

app.listen(process.env.PORT || 3000);
```

File `.env`:

```txt
API_URL=http://localhost:3001
APP_NAME=Demo App
PORT=3000
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `dotenv`, `process.env`, file `.env`, `PORT`, và biến server.

## Phần B — Sửa hoặc viết bổ sung
Sửa hoặc mô tả cấu hình để:
- kiểm tra thiếu `API_URL` khi khởi động,
- không đưa secret vào response,
- tách cấu hình development và production,
- cấu hình biến môi trường khi deploy server.

## Phần C — Câu hỏi vấn đáp
1. Biến môi trường dùng để làm gì?
2. Vì sao không hard-code config trong source code?
3. Vì sao không commit file `.env` chứa secret?
4. Khi deploy Node.js cần kiểm tra những cấu hình nào?

