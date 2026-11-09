# Date Picker

Date picker trong `src/form/datePicker/` là bộ chọn ngày dạng lịch tháng. API công khai được export từ entry point dưới namespace `PVCComponent.datePicker`.

## API

```javascript
PVCComponent.datePicker.init();
PVCComponent.datePicker.show('startDate', 'dd/mm/yyyy', 'Chọn ngày bắt đầu');
```

| Phương thức | Tham số | Mô tả |
|---|---|---|
| `init()` | Không | Tạo giao diện lịch một lần; gọi lại an toàn |
| `show(inputId, format, caption)` | ID input; format mặc định `'dd/mm/yyyy'`; caption mặc định `'Chọn ngày'` | Mở lịch cho input được chỉ định |

Các format được hỗ trợ nội bộ gồm `dd`, `mm`, `dd/mm`, `dd/mm/yyyy` và `mm/yyyy`.

## Dùng với input HTML

```javascript
const input = document.querySelector('#startDate');
input.addEventListener('click', () => {
    PVCComponent.datePicker.show(input.id, 'dd/mm/yyyy', 'Chọn ngày bắt đầu');
});
```

Không dùng inline handler gọi `PVC_Fns_CN` trực tiếp. `document.body` cần tồn tại trước khi gọi `init()` hoặc `show()`. Field `dd/mm/yyyy` trong module Form cũng kết nối tới API này.

## CSS và ví dụ

Stylesheet `src/form/datePicker/style.css` được import cùng module. Xem [Form demo](../../../examples/form/fields.html). API hiện export `init()` và `show()`; không có phương thức `hide()` công khai.