# ĐỀ 50 — CACHE VÀ LÀM MỚI CACHE TRONG NODE.JS

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const app = express();

let cache = null;
let expiresAt = 0;

app.get("/news", async (req, res) => {
    if (cache && expiresAt > Date.now()) {
        return res.json(cache);
    }

    const response = await fetch("https://api.example.com/news");
    cache = await response.json();
    expiresAt = Date.now() + 60 * 1000;

    res.json(cache);
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của cache trong RAM, `expiresAt`, TTL 60 giây, và `fetch`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- thêm route không cache `/news/live`,
- thêm route `DELETE /news/cache` để xóa cache,
- xử lý lỗi API,
- giải thích khi nào dùng cache và khi nào không.

## Phần C — Câu hỏi vấn đáp
1. Cache trong backend giúp gì?
2. TTL là gì?
3. `no-store` trong frontend tương đương tư duy gì ở backend?
4. Dữ liệu nào không nên cache lâu?

