# TRACE (DẤU VẾT) - Landing Page

Dự án trang web giới thiệu nghệ thuật sắp đặt **TRACE (Dấu Vết)**, một sự hợp tác giữa **Nhabe Scholae** và **Saigonxanh** tại Hozo City Tết Fest 2025.

## 🌟 Tổng quan
"Trace (Dấu Vết)" là một sắp đặt nghệ thuật về tuần hoàn và tái sinh đô thị, sử dụng 65 khối đất tái chế từ các khu ngòi của Sài Gòn. Trang web được thiết kế để truyền tải thông điệp về môi trường, sự tái sinh và vòng tròn của sự sống thông qua một trải nghiệm thị giác tối giản và tinh tế.

## 🚀 Khởi động nhanh
Vì dự án sử dụng kiến trúc tệp đơn (Single File Architecture), bạn chỉ cần mở file `index.html` trong bất kỳ trình duyệt hiện đại nào:

```bash
open index.html
```

Không cần cài đặt thêm thư viện hoặc chạy quy trình build nào.

## 🏗 Kiến trúc Kỹ thuật
- **Single File Architecture (SFA)**: Toàn bộ HTML, CSS và JavaScript được đóng gói trong một file `index.html` duy nhất (20.16KB).
- **Vanilla Tech Stack**:
  - HTML5 Semantic cho cấu trúc.
  - CSS3 Modern (Custom Properties, Grid, Flexbox, Clamp) cho giao diện.
  - Vanilla JavaScript (ES6+) cho các hiệu ứng tương tác.
- **Zero Dependencies**: Không sử dụng thư viện bên ngoài (không jQuery, không Tailwind, không Google Fonts).
- **SEO & Social**: Tích hợp đầy đủ Open Graph, Twitter Card và JSON-LD Event Schema.

## 🎨 Nguyên tắc Thiết kế
- **Eco-Aesthetic**: Sử dụng bảng màu tự nhiên (Beige ấm, Xanh lá mềm) gợi liên tưởng đến đất và cây cỏ.
- **Minimalist Editorial**: Font chữ Serif cổ điển kết hợp với bố cục thông thoáng, tập trung vào nội dung văn bản.
- **Fluid Typography**: Kích thước chữ tự động điều chỉnh linh hoạt theo kích thước màn hình.
- **WCAG AAA**: Đảm bảo khả năng tiếp cận tối đa với độ tương phản màu sắc cao.

## 📱 Tính năng nổi bật
- **Responsive Design**: Tối ưu hóa cho mọi thiết bị từ điện thoại nhỏ đến màn hình desktop lớn.
- **Scroll Animations**: Sử dụng `Intersection Observer` cho các hiệu ứng xuất hiện mượt mà khi cuộn trang.
- **Motion Preference**: Tự động tắt hiệu ứng nếu người dùng cài đặt "Reduce Motion" trong hệ thống.
- **Full-width Logo Header**: Thiết kế header mới với thanh logo dàn ngang, phong cách hiện đại và tinh giản.

## 📂 Cấu trúc Thư mục
```
.
├── index.html          # File entry point duy nhất
├── assets/             # Hình ảnh UI và tài liệu tham khảo
├── docs/               # Tài liệu kỹ thuật chi tiết
└── plans/              # Kế hoạch triển khai dự án
```

## 🛠 Quy trình Phát triển
Dự án tuân thủ các quy tắc YAGNI (You Ain't Gonna Need It) và KISS (Keep It Simple, Stupid) để giữ cho mã nguồn sạch sẽ và hiệu quả nhất.

---
© 2025 Nhabe Scholae × Saigonxanh. Phát triển bởi Claude Code.
