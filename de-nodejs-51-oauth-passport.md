# ĐỀ 51 — XÁC THỰC OAUTH VỚI PASSPORT

## Phần A — Đọc và giải thích code
Cho đoạn cấu hình sau:

```js
const passport = require("passport");
const GitHubStrategy = require("passport-github2").Strategy;

passport.use(new GitHubStrategy({
    clientID: process.env.GITHUB_ID,
    clientSecret: process.env.GITHUB_SECRET,
    callbackURL: "/auth/github/callback"
}, (accessToken, refreshToken, profile, done) => {
    done(null, { id: profile.id, username: profile.username });
}));
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của Passport, OAuth provider, `clientID`, `clientSecret`, `callbackURL`, và `done`.

## Phần B — Sửa hoặc viết bổ sung
Sửa hoặc viết thêm để:
- thêm callback lưu `role` vào session,
- bảo vệ route `/dashboard` chỉ cho user đã đăng nhập,
- thêm route sign in và logout,
- không để lộ secret trong client code.

## Phần C — Câu hỏi vấn đáp
1. OAuth dùng để làm gì?
2. Provider OAuth là gì?
3. Session sau OAuth lưu thông tin gì?
4. Vì sao secret phải nằm trong biến môi trường?

