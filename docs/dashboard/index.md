# Dashboard

Nhóm Dashboard có card, desk card, table và helper bố cục. `card`/`card_container` được export từ `src/index.js`; Desk, Table và các helper bố cục chưa được export.

## Card

`PVCComponent.card_container(data, id)` nhận danh sách phần tử theo dạng `{ type, data }`; các loại được dispatch là `detailCard01`, `numberCard01` và `numberCard02`.

```javascript
const cards = PVCComponent.card_container([
    {
        type: 'numberCard01',
        data: { caption: 'Đơn hàng', subCaption: 'Trong tháng', value: '128' }
    },
    {
        type: 'detailCard01',
        data: {
            caption: 'Tổng quan',
            subCaption: 'Cập nhật hôm nay',
            content: ['Nội dung thứ nhất', 'Nội dung thứ hai']
        }
    }
], 'overview-cards');
```

| Biến thể | Dữ liệu |
|---|---|
| `detailCard01` | `caption`, `subCaption`, `content` (mảng chuỗi) |
| `numberCard01` | `caption`, `subCaption`, `value` |
| `numberCard02` | `caption`, `subCaption`, `value`, `loaded`; khi `loaded: false` hiển thị loading text |

## Desk card

`deskCard_01` được thiết kế để nhận `caption`, `subCaption`, `detail`, `actionBar`; `desk_container` dự kiến nhận danh sách item có `type` và `data`.

> Lưu ý: triển khai `deskCard_01` hiện có tham chiếu biến `data` không được khai báo trong hàm; cần sửa lỗi này trước khi gọi API.

## Table

`table_01(columnList, data)` nhận danh sách cột có `caption` hoặc `name`, cùng danh sách hàng dạng mảng giá trị. `table(data)` là wrapper dự kiến nhận `{ columnList, data }`.

> Lưu ý: triển khai table hiện có lỗi tạo cell (`td` chưa được khai báo) và wrapper đang tham chiếu `container` chưa được khai báo. Đây là API chưa sẵn sàng sử dụng.

## Helpers và styles

- `row(options)` và `column(options)` bổ sung class tương ứng cho phần tử tạo bởi helper toàn cục `div`.
- `totalCard_render(title, value)` trả về chuỗi HTML.
- Stylesheet theo nhóm: `src/dashboard/style.css`, `src/dashboard/card/style.css`, `src/dashboard/desk/style.css`, `src/dashboard/table/style.css` và CSS của từng biến thể.
- Một số card dùng `innerHTML` cho caption/giá trị; chỉ truyền nội dung tin cậy.

Xem [Dashboard demo](../../examples/dashboard/index.html) để xem bố cục tĩnh. Demo không gọi các hàm Dashboard.
