# ĐỀ 63 — QUẢN LÝ MYSQL CONNECTION POOL

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const mysql = require("mysql2/promise");

const pool = mysql.createPool({
    host: "localhost",
    user: "root",
    database: "shop",
    waitForConnections: true,
    connectionLimit: 10
});

async function listOrders() {
    const [rows] = await pool.query("SELECT * FROM orders ORDER BY id DESC");
    return rows;
}
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của connection pool, `waitForConnections`, `connectionLimit`, `pool.query`, và `rows`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- lấy cấu hình database từ biến môi trường,
- thêm API `GET /orders`,
- xử lý lỗi database bằng error middleware,
- chỉ select các cột cần thiết thay vì `SELECT *`.

## Phần C — Câu hỏi vấn đáp
1. Connection pool dùng để làm gì?
2. Vì sao không nên tạo connection mới cho mọi request?
3. `connectionLimit` quá cao có rủi ro gì?
4. Vì sao nên tránh `SELECT *`?

