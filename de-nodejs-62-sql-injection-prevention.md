# ĐỀ 62 — CHỐNG SQL INJECTION TRONG NODE.JS

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const mysql = require("mysql2/promise");

async function findUserByEmail(email) {
    const connection = await mysql.createConnection({ database: "app" });
    const [rows] = await connection.execute(
        "SELECT id, email FROM users WHERE email = ?",
        [email]
    );
    return rows[0];
}
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `mysql2/promise`, `execute`, placeholder `?`, mảng tham số, và `rows[0]`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- luôn đóng connection sau khi query,
- validate email trước khi query,
- trả `null` nếu không tìm thấy user,
- viết thêm API `GET /users?email=...` sử dụng hàm trên.

## Phần C — Câu hỏi vấn đáp
1. SQL injection là gì?
2. Parameterized query chống SQL injection như thế nào?
3. `execute` khác gì với ghép chuỗi SQL?
4. Vì sao connection cần được đóng hoặc dùng pool?

