# ĐỀ 41 — RENDER DANH SÁCH SẢN PHẨM BẰNG EXPRESS

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const express = require("express");
const app = express();

async function getProducts() {
    const res = await fetch("https://api.example.com/products");
    return res.json();
}

app.get("/products", async (req, res) => {
    const products = await getProducts();

    res.send(`
        <main>
            <h1>Products</h1>
            ${products.map(p => `<p>${p.name}</p>`).join("")}
        </main>
    `);
});

app.listen(3000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của Express route, `fetch`, async handler, `res.send`, và render HTML.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- xử lý lỗi khi API trả lỗi,
- hiển thị thông báo khi danh sách rỗng,
- thêm link tới trang chi tiết `/products/:id`,
- escape dữ liệu trước khi render ra HTML.

## Phần C — Câu hỏi vấn đáp
1. Server-side rendering bằng Express là gì?
2. Vì sao cần xử lý lỗi khi gọi API ngoài?
3. Vì sao dữ liệu render vào HTML cần escape?
4. Khi nào nên trả HTML thay vì JSON?

