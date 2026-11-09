# PVC Component

Thư viện UI Component viết bằng JavaScript thuần (Vanilla JavaScript), hỗ trợ xây dựng giao diện web theo hướng module hóa và tái sử dụng.

## 1. Giới thiệu

PVC Component cung cấp các thành phần giao diện có thể sử dụng trong nhiều dự án HTML, CSS và JavaScript.

**Đặc điểm:**
- Vanilla JavaScript, không phụ thuộc React hoặc Vue.
- Component được tổ chức theo module độc lập.
- CSS được đóng gói riêng.
- Hỗ trợ nhiều kiểu giao diện cho cùng một component.
- Có thể mở rộng và tùy chỉnh.
- Hỗ trợ build thành một bộ thư viện dùng chung.

## 2. Danh sách Component

| Nhóm | Mô tả | Tài liệu |
|---|---|---|
| Button | Các loại nút bấm | [Button](docs/form/button/index.md) |
| Form | Form, field, date picker | [Form](docs/form/index.md) |
| Alert | Hộp thoại thông báo/xác nhận | [Alert](docs/alert/index.md) |
| Dashboard | Card, desk card và table | [Dashboard](docs/dashboard/index.md) |
| Loading | Loading bar, screen và text | [Loading](docs/loading/index.md) |
| Toast | Thông báo ngắn | [Toast](docs/toast/index.md) |
| Tiện ích | Màn che và chat line | [Tiện ích](docs/utilities/index.md) |

## 3. Cài đặt và sử dụng

### 3.1. Nhúng thư viện

Build thư viện bằng `npm run build`, sau đó nạp bundle:

```html
<link rel="stylesheet" href="dist/pvc-component.css">
<script src="dist/pvc-component.js"></script>
```

### 3.2. Khởi tạo component

Ví dụ tạo Button:

```javascript
const btn = PVCComponent.Button.button({
    type: 'button01',
    id: 'btnThem',
    iconSrc: 'img/add.svg',
    text: 'Thêm mới',
    onColor: true,
    onclick: () => {
        console.log('Button clicked');
    }
});

document.body.appendChild(btn);
```

## 4. Cấu trúc thư viện

```text
component/
├── src/           # Mã nguồn
├── docs/          # Tài liệu hướng dẫn
├── examples/      # Ví dụ sử dụng
├── dist/          # Thư viện sau khi build
├── README.md
├── package.json
└── vite.config.js
```

## 5. Phát triển và Build

```sh
npm install
npm run build
```

Kết quả được xuất vào thư mục `dist/`.

Entry point hiện export Button, `canhBao` và `datePicker`. Các nhóm khác có tài liệu và trang xem trước nhưng chưa thể gọi qua bundle cho đến khi được export/tích hợp.

## 6. Tài liệu chi tiết

- [Toàn bộ tài liệu](docs/index.md)
- [Các ví dụ HTML](examples/index.html)

## 7. Quy ước phát triển

- Mỗi component có thư mục riêng.
- Mỗi component có file logic và CSS riêng.
- Sử dụng ES Modules (`import/export`).
- Component cần được export thông qua module nhóm trước khi dùng từ bundle.
- Tên class CSS cần có tiền tố `pvc-` hoặc namespace riêng để tránh xung đột với ứng dụng sử dụng thư viện.

## 8. Phiên bản

- Version: 1.0.0
- Build tool: Vite
- Language: JavaScript
- UI: Vanilla JavaScript
