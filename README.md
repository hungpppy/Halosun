# HALOSUN – Khái toán điện mặt trời (bản web)

Trang web tĩnh, chạy được trên GitHub Pages. Không cần server.

## Gồm
- `index.html` – trang chính (tính toán bằng JavaScript thuần, giao diện làm đẹp bằng CSS).
- `react-ui.js` – lớp giao diện React đã đóng gói sẵn (thẻ số liệu, biểu đồ, gợi ý). **Phải để cùng thư mục với `index.html`.**
- `favicon.png`, `apple-touch-icon.png` – biểu tượng tab trình duyệt và biểu tượng khi lưu về màn hình điện thoại (biểu tượng tab đã nhúng sẵn trong `index.html`; `apple-touch-icon.png` cần để cùng thư mục).
- `src/ui.jsx` – mã nguồn React (chỉ cần khi muốn sửa giao diện React).

> Nếu thiếu `react-ui.js`, trang vẫn hiện thẻ số liệu và gợi ý (không có biểu đồ) kèm dòng báo lỗi màu đỏ.

## Đưa lên GitHub Pages
1. Tải các file `index.html`, `react-ui.js`, `apple-touch-icon.png`, `favicon.png` lên repo (thư mục gốc).
2. Settings → Pages → Branch `main` / root → Save.

## Sửa giá, hotline, logo
Mở `index.html`, tìm `const CFG=` và các bảng `PVTECH`, `INVT`, `BATT`, `TOU`, `FLAT`, `ROOF`, `P`.

## Dựng lại react-ui.js sau khi sửa src/ui.jsx
```
npm i react react-dom esbuild
npx esbuild src/ui.jsx --bundle --minify --format=iife --jsx=automatic --define:process.env.NODE_ENV='"production"' --outfile=react-ui.js
```
