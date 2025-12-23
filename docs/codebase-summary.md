# Codebase Summary - TRACE Project

Tóm tắt cấu trúc và nội dung mã nguồn của dự án TRACE (Dấu Vết).

## 1. Thành phần Chính
| Tệp tin | Kích thước | Chức năng |
| :--- | :--- | :--- |
| `index.html` | 20.16KB | Tệp duy nhất chứa toàn bộ HTML/CSS/JS (Single File Architecture) |
| `assets/` | ~480KB | Chứa các tài sản hình ảnh UI và tham khảo |
| `docs/` | - | Tài liệu kỹ thuật và hướng dẫn dự án |

## 2. Chi tiết Triển khai (SFA)

### HTML Structure
- **Semantic HTML5**: Sử dụng `<header>`, `<main>`, `<section>`, `<article>`, `<footer>`.
- **SEO Ready**: Đầy đủ Meta Tags (Primary, OG, Twitter) và JSON-LD Event Schema.
- **Accessibility**: Đạt chuẩn WCAG AAA với độ tương phản màu sắc cao (≥13.5:1).

### CSS (Design Tokens & Layout)
- **Bảng màu (Eco-Aesthetic)**:
  - `--color-background`: `#EBE5D9` (Beige ấm)
  - `--color-accent-green`: `#4A7C59` (Xanh lá mềm)
  - `--color-text-primary`: `#1A1A1A`
- **Typography**: Sử dụng font Serif hệ thống (`Times New Roman`, `Georgia`), hỗ trợ fluid scaling bằng `clamp()`.
- **Responsive**: Mobile-first với breakpoints tại `768px` và `1024px`.
- **Layout**: Max-width `800px`, padding linh hoạt theo thiết bị.

### JavaScript (Interactions)
- **Vanilla JS**: Khoảng 38 dòng mã để xử lý hiệu ứng.
- **Intersection Observer**: Xử lý hiệu ứng fade-in khi cuộn trang.
- **Motion Preference**: Hỗ trợ `prefers-reduced-motion` để tắt hiệu ứng cho người dùng nhạy cảm.

## 3. Hiệu suất & Tối ưu hóa
- **Kích thước file**: 20.16KB (Chỉ chiếm 40% giới hạn 50KB đề ra).
- **Dependencies**: 0 (Không sử dụng thư viện bên ngoài).
- **Requests**: Chỉ 1 request chính cho HTML (ngoại trừ các assets hình ảnh).

---
*Cập nhật lần cuối: 2025-12-23*
