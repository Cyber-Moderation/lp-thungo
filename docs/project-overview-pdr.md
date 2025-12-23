# Project Overview & PDR - TRACE (Dấu Vết)

## Project Overview
Dự án TRACE (Dấu Vết) là một trang web giới thiệu nghệ thuật sắp đặt về tuần hoàn và tái sinh đô thị, được thực hiện bởi Nhabe Scholae phối hợp với Saigonxanh trong khuôn khổ Hozo City Tết Fest 2025.

Trang web được thiết kế theo phong cách tối giản, tập trung vào nội dung và hình ảnh, sử dụng một file duy nhất (self-contained) để tối ưu hóa hiệu suất và khả năng bảo trì.

## Product Development Requirements (PDR)

### 1. Functional Requirements
- **Hiển thị nội dung**: Trình bày thông tin về dự án, thông điệp về môi trường và thông tin các đơn vị đồng hành.
- **Hỗ trợ tiếng Việt**: Đảm bảo hiển thị chính xác các ký tự tiếng Việt có dấu.
- **Responsive Design**: Hoạt động mượt mà trên nhiều thiết bị (Mobile, Tablet, Desktop).

### 2. Non-functional Requirements
- **Performance**: Trang web phải tải nhanh, không phụ thuộc vào các thư viện bên ngoài.
- **Single File Architecture**: Toàn bộ HTML, CSS và JS (nếu có) được đặt trong một file `index.html`.
- **Accessibility**: Sử dụng HTML5 semantic để hỗ trợ trình đọc màn hình.
- **Visual Style**: Tuân thủ hướng dẫn thiết kế (Design Guidelines) với tone màu tự nhiên và font chữ Serif cổ điển.

### 3. Technical Constraints
- **Không có dependency bên ngoài**: Không sử dụng CDN cho CSS/JS, không dùng framework (React, Vue, v.v.).
- **CSS Inline**: Toàn bộ CSS nằm trong thẻ `<style>` của `index.html`.
- **Mobile-first**: Ưu tiên thiết kế cho thiết bị di động trước.

## Status: Phase 1 Completed
- Cấu trúc HTML cơ bản đã được thiết lập.
- Design System (Tokens) đã được định nghĩa.
- Cơ chế Responsive đã được triển khai.
- Hiển thị tiếng Việt đã được xác nhận.

---
*Cập nhật lần cuối: 2025-12-23*
