# System Architecture - TRACE Project

Tài liệu này mô tả chi tiết kiến trúc hệ thống và các thành phần kỹ thuật của dự án TRACE (Dấu Vết).

## 1. Kiến trúc Tổng quan: Single File Architecture (SFA)
Toàn bộ ứng dụng được phân phối dưới dạng một tệp HTML duy nhất (`index.html`). Kiến trúc này được chọn để:
- **Tối ưu hóa tốc độ tải**: Loại bỏ độ trễ từ các HTTP requests cho file CSS/JS bên ngoài.
- **Tính độc lập**: Trang web hoạt động hoàn hảo mà không cần internet (nếu assets hình ảnh đã được cache).
- **Dễ dàng triển khai**: Có thể host ở bất kỳ đâu (GitHub Pages, S3, Netlify) chỉ với một file.

## 2. Các lớp Thành phần

### Lớp Dữ liệu & Cấu trúc (HTML5)
- Cấu trúc cây DOM được tổ chức phân cấp rõ ràng theo các Section.
- Tích hợp **SEO Metadata** sâu rộng và **JSON-LD Schema** để hỗ trợ bộ máy tìm kiếm nhận diện đây là một sự kiện (Event).

### Lớp Giao diện (CSS3)
- **Design System**: Định nghĩa toàn bộ hệ thống tokens trong `:root`.
- **Responsive System**:
  - `768px`: Chuyển sang layout máy tính bảng, điều chỉnh grid.
  - `1024px`: Layout desktop đầy đủ, tăng padding và kích thước chữ.
- **Component Styling**: Sử dụng inline styles trong thẻ `<style>` để đảm bảo render blocking minimal nhất.
- **Logo Header Pattern**: Triển khai thiết kế header dàn ngang với viền dưới, thay thế cho thiết kế boxed cũ.

### Lớp Logic & Tương tác (JavaScript Vanilla)
- **Observer Pattern**: Sử dụng `Intersection Observer API` để theo dõi vị trí cuộn của người dùng và kích hoạt các class hiệu ứng.
- **Event Handling**: Xử lý sự kiện `DOMContentLoaded` để đảm bảo scripts chỉ chạy khi nội dung đã sẵn sàng.

## 3. Quy trình Xử lý Giao diện
1. **Request**: Trình duyệt yêu cầu `index.html`.
2. **Parsing**: Trình duyệt đọc file, áp dụng ngay lập tức các CSS tokens và styles trong `<style>`.
3. **First Meaningful Paint**: Nội dung hiển thị ngay lập tức (Zero flash of unstyled content - FOUC).
4. **Hydration**: JavaScript kích hoạt các bộ quan sát (observers) cho các hiệu ứng cuộn.

## 4. Tối ưu hóa Hiệu suất
- **Gzip/Brotli**: Với kích thước file 20.16KB, sau khi nén có thể giảm xuống còn ~5KB.
- **Image Optimization**: Logo sử dụng Data URI (Base64/SVG) để nhúng trực tiếp vào mã nguồn.
- **No External Fonts**: Sử dụng font hệ thống loại Serif để loại bỏ bước tải font từ máy chủ khác.

---
*Cập nhật lần cuối: 2025-12-23*
