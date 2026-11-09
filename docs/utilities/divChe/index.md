# divChe

`PVCComponent.divChe` tạo và gắn một phần tử phủ toàn màn hình vào `document.body`. Component được export từ `src/index.js`; CSS của `.div-che` được đóng gói cùng bundle.

## Khởi tạo

```javascript
PVCComponent.divChe({
    id: 'page-overlay',
    zIndex: 100
});
```

| Tham số | Mặc định | Mô tả |
|---|---|---|
| `id` | `'divChe'` | ID của phần tử overlay |
| `zIndex` | `100` | Thứ tự xếp lớp CSS |

Hàm tự thêm phần tử vào `document.body` và không trả về phần tử đó. Sau khi tạo, truy cập overlay bằng ID để bật/tắt:

```javascript
const overlay = document.getElementById('page-overlay');
overlay.style.display = 'block';
overlay.style.display = 'none';
```

Overlay ban đầu được ẩn (`display: none`) và có nền đen trong suốt. Để hiển thị nội dung bên trên lớp phủ, thêm phần tử con vào overlay và tự định kiểu cho nội dung đó. Chỉ khởi tạo một lần cho mỗi ID.

## Ví dụ

Mở [divChe demo](../../../examples/divChe.html) để xem cách tạo, hiển thị và đóng overlay. Trang demo nạp bundle từ `dist/`; chạy `npm run build` trước nếu bundle chưa được tạo.
