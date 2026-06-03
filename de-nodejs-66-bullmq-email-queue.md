# ĐỀ 66 — GỬI EMAIL BẰNG JOB QUEUE BULLMQ

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const { Queue, Worker } = require("bullmq");

const emailQueue = new Queue("email", {
    connection: { host: "localhost", port: 6379 }
});

app.post("/send-email", async (req, res) => {
    await emailQueue.add("welcome", { to: req.body.email });
    res.json({ queued: true });
});

new Worker("email", async job => {
    console.log("Sending email to", job.data.to);
}, {
    connection: { host: "localhost", port: 6379 }
});
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của Queue, Worker, Redis connection, job name, và `job.data`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- validate email trước khi đưa vào queue,
- retry job tối đa 3 lần nếu gửi thất bại,
- thêm delay 5 giây trước khi chạy job,
- log trạng thái completed và failed.

## Phần C — Câu hỏi vấn đáp
1. Job queue dùng để làm gì?
2. Vì sao gửi email nên chạy nền?
3. Redis có vai trò gì trong BullMQ?
4. Retry job cần chú ý điều gì?

