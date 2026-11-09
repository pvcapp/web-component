# Toast

Toast hiển thị thông báo ngắn có thể tự ẩn hoặc đóng khi nhấn. `toast` và `hideToast` được export trực tiếp từ `src/index.js`.

## Khởi tạo và sử dụng

```javascript
PVCComponent.toast('Đã lưu dữ liệu', 3000, 'infor');
```

`PVCComponent.toast(noiDung, thoiGian, status)` tự tạo container khi cần và hiển thị thông báo; thời gian tính bằng mili giây, mặc định `3000`, trạng thái mặc định `'infor'`. `PVCComponent.hideToast()` đóng thông báo ngay.

## Tích hợp

`toast_init()` đọc `APP.config.showIcon` và `APP.config.publicUrl`; ứng dụng cần cung cấp `APP.config` nếu muốn khởi tạo theo cấu hình này. Các hàm cũng dùng helper `$` toàn cục. Không gọi `toast_init()` nhiều lần vì mỗi lần sẽ thêm một container mới.

Nội dung được gán bằng `innerHTML`; chỉ truyền HTML tin cậy. Stylesheet: `src/toast/style.css`.
Mã CSS hiện định nghĩa trạng thái `toast-infor`; các trạng thái khác cần stylesheet tương ứng để có giao diện riêng.

Xem [Toast demo](../../examples/toast.html); đây là bản xem trước độc lập bằng HTML/CSS.
