# Tài liệu PVC Component

Thư viện cung cấp các thành phần giao diện viết bằng JavaScript thuần. Tài liệu dưới đây được đối chiếu với mã nguồn hiện có trong `src/`.

## Danh mục

| Nhóm | Thành phần | Tài liệu | Ví dụ |
|---|---|---|---|
| Button | `button01`, `onlyIconButton01` | [Button](form/button/index.md), [Button 01](form/button/button_01/index.md) | [Button demo](../examples/form/button/index.html) |
| Form | Field, date picker và reset form | [Form](form/index.md), [Form field](form/formField/index.md), [Date picker](form/date-picker/index.md) | [Form demo](../examples/form/fields.html) |
| Alert | Hộp thoại xác nhận/thông báo | [Alert](alert/index.md) | [Alert demo](../examples/alert.html) |
| Dashboard | Card, desk card, table, layout helpers | [Dashboard](dashboard/index.md) | [Dashboard demo](../examples/dashboard/index.html) |
| Loading | Loading bar, screen, text | [Loading](loading/index.md) | [Loading demo](../examples/loading/index.html) |
| Toast | Thông báo ngắn | [Toast](toast/index.md) | [Toast demo](../examples/toast.html) |
| Tiện ích | Màn che và chat line | [Tiện ích](utilities/index.md) | [Utilities demo](../examples/utilities.html) |

## Phạm vi API hiện được export

Entry point `src/index.js` export `button`, `field`, namespace `datePicker`, `canhBao`, `toast`, `hideToast`, `divChe`, các hàm Loading và `card`/`card_container`. `buildForm`, `resetForm`, các thành phần Desk/Table và `chat_line` chưa được export. Những trang ví dụ là bản xem trước HTML/CSS độc lập, trừ trang Button và Form có dùng bundle.

## Build

Chạy `npm install`, sau đó `npm run build`. Vite tạo bundle trong `dist/`; trang Button demo cần bundle này. Các trang xem trước HTML khác tải trực tiếp CSS trong `src/`.
