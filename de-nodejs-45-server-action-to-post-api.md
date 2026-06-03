# ĐỀ 45 — TẠO TODO BẰNG POST API TRONG EXPRESS

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const app = express();

app.use(express.urlencoded({ extended: false }));

const todos = [];

app.post("/todos", (req, res) => {
    const title = req.body.title;
    todos.push({ id: Date.now(), title });
    res.redirect("/todos");
});

app.get("/todos", (req, res) => {
    res.send(todos.map(todo => `<p>${todo.title}</p>`).join(""));
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `express.urlencoded`, `req.body`, POST form, `res.redirect`, và mảng `todos`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- kiểm tra `title` không được rỗng,
- lưu todo bằng một hàm riêng,
- sau khi tạo xong redirect về `/todos`,
- xử lý lỗi và hiển thị thông báo phù hợp.

## Phần C — Câu hỏi vấn đáp
1. POST request thường dùng để làm gì?
2. `express.urlencoded()` khác gì với `express.json()`?
3. Vì sao logic ghi database nên đặt ở server?
4. Redirect sau POST giúp tránh vấn đề gì?

