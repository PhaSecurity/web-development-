# ĐỀ 34 — TẢI FILE BẰNG STREAM

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const fs = require("fs");
const path = require("path");
const app = express();

app.get("/download/:file", (req, res) => {
    const filePath = path.join(__dirname, "files", req.params.file);
    const stream = fs.createReadStream(filePath);
    stream.pipe(res);
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `createReadStream`, `pipe`, `path.join`, và response stream.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- chặn path traversal như `../secret.txt`,
- trả `404` nếu file không tồn tại,
- đặt header `Content-Disposition` để tải xuống,
- bắt lỗi stream và trả lỗi phù hợp.

## Phần C — Câu hỏi vấn đáp
1. Stream trong Node.js là gì?
2. Vì sao tải file lớn nên dùng stream?
3. Path traversal là lỗi bảo mật gì?
4. `res.download()` khác gì với tự stream file?

