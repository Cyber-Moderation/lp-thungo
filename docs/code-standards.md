# Code Standards - TRACE Project

Tài liệu này quy định các tiêu chuẩn lập trình và cấu trúc mã nguồn cho dự án TRACE.

## 1. Cấu trúc Tệp tin
Dự án tuân thủ mô hình **Single File Component**, toàn bộ mã nguồn nằm trong tệp `index.html`.
- `<head>`: Chứa meta tags, title và các định nghĩa SEO.
- `<style>`: Chứa toàn bộ CSS.
- `<body>`: Chứa cấu trúc HTML semantic.
- `<script>`: Chứa logic JavaScript (nếu có).

## 2. Tiêu chuẩn CSS
### Quy tắc đặt tên biến (CSS Variables)
Sử dụng tiền tố `--color-`, `--font-`, `--space-`, `--container-` để phân loại biến.
Ví dụ:
- `--color-background`
- `--space-md`

### Mobile-first Approach
- CSS mặc định được viết cho Mobile.
- Sử dụng Media Queries (`min-width`) để ghi đè (override) style cho các màn hình lớn hơn.
- Ngưỡng thiết bị (Breakpoints):
    - Tablet: `768px`
    - Desktop: `1024px`

### Đơn vị và Kích thước
- Sử dụng `clamp()` cho typography để có fluid scaling.
- Sử dụng hệ thống spacing dựa trên cơ sở 8px.

## 3. Tiêu chuẩn HTML
- Sử dụng các thẻ semantic: `<header>`, `<main>`, `<section>`, `<article>`, `<footer>`.
- Toàn bộ nội dung văn bản phải hỗ trợ tiếng Việt (UTF-8).

## 4. Nguyên tắc Phát triển
- **Zero External Dependencies**: Tuyệt đối không nhúng các thư viện bên ngoài.
- **Inline Strategy**: Mọi thứ phải nằm trong một file duy nhất để đảm bảo tính độc lập.

---
*Cập nhật lần cuối: 2025-12-23*
