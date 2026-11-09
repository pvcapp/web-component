# Form

Nhóm Form gồm field và date picker được export từ `src/index.js`, cùng helper dựng/reset form chưa được export trong entry point.

## Tạo field

`PVCComponent.field(...)` tạo một field; hàm được export trực tiếp từ `src/index.js`. `buildForm` là helper nội bộ, không được export; xem phần [helpers chỉ có trong mã nguồn](#helpers-chi-co-trong-ma-nguon).

```javascript
const fullName = PVCComponent.field({
    style: 'field01',
    id: 'fullName',
    type: 'text',
    caption: 'Họ và tên',
    placeholder: 'Nhập họ và tên',
    required: true
});
document.querySelector('#form-slot').appendChild(fullName);
```

## Helpers chỉ có trong mã nguồn

`buildForm(columnList)` trong `src/form/form01/` tạo `.form__grid`; hàm không được export từ bundle và cần các helper toàn cục `div` và `field`. Mỗi cột cần `name`; các cột có `show: false`, `0` hoặc `'0'` bị bỏ qua.

`resetForm(id)` xóa giá trị các `input`, `textarea`, `select` trong phần tử có ID tương ứng; checkbox và radio được bỏ chọn. Hàm này cũng không được export.

### Thuộc tính cột buildForm

| Thuộc tính | Mô tả |
|---|---|
| `name` | ID field; cột không có `name` sẽ bị bỏ qua |
| `type` | Loại input như `text`, `number`, `email`, `tel`, `textarea`, `hidden`, `date`, `month`, `year`, `select`, `dd/mm/yyyy` |
| `value` | Giá trị ban đầu |
| `caption` | Nhãn field |
| `require` | Chuyển thành thuộc tính `required` |
| `readonly` | Chuyển thành thuộc tính `readonly` |
| `placeholder`, `maxlength`, `hidden`, `inputmode` | Tùy chọn hiển thị/nhập liệu |
| `selectOptions` | Danh sách dự kiến cho field `select`; tích hợp hiện chưa chuyển tiếp thuộc tính này đúng cách |

## Giới hạn cần lưu ý

- Các helper dựng/reset form là API nội bộ; chúng không được export ở entry point.
- `field` được export trực tiếp dưới tên `PVCComponent.field`; xem [Form Field](formField/index.md).
- Một số kiểu field có kết nối tới date picker; xem [Date picker](date-picker/index.md).

## Ví dụ giao diện

[Mở trang xem trước Form](../../examples/form/fields.html). Field được dựng bằng markup HTML/CSS; date picker dùng API `PVCComponent.datePicker` đã export.

## CSS

Nhóm stylesheet: `src/form/form01/style.css` và `src/form/field/field01/style.css`.
