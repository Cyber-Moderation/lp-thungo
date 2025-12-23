# Codebase Summary - TRACE Project

Tóm tắt cấu trúc và nội dung mã nguồn hiện tại của dự án.

## 1. Thành phần Chính
| Tệp tin | Kích thước | Chức năng |
| :--- | :--- | :--- |
| `index.html` | ~4.5KB | Tệp duy nhất chứa toàn bộ HTML/CSS/JS |

## 2. Chi tiết Triển khai (Phase 1)

### HTML Structure
- Sử dụng thẻ `<main>` với class `.page-container` để bọc toàn bộ nội dung.
- Đã có khung thử nghiệm hiển thị tiếng Việt.

### CSS (Design Tokens)
- **Bảng màu**: 6 biến màu cơ bản (background, text primary/heading/secondary, accent green, border).
- **Typography**: Sử dụng font Serif (Times New Roman fallback), hỗ trợ fluid scaling bằng `clamp()`.
- **Spacing**: Hệ thống thang đo từ `xs` (8px) đến `3xl` (80px).
- **Layout**: Max-width `800px`, padding linh hoạt theo thiết bị.

### Responsive Strategy
- Sử dụng Mobile-first approach.
- Breakpoints tại `768px` (Tablet) và `1024px` (Desktop).

## 3. Trạng thái Hiện tại
- [x] Thiết lập cấu trúc nền tảng.
- [x] Định nghĩa Design Tokens.
- [x] Xử lý hiển thị tiếng Việt.
- [ ] Chưa có JavaScript logic (dự kiến Phase 4).

---
*Cập nhật lần cuối: 2025-12-23*
