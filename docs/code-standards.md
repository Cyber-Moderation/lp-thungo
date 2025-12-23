# Code Standards - TRACE Project

Tài liệu này quy định các tiêu chuẩn lập trình và cấu trúc mã nguồn cho dự án TRACE (Dấu Vết).

## 1. Cấu trúc Tệp tin (SFA)
Dự án tuân thủ mô hình **Single File Architecture**, toàn bộ mã nguồn nằm trong tệp `index.html`.
- `<head>`: Chứa meta tags, title, SEO và JSON-LD.
- `<style>`: Chứa toàn bộ CSS (Design Tokens, Base, Layout, Components, Animations).
- `<body>`: Chứa cấu trúc HTML5 semantic.
- `<script>`: Chứa logic JavaScript Vanilla ở cuối file.

## 2. Tiêu chuẩn CSS
### Quy tắc đặt tên biến (CSS Variables)
Sử dụng hệ thống Design Tokens để quản lý giao diện:
- `--color-*`: Định nghĩa bảng màu (ví dụ: `--color-background`, `--color-accent-green`).
- `--font-*`: Định nghĩa font-family.
- `--space-*`: Hệ thống thang đo spacing (8px base).
- `--container-*`: Các biến cấu trúc layout.

### Mobile-first Approach
- CSS mặc định được viết cho Mobile.
- Sử dụng Media Queries (`min-width`) để mở rộng cho màn hình lớn.
- Breakpoints: `768px` (Tablet) và `1024px` (Desktop).

### Typography & Layout
- Sử dụng `clamp()` cho font-size để tạo fluid typography.
- Sử dụng Flexbox cho các component đơn giản và Grid cho các layout phức tạp (About Grid).
- Độ tương phản màu sắc phải đạt chuẩn WCAG AAA (≥13.5:1).

## 3. Tiêu chuẩn HTML
- Sử dụng thẻ semantic đúng mục đích: `<main>`, `<header>`, `<section>`, `<footer>`.
- Hình ảnh/Logo: Ưu tiên sử dụng Inline SVG (Data URI) để giảm HTTP requests.
- Ngôn ngữ: `html lang="vi"`, mã hóa `UTF-8`.

## 4. Tiêu chuẩn JavaScript
- **Vanilla JS**: Không sử dụng framework hay thư viện (No jQuery).
- **Performance**: Sử dụng `Intersection Observer` thay vì lắng nghe sự kiện `scroll` trực tiếp để tối ưu hiệu suất.
- **Accessibility**: Tôn trọng thiết lập `prefers-reduced-motion` của người dùng.

## 5. Nguyên tắc Phát triển
- **YAGNI**: Chỉ cài đặt những gì thực sự cần thiết.
- **Zero External Dependencies**: Tuyệt đối không nhúng tài nguyên bên ngoài để đảm bảo tính sẵn sàng và tốc độ.
- **Single Source of Truth**: Mọi thứ phải nằm trong `index.html`.

---
*Cập nhật lần cuối: 2025-12-23*
