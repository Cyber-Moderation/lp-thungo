# System Architecture - TRACE Project

Tài liệu này mô tả kiến trúc hệ thống và cách tổ chức mã nguồn của dự án TRACE.

## 1. Kiến trúc Tổng quan
Dự án sử dụng kiến trúc **Single File Application (SFA)**. Toàn bộ tài nguyên cần thiết để trang web hoạt động được đóng gói trong một tệp HTML duy nhất. Điều này giúp tối ưu hóa tốc độ tải trang và đơn giản hóa việc triển khai (deployment).

## 2. Các lớp Thành phần

### Lớp Dữ liệu & Cấu trúc (HTML5)
- Sử dụng HTML5 semantic để định nghĩa cấu trúc nội dung.
- Encoding: `UTF-8` để hỗ trợ đầy đủ tiếng Việt.

### Lớp Giao diện (CSS3)
- **Design Tokens**: Sử dụng CSS Custom Properties (:root) để quản lý màu sắc, khoảng cách và font chữ.
- **Fluid Layout**: Sử dụng kết hợp Flexbox/Grid và các hàm tính toán CSS như `clamp()`, `calc()` để tạo giao diện linh hoạt.
- **Zero-External CSS**: Không sử dụng link đến các file CSS bên ngoài hoặc Google Fonts.

### Lớp Logic (JavaScript)
- **Vanilla JS**: Chỉ sử dụng JavaScript thuần túy nếu cần thiết (Phase 4).
- **Inline Script**: Mã JavaScript được đặt trực tiếp trong thẻ `<script>` ở cuối file.

## 3. Quy trình Xử lý
1. Trình duyệt tải `index.html`.
2. Phân giải (Parse) các thẻ `<style>` và áp dụng giao diện ngay lập tức.
3. Hiển thị nội dung HTML đã được định dạng.
4. Thực thi JavaScript (nếu có) sau khi DOM đã sẵn sàng.

## 4. Ưu điểm Kiến trúc
- **Tốc độ**: Giảm thiểu số lượng HTTP requests.
- **Độc lập**: Không bị ảnh hưởng bởi các sự cố từ bên thứ ba (CDN down, v.v.).
- **Dễ bảo trì**: Mọi thứ nằm ở một nơi duy nhất.

---
*Cập nhật lần cuối: 2025-12-23*
