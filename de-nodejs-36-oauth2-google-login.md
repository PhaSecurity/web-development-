# ĐỀ 36 — ĐĂNG NHẬP GOOGLE OAUTH2

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const passport = require("passport");
const GoogleStrategy = require("passport-google-oauth20").Strategy;

passport.use(new GoogleStrategy({
    clientID: process.env.GOOGLE_CLIENT_ID,
    clientSecret: process.env.GOOGLE_CLIENT_SECRET,
    callbackURL: "/auth/google/callback"
}, (accessToken, refreshToken, profile, done) => {
    done(null, { id: profile.id, email: profile.emails[0].value });
}));
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của Passport, Google Strategy, `clientID`, `clientSecret`, `callbackURL`, và `done`.

## Phần B — Sửa hoặc viết bổ sung
Viết thêm route để:
- bắt đầu đăng nhập tại `GET /auth/google`,
- xử lý callback tại `/auth/google/callback`,
- lưu thông tin user vào session,
- route `/me` trả thông tin user sau khi đăng nhập.

## Phần C — Câu hỏi vấn đáp
1. OAuth2 dùng để làm gì?
2. Vì sao không nên tự nhận mật khẩu Google của người dùng?
3. Access token khác gì refresh token?
4. Callback URL trong OAuth2 có vai trò gì?

