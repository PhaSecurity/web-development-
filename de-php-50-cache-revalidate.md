# ĐỀ 50 — CACHE DỮ LIỆU TRONG PHP

## Phần A — Đọc và giải thích code
Cho đoạn mã Laravel sau:

```php
Route::get("/news", function () {
    $news = Cache::remember("news", 60, function () {
        return Http::get("https://api.example.com/news")->json();
    });

    return response()->json($news);
});
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `Cache::remember`, key `news`, thời gian 60 giây, và HTTP client.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- xử lý lỗi khi API bên ngoài thất bại,
- thêm route xóa cache `DELETE /news/cache`,
- thêm trường hợp không cache cho dữ liệu realtime,
- giải thích khi nào nên cache và khi nào không.

## Phần C — Câu hỏi vấn đáp
1. Cache giúp gì cho backend?
2. Cache key là gì?
3. Dữ liệu nào không nên cache lâu?
4. Khi nào cần xóa hoặc làm mới cache?

