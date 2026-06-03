# ĐỀ 23 — LẬP LỊCH TÁC VỤ BẰNG NODE-CRON

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const cron = require("node-cron");

function cleanupExpiredSessions() {
    console.log("Cleaning expired sessions...");
}

cron.schedule("0 * * * *", () => {
    cleanupExpiredSessions();
});

console.log("Scheduler started");
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `node-cron`, biểu thức `"0 * * * *"`, và hàm `cleanupExpiredSessions`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- chạy tác vụ dọn session mỗi 30 phút,
- ghi log thời gian bắt đầu và kết thúc tác vụ,
- bắt lỗi nếu tác vụ thất bại,
- không cho tác vụ mới chạy nếu tác vụ trước đó chưa kết thúc.

## Phần C — Câu hỏi vấn đáp
1. Cron job là gì?
2. Biểu thức cron gồm những thành phần nào?
3. Vì sao cần tránh chạy chồng nhiều tác vụ giống nhau?
4. Những tác vụ nào trong backend thường được lập lịch?
