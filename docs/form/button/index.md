# Button Components

Các component thuộc nhóm Button dùng để tạo các nút tương tác trong giao diện.

## 1. Danh sách Button

| Component | Mô tả | Tài liệu |
|---|---|---|
| button01 | Button có icon và text | [Chi tiết](button_01/index.md) |
| onlyIconButton01 | Phần tử ảnh có thể click, chỉ hiển thị icon | Được chọn bằng `type: 'onlyIconButton01'` |

## 2. Cách sử dụng chung

```javascript
const btn = PVCComponent.button({
    type: 'button01',
    text: 'Thêm mới',
    iconSrc: 'img/add.svg'
});

document.body.appendChild(btn);
```

## 3. Các thuộc tính chung

| Thuộc tính | Kiểu dữ liệu | Mặc định | Mô tả |
|---|---|---|---|
| type | String | button01 | Loại Button |
| id | String | '' | ID phần tử |
| iconSrc | String | '' | Đường dẫn icon |
| text | String | '' | Nội dung |
| onclick | Function | null | Sự kiện click |
| onColor | Boolean | false | Sử dụng nền màu |

Lưu ý: Các thuộc tính thực sự được hỗ trợ có thể khác nhau tùy từng loại Button.

## 4. Button chỉ có icon

```javascript
const iconButton = PVCComponent.button({
    type: 'onlyIconButton01',
    id: 'edit-action',
    iconSrc: 'img/edit.svg',
    onclick: () => console.log('Edit')
});
```

Nút icon nhận `id`, `iconSrc` và `onclick`; `text` và `onColor` chỉ áp dụng cho `button01`. Phần tử trả về là `<img>`, không phải `<button>` semantic.

## 5. Tài liệu từng Button

- [Button 01](button_01/index.md)
- [Ví dụ Button 01](../../../examples/form/button/button_01.html)

Các component Button được export trực tiếp từ `src/index.js` dưới dạng `PVCComponent.button(...)`.
