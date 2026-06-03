# ĐỀ 44 — XỬ LÝ FORM BẰNG EXPRESS API

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const app = express();

app.use(express.static("public"));
app.use(express.json());

app.post("/api/contact", (req, res) => {
    res.json({ email: req.body.email });
});

app.listen(3000);
```

File `public/contact.html`:

```html
<form id="contactForm">
    <input id="email" />
    <button type="submit">Send</button>
</form>

<script>
document.getElementById("contactForm").addEventListener("submit", async e => {
    e.preventDefault();
    const email = document.getElementById("email").value;

    await fetch("/api/contact", {
        method: "POST",
        body: JSON.stringify({ email })
    });
});
</script>
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `express.static`, `express.json`, `fetch`, `preventDefault`, và JSON body.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- validate email không được rỗng,
- hiển thị trạng thái loading khi submit,
- hiển thị lỗi nếu API thất bại,
- thêm header `Content-Type: application/json`.

## Phần C — Câu hỏi vấn đáp
1. Vì sao form submit mặc định reload trang?
2. `express.json()` dùng để làm gì?
3. Vì sao cần validate dữ liệu ở server?
4. Loading state giúp cải thiện UX như thế nào?

