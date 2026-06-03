# ĐỀ 38 — CRUD VỚI PRISMA

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const { PrismaClient } = require("@prisma/client");
const prisma = new PrismaClient();

async function listUsers() {
    return prisma.user.findMany({
        orderBy: { id: "desc" }
    });
}

async function createUser(email, name) {
    return prisma.user.create({
        data: { email, name }
    });
}
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `PrismaClient`, `findMany`, `create`, `data`, và `orderBy`.

## Phần B — Sửa hoặc viết bổ sung
Viết API Express để:
- `GET /users` lấy danh sách user,
- `POST /users` tạo user mới,
- kiểm tra `email` không được rỗng,
- xử lý lỗi email bị trùng và trả `409`.

## Phần C — Câu hỏi vấn đáp
1. Prisma là gì?
2. ORM giúp gì khi làm backend?
3. Prisma schema dùng để làm gì?
4. Vì sao vẫn cần hiểu SQL khi dùng ORM?

