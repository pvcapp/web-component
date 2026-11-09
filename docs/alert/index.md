# Alert

Alert tạo hộp thoại thông báo hoặc xác nhận. Hàm `canhBao` được export trực tiếp từ entry point.

## Khởi tạo và gọi

Lần gọi `canhBao` đầu tiên tự tạo hộp thoại; các lần sau tái sử dụng hộp thoại đó.

```javascript
const accepted = await PVCComponent.canhBao(
    'Bạn có muốn tiếp tục?',
    'Xác nhận',
    'okCancel'
);

if (accepted) {
    console.log('Người dùng chọn OK');
}
```

## Tham số và kết quả

| Tham số | Mặc định | Mô tả |
|---|---|---|
| `noiDung` | `''` | Nội dung thông báo |
| `caption` | `'Thông báo'` | Tiêu đề; giá trị rỗng cũng hiển thị “Thông báo” |
| `hinhThucXacThuc` | `'ok'` | `'ok'` hiển thị nút OK; giá trị khác hiển thị OK và Bỏ qua |

`PVCComponent.canhBao(...)` trả về Promise: `true` khi bấm OK và `false` khi bấm Bỏ qua.

## CSS và ví dụ

Stylesheet: `src/alert/style.css`. Xem [Alert demo](../../examples/alert.html). Trang demo dùng markup độc lập.

`canhBao` dùng helper `$` toàn cục để tìm phần tử được tạo lúc khởi tạo; cần cung cấp helper này khi tích hợp trực tiếp mã nguồn.

## Lưu ý

Triển khai hiện tại cập nhật nội dung bằng `innerHTML`. Chỉ truyền HTML tin cậy; không đưa nội dung do người dùng cung cấp trực tiếp vào `noiDung`.