# ĐỀ 47 — PHỤC VỤ VÀ TỐI ƯU ẢNH TRONG NODE.JS

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const path = require("path");
const app = express();

app.use("/images", express.static(path.join(__dirname, "images")));

app.get("/avatar", (req, res) => {
    res.send(`
        <img src="/images/avatar.png" alt="User avatar" width="120" height="120" />
    `);
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `express.static`, `path.join`, `alt`, `width`, và `height`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- chỉ cho phép truy cập file ảnh `.png`, `.jpg`, `.webp`,
- thêm cache header cho ảnh tĩnh,
- xử lý ảnh không tồn tại bằng `404`,
- giải thích cách tạo nhiều kích thước ảnh bằng thư viện như `sharp`.

## Phần C — Câu hỏi vấn đáp
1. Static image là gì?
2. Vì sao ảnh cần thuộc tính `alt`?
3. `width` và `height` giúp tránh lỗi layout nào?
4. Cache ảnh tĩnh giúp website như thế nào?

