# ĐỀ 44 — FORM SUBMIT BẰNG SPRING BOOT

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```java
@RestController
public class ContactController {
    record ContactRequest(String email) {}

    @PostMapping("/contact")
    public Map<String, String> contact(@RequestBody ContactRequest request) {
        return Map.of("email", request.email());
    }
}
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `@RestController`, `@PostMapping`, `@RequestBody`, record, và JSON response.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- validate email không được rỗng,
- trả `400 Bad Request` nếu dữ liệu không hợp lệ,
- thêm frontend dùng `fetch` gửi form,
- hiển thị loading và lỗi ở phía client.

## Phần C — Câu hỏi vấn đáp
1. Spring Boot map JSON body vào object như thế nào?
2. `@RestController` khác gì với `@Controller`?
3. Vì sao API cần status code rõ ràng?
4. Client-side validation có thay thế server-side validation được không?

