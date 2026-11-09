# Button 01

<text>**Tên:** button01</text>

Button cơ bản gồm icon và text, hỗ trợ màu nền tùy chọn, hiệu ứng hover, active và sự kiện click.

## 1. Xem trước

Mô tả giao diện:

- Icon nằm bên trái.
- Text nằm bên phải.
- Có thể bật nền màu bằng `onColor`.
- Có hiệu ứng khi hover và active.

## 2. Cách sử dụng

```javascript
const btn = PVCComponent.button({
    type: 'button01',
    id: 'btnThem',
    iconSrc: 'img/add.svg',
    text: 'Khách hàng mới',
    onColor: true,
    onclick: () => {
        console.log('Đã nhấn button');
    }
});

document.body.appendChild(btn);
```

## 3. API Parameters

| Thuộc tính | Kiểu dữ liệu | Mặc định | Bắt buộc |
|---|---|---|---|
| id | String | '' | Không |
| iconSrc | String | '' | Không |
| text | String | '' | Không |
| onclick | Function | null | Không |
| onColor | Boolean | false | Không |

### Chi tiết thuộc tính

**id**

ID của phần tử HTML được tạo ra.

```javascript
id: 'btnThem'
```

**iconSrc**

Đường dẫn đến file icon.

```javascript
iconSrc: 'img/add.svg'
```

Nếu để trống, button không hiển thị icon.

**text**

Nội dung hiển thị trên button.

```javascript
text: 'Thêm mới'
```

Nếu để trống, button không hiển thị text.

**onclick**

Hàm được thực thi khi người dùng nhấn button.

```javascript
onclick: () => {
    console.log('Clicked');
}
```

**onColor**

Bật hoặc tắt kiểu nền màu.

```javascript
onColor: true
```

Mặc định: `false`.

## 4. CSS Classes

| Class | Mô tả |
|---|---|
| button01 | Class chính |
| button01__icon | Icon |
| button01__text | Text |
| on-color-background | Nền màu |

## 5. Cấu trúc HTML được tạo

```html
<div class="button01 on-color-background" id="btnThem">
    <img class="button01__icon" src="img/add.svg">
    <span class="button01__text">Khách hàng mới</span>
</div>
```

## 6. Ví dụ sử dụng

### Button có icon và text

```javascript
PVCComponent.button({
    type: 'button01',
    iconSrc: 'img/add.svg',
    text: 'Thêm mới'
});
```

### Button chỉ có text

```javascript
PVCComponent.button({
    type: 'button01',
    text: 'Lưu'
});
```

### Button trắng trên nền màu

```javascript
PVCComponent.button({
   type: 'button01',
   text: 'Xác nhận',
   onColor: true
});
```

## 7. Accessibility

Biến thể hiện tại tạo phần tử `<div>` thay vì `<button>`, do đó không có hành vi bàn phím hoặc ngữ nghĩa button mặc định. Với giao diện cần accessibility đầy đủ, nên bổ sung `role`, `tabindex` và xử lý phím hoặc dùng phần tử `<button>` trong lần cải tiến component.

## 8. Dependencies

- JavaScript: Không có thư viện bên ngoài.
- CSS: `src/form/button/button01/style.css`.
- Assets: Icon SVG do ứng dụng cung cấp.

## 9. Phiên bản

- Version: 1.0.0
- Status: Stable
