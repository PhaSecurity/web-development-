# ĐỀ 37 — GỬI EMAIL BẰNG NODEMAILER

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const nodemailer = require("nodemailer");

const transporter = nodemailer.createTransport({
    host: "smtp.example.com",
    port: 587,
    auth: {
        user: process.env.SMTP_USER,
        pass: process.env.SMTP_PASS
    }
});

async function sendWelcomeEmail(to) {
    await transporter.sendMail({
        from: "app@example.com",
        to,
        subject: "Welcome",
        text: "Thanks for registering"
    });
}
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của SMTP, `createTransport`, `auth`, và `sendMail`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- kiểm tra email người nhận không được rỗng,
- gửi cả `text` và `html`,
- bắt lỗi gửi mail và trả lỗi cho API,
- không hard-code địa chỉ `from` mà lấy từ biến môi trường.

## Phần C — Câu hỏi vấn đáp
1. SMTP là gì?
2. Vì sao thông tin SMTP phải để trong `.env`?
3. Email HTML cần lưu ý gì về bảo mật?
4. Khi gửi email hàng loạt cần tránh vấn đề gì?

