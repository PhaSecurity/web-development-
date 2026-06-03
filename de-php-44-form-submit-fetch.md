# ĐỀ 44 — FORM SUBMIT BẰNG FETCH TRONG PHP

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```php
<?php
// contact.php
$data = json_decode(file_get_contents("php://input"), true);

if ($_SERVER["REQUEST_METHOD"] === "POST") {
    echo json_encode([
        "email" => $data["email"] ?? null
    ]);
}
```

```html
<form id="contactForm">
    <input id="email" />
    <button type="submit">Send</button>
</form>

<script>
document.getElementById("contactForm").addEventListener("submit", async e => {
    e.preventDefault();
    const email = document.getElementById("email").value;

    await fetch("/contact.php", {
        method: "POST",
        body: JSON.stringify({ email })
    });
});
</script>
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `php://input`, `json_decode`, `fetch`, `preventDefault`, và JSON body.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- validate email không được rỗng,
- trả `400` nếu email không hợp lệ,
- thêm header `Content-Type: application/json`,
- hiển thị loading và lỗi ở phía client.

## Phần C — Câu hỏi vấn đáp
1. Vì sao form submit mặc định reload trang?
2. `php://input` dùng để làm gì?
3. Vì sao API cần trả đúng status code?
4. Khi nào nên validate ở cả client và server?

