# Tiện ích

Màn che `divChe` được export từ `src/index.js`. `chat_line` nằm trong `src/ai/` nhưng chưa được export.

## Màn che (`divChe`)

`PVCComponent.divChe({ id, zIndex })` thêm một phần tử `.div-che` vào trang. ID mặc định là `divChe`, z-index mặc định là `100`.

```javascript
PVCComponent.divChe({ id: 'page-overlay' });
document.querySelector('#page-overlay').style.display = 'block';
```

Xem [tài liệu divChe](divChe/index.md) để biết đầy đủ tham số và cách sử dụng, hoặc mở [divChe demo](../../examples/divChe.html).

## Chat line

`chat_line(chatData, divId, speed)` trong mã nguồn lần lượt hiển thị chuỗi trong mảng, mỗi dòng cách nhau `speed` mili giây (mặc định `2000`). Hàm này chưa thể gọi qua bundle vì chưa được export.

```javascript
chat_line(
    ['Xin chào!', 'Bạn cần hỗ trợ gì?', 'Tôi sẵn sàng trợ giúp.'],
    'chat-message',
    1500
);
```

Nếu bỏ `divId`, hàm gọi helper `toast(...)` toàn cục cho từng dòng. Khi có `divId`, phần tử đích phải tồn tại và helper `$` cần được cung cấp.

Xem [Utilities demo](../../examples/utilities.html) để xem trước chat line; trang demo dùng markup và JavaScript độc lập.
