# ĐỀ 65 — LƯU SESSION BẰNG REDIS

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const session = require("express-session");
const RedisStore = require("connect-redis").default;
const { createClient } = require("redis");

const redisClient = createClient({ url: process.env.REDIS_URL });
redisClient.connect();

app.use(session({
    store: new RedisStore({ client: redisClient }),
    secret: process.env.SESSION_SECRET,
    resave: false,
    saveUninitialized: false
}));
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của Redis session store, `express-session`, `SESSION_SECRET`, `resave`, và `saveUninitialized`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- cấu hình cookie `httpOnly`, `sameSite`, `secure`, và `maxAge`,
- xử lý lỗi khi Redis không kết nối được,
- thêm route login lưu `req.session.user`,
- thêm route logout hủy session.

## Phần C — Câu hỏi vấn đáp
1. Vì sao production không nên dùng MemoryStore?
2. Redis phù hợp để lưu session vì sao?
3. Cookie session lưu gì?
4. Khi logout cần xóa session như thế nào?

