# ĐỀ 69 — BẢO VỆ CSRF CHO FORM

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const csrf = require("csurf");
const cookieParser = require("cookie-parser");
const app = express();

app.use(cookieParser());
app.use(express.urlencoded({ extended: false }));
app.use(csrf({ cookie: true }));

app.get("/form", (req, res) => {
    res.send(`<form method="post"><input name="_csrf" value="${req.csrfToken()}" /><button>Save</button></form>`);
});

app.post("/form", (req, res) => {
    res.send("Saved");
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của CSRF token, `csurf`, cookie, hidden input, và POST form.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- trả lỗi `403` nếu CSRF token không hợp lệ,
- không áp dụng CSRF cho route webhook,
- thêm cookie `sameSite`,
- giải thích khi nào API dùng JWT bearer có thể không cần CSRF.

## Phần C — Câu hỏi vấn đáp
1. CSRF là gì?
2. CSRF token bảo vệ form như thế nào?
3. SameSite cookie giúp giảm CSRF ra sao?
4. CSRF khác XSS thế nào?

