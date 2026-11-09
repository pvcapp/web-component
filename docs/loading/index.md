# Loading

Nhóm Loading gồm `loadingBar`, `loadingScreen` và `loadingText`, được export từ `src/index.js`. Một số thành phần phụ thuộc helper toàn cục `div`.

## Loading text

`PVCComponent.loadingText({ id, text, type })` chọn `loadingText01` hoặc `loadingText02`. Mặc định text là “Đang xử lý”, type là `01`.

```javascript
const indicator = PVCComponent.loadingText({
    id: 'saving-state',
    text: 'Đang lưu dữ liệu',
    type: 'loadingText02'
});
```

## Loading screen

`PVCComponent.loadingScreen(message, id, type)` hỗ trợ `type: '01'` hoặc `'02'` (mặc định `'02'`).

```javascript
const screen = PVCComponent.loadingScreen('Đang tải dữ liệu', 'page-loading', '02');
document.body.appendChild(screen);
```

Loại `01` cần loading bar. Loại `02` có thông điệp mặc định “Dữ liệu của bạn đang được tải lên”.

## Loading bar

`PVCComponent.loadingBar(id, type)` tạo loading bar; hiện tại hàm dùng helper `div` chưa được định nghĩa trong module.

## CSS

Stylesheet nằm tại `src/loading/loadingBar/loadingBar01/`, `src/loading/loadingScreen/loadingScreen01/`, `src/loading/loadingScreen/loadingScreen02/`, `src/loading/loadingText/loadingText01/` và `src/loading/loadingText/loadingText02/`. Xem [Loading demo](../../examples/loading/index.html) để xem trước các trạng thái.
