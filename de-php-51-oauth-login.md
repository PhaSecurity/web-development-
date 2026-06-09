# ĐỀ 51 — XÁC THỰC OAUTH TRONG PHP

## Phần A — Đọc và giải thích code
Cho đoạn cấu hình Laravel Socialite sau:

```php
Route::get("/auth/github", function () {
    return Socialite::driver("github")->redirect();
});

Route::get("/auth/github/callback", function () {
    $githubUser = Socialite::driver("github")->user();

    session([
        "user" => [
            "id" => $githubUser->getId(),
            "email" => $githubUser->getEmail()
        ]
    ]);

    return redirect("/dashboard");
});
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của OAuth provider, redirect, callback, session, và Socialite.

## Phần B — Sửa hoặc viết bổ sung
Sửa hoặc viết thêm để:
- lưu thêm `role` vào session,
- bảo vệ route `/dashboard` bằng middleware đăng nhập,
- thêm route logout,
- không để lộ client secret trong code.

## Phần C — Câu hỏi vấn đáp
1. OAuth dùng để làm gì?
2. Vì sao không nên tự nhận mật khẩu GitHub của user?
3. Session sau OAuth dùng để làm gì?
4. Secret nên cấu hình ở đâu?

