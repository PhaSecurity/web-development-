# ĐỀ 43 — API ROUTE HANDLER TRONG EXPRESS

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const app = express();

app.use(express.json());

const tasks = [{ id: 1, title: "Learn Express" }];

app.get("/api/tasks", (req, res) => {
    res.json(tasks);
});

app.post("/api/tasks", (req, res) => {
    const task = { id: Date.now(), title: req.body.title };
    tasks.push(task);
    res.status(201).json(task);
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `express.json`, `GET`, `POST`, `req.body`, và `res.json`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- trả `400` nếu thiếu `title`,
- thêm `DELETE /api/tasks/:id`,
- trả `404` nếu task cần xóa không tồn tại,
- giải thích hạn chế khi lưu dữ liệu bằng biến `tasks` trong server.

## Phần C — Câu hỏi vấn đáp
1. REST API là gì?
2. Express route handler dùng để làm gì?
3. Vì sao biến toàn cục không phù hợp để lưu dữ liệu thật?
4. `201 Created` dùng trong trường hợp nào?

