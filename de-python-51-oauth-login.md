# ĐỀ 51 — XÁC THỰC OAUTH TRONG PYTHON

## Phần A — Đọc và giải thích code
Cho đoạn mã FastAPI dùng Authlib sau:

```python
from authlib.integrations.starlette_client import OAuth

oauth = OAuth()
oauth.register(
    name="github",
    client_id="GITHUB_ID",
    client_secret="GITHUB_SECRET",
    access_token_url="https://github.com/login/oauth/access_token",
    authorize_url="https://github.com/login/oauth/authorize",
)
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của OAuth, provider GitHub, `client_id`, `client_secret`, authorize URL, và access token URL.

## Phần B — Sửa hoặc viết bổ sung
Viết thêm để:
- route `/auth/github` redirect sang GitHub,
- route callback nhận thông tin user,
- lưu user vào session,
- bảo vệ route `/dashboard` cho user đã đăng nhập.

## Phần C — Câu hỏi vấn đáp
1. OAuth provider là gì?
2. Access token dùng để làm gì?
3. Vì sao secret phải nằm trong biến môi trường?
4. Session sau đăng nhập OAuth có vai trò gì?

