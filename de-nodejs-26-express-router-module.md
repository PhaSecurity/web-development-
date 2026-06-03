# ĐỀ 26 — TÁCH ROUTE BẰNG EXPRESS ROUTER

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const app = express();
const userRouter = express.Router();

userRouter.get("/", (req, res) => {
    res.json([{ id: 1, name: "An" }]);
});

userRouter.get("/:id", (req, res) => {
    res.json({ id: req.params.id, name: "An" });
});

app.use("/users", userRouter);
app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `express.Router()`, `req.params`, và `app.use("/users", ...)`.

## Phần B — Sửa hoặc viết bổ sung
Sửa hoặc viết thêm code để:
- tách router ra file `routes/users.js`,
- thêm route `POST /users` nhận `name` từ body,
- trả `400` nếu thiếu `name`,
- export router và import lại trong file chính.

## Phần C — Câu hỏi vấn đáp
1. Vì sao nên tách route ra nhiều file?
2. `app.use()` khác gì với `app.get()`?
3. Router-level middleware là gì?
4. Khi nào nên nhóm API theo resource?

