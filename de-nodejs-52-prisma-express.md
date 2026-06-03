# ĐỀ 52 — DÙNG PRISMA TRONG EXPRESS

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const { PrismaClient } = require("@prisma/client");

const app = express();
const prisma = new PrismaClient();

app.get("/users", async (req, res) => {
    const users = await prisma.user.findMany();
    res.json(users);
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của Prisma Client, Express route, `findMany`, và vì sao database query chạy ở server.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- tạo helper dùng chung Prisma Client,
- sắp xếp user theo ngày tạo mới nhất,
- chỉ lấy các field `id`, `email`, `name`,
- xử lý khi danh sách user rỗng.

## Phần C — Câu hỏi vấn đáp
1. Vì sao không được query database trực tiếp từ browser?
2. Prisma Client nên được khởi tạo thế nào?
3. `select` trong Prisma giúp gì?
4. Rủi ro khi tạo quá nhiều database connection là gì?

