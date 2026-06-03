# ĐỀ 50 — CACHE DỮ LIỆU TRONG SPRING BOOT

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```java
@Service
public class NewsService {
    @Cacheable("news")
    public List<News> getNews() {
        return restClient.get()
            .uri("https://api.example.com/news")
            .retrieve()
            .body(new ParameterizedTypeReference<>() {});
    }
}
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `@Cacheable`, cache name `news`, service layer, và HTTP client.

## Phần B — Sửa hoặc viết bổ sung
Sửa hoặc viết thêm để:
- thêm `@CacheEvict` để xóa cache,
- xử lý lỗi API bên ngoài,
- cấu hình TTL cache,
- nêu khi nào không nên cache dữ liệu.

## Phần C — Câu hỏi vấn đáp
1. Cache giúp cải thiện hiệu năng thế nào?
2. `@Cacheable` hoạt động ra sao?
3. Cache eviction là gì?
4. Vì sao dữ liệu realtime không nên cache lâu?

