# ĐỀ 54 — FILTER BẰNG QUERY STRING TRONG PHP

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```php
<?php
$keyword = $_GET["q"] ?? "";

$products = [
    ["id" => 1, "name" => "Laptop"],
    ["id" => 2, "name" => "Mouse"]
];

$result = array_filter($products, function ($product) use ($keyword) {
    return stripos($product["name"], $keyword) !== false;
});

header("Content-Type: application/json");
echo json_encode(array_values($result));
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `$_GET`, query string, `array_filter`, `stripos`, và `json_encode`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- thêm filter `category` và `page`,
- validate `page` là số dương,
- giới hạn số sản phẩm mỗi trang,
- trả thông tin `total`, `page`, và danh sách `items`.

## Phần C — Câu hỏi vấn đáp
1. Query string dùng để làm gì?
2. Vì sao cần validate dữ liệu từ `$_GET`?
3. Pagination giúp API như thế nào?
4. Khi filter từ database cần tránh lỗi SQL injection thế nào?

