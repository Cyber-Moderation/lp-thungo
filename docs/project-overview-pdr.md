# Project Overview & PDR - TRACE (Dấu Vết)

## Project Overview
Dự án TRACE (Dấu Vết) là một trang web giới thiệu nghệ thuật sắp đặt về tuần hoàn và tái sinh đô thị, được thực hiện bởi Nhabe Scholae phối hợp với Saigonxanh trong khuôn khổ Hozo City Tết Fest 2025.

Trang web được thiết kế theo phong cách tối giản, tập trung vào nội dung và thông điệp, sử dụng kiến trúc tệp duy nhất (Single File Architecture) để đạt hiệu suất tối đa và tính độc lập hoàn toàn.

## Status: PRODUCTION READY ✅
Dự án đã hoàn thành tất cả 5 giai đoạn triển khai với điểm chất lượng 100/100.
- **Phase 1 (Foundation)**: Thiết lập cấu trúc nền tảng và Design System.
- **Phase 2 (Components)**: Xây dựng các khối nội dung và layout.
- **Phase 3 (Responsive)**: Tối ưu hóa cho Mobile, Tablet và Desktop.
- **Phase 4 (Interactions)**: Thêm hiệu ứng cuộn và tương tác người dùng.
- **Phase 5 (Polish)**: Tối ưu hóa SEO, Accessibility và hiệu suất cuối cùng.

## Product Development Requirements (PDR)

### 1. Functional Requirements
- **Hiển thị nội dung**: Trình bày thông điệp nghệ thuật (Artist Statement) và đối tác vật liệu (Material Partner Statement).
- **Hỗ trợ tiếng Việt**: Đảm bảo hiển thị chính xác các ký tự tiếng Việt với font Serif.
- **Responsive Design**: Hoạt động mượt mà trên nhiều thiết bị (Mobile, Tablet, Desktop).
- **SEO & Social**: Đầy đủ meta tags và Schema.org cho sự kiện.

### 2. Non-functional Requirements
- **Performance**: Tải trang cực nhanh, kích thước tệp < 25KB (thực tế 20.16KB).
- **Single File Architecture**: Toàn bộ HTML, CSS và JS nằm trong một file `index.html`.
- **Accessibility**: Đạt chuẩn WCAG AAA (độ tương phản ≥13.5:1).
- **Zero Dependencies**: Không phụ thuộc vào bất kỳ thư viện hay CDN bên ngoài nào.

### 3. Technical Decisions & Recent Changes
- **Architecture**: Sử dụng SFA để loại bỏ HTTP requests bổ sung và đơn giản hóa việc triển khai.
- **Logo Header Redesign**: Thay đổi từ dạng khối (boxed) sang dạng thanh dàn ngang (full-width header bar).
  - Loại bỏ nền trắng, chuyển sang trong suốt đồng nhất với body.
  - Sử dụng viền dưới (bottom-border) chạy toàn màn hình thay vì viền 4 cạnh.
  - Tối ưu hóa scaling trên mobile bằng `transform: scale()`.
- **Motion Control**: Tích hợp `prefers-reduced-motion` để tôn trọng thiết lập của người dùng.

---
*Cập nhật lần cuối: 2025-12-23*
