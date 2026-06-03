# ĐỀ 12 — CẤU HÌNH CORS CHO API EXPRESS

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const cors = require("cors");

const app = express();

app.use(cors());

app.get("/api/products", (req, res) => {
    res.json([
        { id: 1, name: "Laptop" },
        { id: 2, name: "Mouse" }
    ]);
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `cors()` và vì sao frontend ở domain khác có thể gọi API.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- chỉ cho phép origin `http://localhost:5173`,
- chỉ cho phép method `GET` và `POST`,
- thêm route `POST /api/products` nhận JSON và trả về sản phẩm vừa tạo.

## Phần C — Câu hỏi vấn đáp
1. CORS là gì?
2. Vì sao trình duyệt chặn request cross-origin trong một số trường hợp?
3. Header `Access-Control-Allow-Origin` có tác dụng gì?
4. Nếu cấu hình CORS quá rộng trong môi trường production thì có rủi ro gì?
