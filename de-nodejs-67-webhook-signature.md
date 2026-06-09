# ĐỀ 67 — KIỂM TRA CHỮ KÝ WEBHOOK

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const crypto = require("crypto");
const app = express();

app.use("/webhook", express.raw({ type: "application/json" }));

app.post("/webhook", (req, res) => {
    const signature = req.headers["x-signature"];
    const expected = crypto
        .createHmac("sha256", process.env.WEBHOOK_SECRET)
        .update(req.body)
        .digest("hex");

    if (signature !== expected) {
        return res.status(401).json({ error: "Invalid signature" });
    }

    res.json({ received: true });
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của webhook, `express.raw`, HMAC, `WEBHOOK_SECRET`, và header `x-signature`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- dùng `crypto.timingSafeEqual` khi so sánh chữ ký,
- parse JSON sau khi xác thực chữ ký,
- trả `400` nếu body không hợp lệ,
- chống xử lý trùng event bằng `eventId`.

## Phần C — Câu hỏi vấn đáp
1. Webhook là gì?
2. Vì sao cần xác thực chữ ký webhook?
3. Vì sao body raw quan trọng khi verify signature?
4. Idempotency trong webhook là gì?

