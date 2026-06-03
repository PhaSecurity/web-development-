# ĐỀ 31 — LIÊN KẾT DỮ LIỆU VỚI MONGOOSE POPULATE

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const mongoose = require("mongoose");

const userSchema = new mongoose.Schema({ name: String });
const postSchema = new mongoose.Schema({
    title: String,
    author: { type: mongoose.Schema.Types.ObjectId, ref: "User" }
});

const User = mongoose.model("User", userSchema);
const Post = mongoose.model("Post", postSchema);

async function getPosts() {
    return Post.find().populate("author");
}
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `ObjectId`, `ref`, và `populate("author")`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- chỉ populate trường `name` của author,
- thêm route `GET /posts/:id` trả bài viết kèm author,
- trả `404` nếu không tìm thấy bài viết,
- kiểm tra `id` có đúng ObjectId trước khi query.

## Phần C — Câu hỏi vấn đáp
1. `populate` giải quyết vấn đề gì?
2. MongoDB có join giống SQL không?
3. Khi nào không nên lạm dụng `populate`?
4. `ObjectId` khác gì với string thông thường?

