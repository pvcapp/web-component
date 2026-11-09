# Form Field

`PVCComponent.field` chọn kiểu hiển thị theo `style` (mặc định `field01`) và tạo field HTML. Hàm được export trực tiếp từ `src/index.js`.

## Cách gọi theo mã nguồn

```javascript
const fieldElement = PVCComponent.field({
    style: 'field01',
    type: 'email',
    id: 'email',
    caption: 'Email',
    value: '',
    placeholder: 'name@example.com',
    required: true
});

document.querySelector('#form-slot').appendChild(fieldElement);
```

## Tham số

| Tham số | Mặc định | Mô tả |
|---|---|---|
| `style` | `'field01'` | Biến thể giao diện; hiện chỉ có `field01` |
| `type` | `'text'` | Kiểu field |
| `id` | `''` | ID phần tử điều khiển |
| `value` | `''` | Giá trị ban đầu |
| `placeholder` | `''` | Gợi ý nhập liệu |
| `caption` | `''` | Nhãn |
| `required`, `readonly`, `hidden` | `false` | Trạng thái tương ứng |
| `inputmode`, `maxlength` | `''` | Thuộc tính nhập liệu |
| `options` | `{}` | Được chấp nhận nhưng không được sử dụng bởi `field01` |

Các kiểu được xử lý trong `field01`: `text`, `number`, `email`, `tel`, `textarea`, `hidden`, `dd/mm/yyyy`, `date`, `month`, `year`, `select`. Kiểu không nhận diện sẽ trở về input text.

## CSS

Biến thể dùng class `.field-01`. Xem [ví dụ giao diện Form](../../../examples/form/fields.html).
