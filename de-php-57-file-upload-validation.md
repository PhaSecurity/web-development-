# ĐỀ 57 — UPLOAD FILE VÀ VALIDATION TRONG PHP

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```php
<?php
if ($_SERVER["REQUEST_METHOD"] === "POST") {
    $avatar = $_FILES["avatar"];

    move_uploaded_file(
        $avatar["tmp_name"],
        "uploads/" . $avatar["name"]
    );

    header("Content-Type: application/json");
    echo json_encode([
        "filename" => $avatar["name"]
    ]);
}
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `$_FILES`, field `avatar`, `tmp_name`, `move_uploaded_file`, và thư mục `uploads`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- kiểm tra request phải là `POST`,
- trả lỗi nếu thiếu file hoặc upload lỗi,
- chỉ cho phép upload ảnh `.png`, `.jpg`, `.jpeg`,
- kiểm tra MIME type bằng `finfo_file`,
- giới hạn dung lượng file tối đa 2MB,
- đổi tên file tránh trùng và tránh dùng trực tiếp tên file người dùng gửi lên,
- trả JSON kèm HTTP status phù hợp khi file không hợp lệ.

## Phần C — Câu hỏi vấn đáp
1. `multipart/form-data` dùng để làm gì?
2. Vì sao không nên tin tưởng `$_FILES["avatar"]["type"]`?
3. Rủi ro khi lưu file upload bằng tên gốc của người dùng là gì?
4. Vì sao cần giới hạn dung lượng file upload?
5. Khi public thư mục upload cần cấu hình gì để tránh thực thi file nguy hiểm?

