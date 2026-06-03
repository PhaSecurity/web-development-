# ĐỀ 61 — PHÂN QUYỀN ROLE VÀ PERMISSION

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
function requireRole(role) {
    return (req, res, next) => {
        if (req.user.role !== role) {
            return res.status(403).json({ error: "Forbidden" });
        }
        next();
    };
}

app.delete("/posts/:id", requireLogin, requireRole("admin"), (req, res) => {
    res.json({ deleted: true });
});
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của higher-order middleware, `req.user`, role, `403`, và route xóa bài viết.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- hỗ trợ nhiều role được phép truy cập,
- thêm permission `post:delete`,
- admin hoặc owner bài viết được quyền xóa,
- trả `401` nếu chưa đăng nhập và `403` nếu không đủ quyền.

## Phần C — Câu hỏi vấn đáp
1. Authentication khác authorization như thế nào?
2. Role khác permission thế nào?
3. Vì sao cần kiểm tra owner của tài nguyên?
4. `401` khác `403` thế nào?

