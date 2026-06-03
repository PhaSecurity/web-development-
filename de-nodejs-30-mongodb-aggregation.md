# ĐỀ 30 — THỐNG KÊ DỮ LIỆU BẰNG MONGODB AGGREGATION

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const mongoose = require("mongoose");

const Order = mongoose.model("Order", new mongoose.Schema({
    userId: String,
    total: Number,
    status: String,
    createdAt: Date
}));

async function getRevenueByStatus() {
    return Order.aggregate([
        { $match: { status: "paid" } },
        { $group: { _id: "$status", revenue: { $sum: "$total" } } }
    ]);
}
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `aggregate`, `$match`, `$group`, `$sum`, và `_id`.

## Phần B — Sửa hoặc viết bổ sung
Sửa hàm để:
- thống kê doanh thu theo từng ngày,
- chỉ lấy đơn hàng trong 30 ngày gần nhất,
- sắp xếp theo ngày tăng dần,
- trả thêm số lượng đơn hàng đã thanh toán mỗi ngày.

## Phần C — Câu hỏi vấn đáp
1. Aggregation trong MongoDB dùng để làm gì?
2. `$match` nên đặt trước hay sau `$group`, vì sao?
3. Khi nào dùng aggregation thay vì `find()`?
4. Index ảnh hưởng thế nào đến truy vấn thống kê?

