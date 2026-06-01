# Phân tích link `womens-day-deargift`

## Tổng quan

- Trang gốc: `https://womens-day-deargift.vercel.app/index.html?50bbfaeb61587746`
- Loại trang: web quà tặng tương tác cho Women's Day, dựng bằng HTML/CSS/JavaScript tĩnh với Three.js/WebGL.
- Cấu trúc gốc: gần như toàn bộ CSS và JavaScript nằm trực tiếp trong `index.html`; dữ liệu cá nhân được tải qua API `https://api.deargift.online/api/womenday/50bbfaeb61587746`.

## Dữ liệu cấu hình của link

- `enablePasscode`: `false`, nên link thật không bắt nhập mật khẩu.
- `morphTexts`: `Chúc Mừng`, `Ngày Quốc Tế Phụ Nữ`, `8 Tháng 3`, `Lớp 10A1`.
- `particleImage`: 1 ảnh dùng để morph hạt.
- `sphereImages`: 10 ảnh dùng để tạo quả cầu ảnh 3D.
- `letter.text`: lời chúc Women's Day cho các bạn gái lớp 10A1.
- `letter.image`: ảnh tập thể trong lá thư.
- `letter.caption`: `Mãi iu 10A1`.
- `bgMusic`: `musics/noinaycoanh.mp3`.

## Luồng trải nghiệm

1. Màn loading nền đen tải tài nguyên.
2. Hiển thị màn WebGL hạt màu hồng và nút `Giữ để bắt đầu`.
3. Người dùng giữ nút khoảng 1 giây để kích hoạt nhạc và animation.
4. Hạt morph lần lượt thành chữ theo cấu hình.
5. Chuyển sang quả cầu ảnh 3D từ 10 ảnh cá nhân.
6. Click quả cầu lần 1 để zoom.
7. Click lần 2 để bung ảnh bay.
8. Click nút phong bì ở góc phải để chuyển sang sequence Cupid.
9. Cupid bay tới phong bì, click phong bì để mở lá thư.
10. Lá thư gõ chữ từng ký tự, hiển thị ảnh và caption.

## Clone đã dựng

- File chính: `index.html`.
- Đã mirror asset template từ Vercel vào `assets/`.
- Đã mirror ảnh cá nhân từ R2 vào `assets/uploads/`.
- Đã mirror nhạc nền vào `musics/noinaycoanh.mp3`.
- Đã bỏ phụ thuộc API DearGift bằng cách nhúng cấu hình trực tiếp vào HTML.
- Đã thay `detect-devtools.js` bằng no-op để clone không khóa DevTools khi debug.
- Đã chỉnh lại dữ liệu tiếng Việt bị mất dấu trong quá trình sinh file.
- Đã giữ CDN Three.js, Simplex Noise và Google Fonts như bản gốc để không thay đổi logic render WebGL.

## Kiểm tra

- Đã chạy qua HTTP local.
- Đã kiểm tra render màn đầu, morph chữ, quả cầu ảnh, bung ảnh, phong bì và lá thư.
- Không ghi nhận lỗi runtime hoặc request lỗi trong kiểm tra Playwright.
