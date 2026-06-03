# ĐỀ 39 — CHẠY NODE.JS VỚI DOCKER COMPOSE

## Phần A — Đọc và giải thích code
Cho file `docker-compose.yml` sau:

```yaml
services:
  api:
    build: .
    ports:
      - "3000:3000"
    environment:
      DB_HOST: db
  db:
    image: mysql:8
    environment:
      MYSQL_ROOT_PASSWORD: root
      MYSQL_DATABASE: app
```

### Yêu cầu
- Giải thích file compose đang làm gì.
- Giải thích vai trò của `services`, `build`, `ports`, `environment`, và hostname `db`.

## Phần B — Sửa hoặc viết bổ sung
Sửa compose để:
- thêm volume lưu dữ liệu MySQL,
- thêm biến `DB_USER`, `DB_PASSWORD`, `DB_NAME` cho service API,
- chỉ expose database trong network nội bộ,
- thêm `depends_on` cho API.

## Phần C — Câu hỏi vấn đáp
1. Docker Compose dùng để làm gì?
2. Container khác gì với image?
3. Vì sao API có thể kết nối database qua host `db`?
4. Volume trong Docker dùng để làm gì?

