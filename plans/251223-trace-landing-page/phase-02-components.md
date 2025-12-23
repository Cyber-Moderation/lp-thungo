# Phase 2: Component Development (UPDATED - Pure CSS)

**Duration**: 25-30 minutes
**Dependency**: Phase 1 (Foundation)
**Output**: All visual components with pure CSS (NO Tailwind classes)

---

## Objectives

1. Build logo section with placeholder images
2. Create hero section (title, subtitle, event info)
3. Develop content sections (4 main sections)
4. Implement footer with contact info
5. Add section dividers
6. Apply proper semantic HTML and pure CSS classes

---

## Components

### 2.1 Logo Section (WITH IMAGE PLACEHOLDERS)

```html
<div class="logo-section">
  <div class="logo-container">
    <!-- User will add logo image links here -->
    <div class="logo-left">
      <img src="" alt="Nhabe Scholae Logo" class="logo-img" />
      <span class="logo-text">NHABE SCHOLAE</span>
    </div>

    <div class="logo-divider"></div>

    <div class="logo-right">
      <img src="" alt="Saigonxanh Logo" class="logo-img" />
      <span class="logo-text">saigonxanh</span>
    </div>
  </div>
</div>

<style>
.logo-section {
  text-align: center;
  margin-bottom: 48px;
}

.logo-container {
  max-width: 600px;
  margin: 0 auto;
  padding: 24px 32px;
  background-color: white;
  border: 2px solid var(--color-border-light);
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 24px;
  transition: transform 0.4s ease, box-shadow 0.4s ease;
}

.logo-container:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
}

.logo-left,
.logo-right {
  display: flex;
  align-items: center;
  gap: 12px;
}

.logo-img {
  height: 40px;
  width: auto;
  object-fit: contain;
}

/* Hide broken image icon if src is empty */
.logo-img[src=""] {
  display: none;
}

.logo-text {
  font-family: Arial, 'Helvetica Neue', sans-serif;
  font-size: 11px;
  font-weight: 400;
  letter-spacing: 0.05em;
  color: var(--color-text-primary);
}

.logo-divider {
  width: 1px;
  height: 40px;
  background-color: var(--color-border-light);
}

@media (max-width: 767px) {
  .logo-container {
    flex-direction: column;
    padding: 20px;
    gap: 16px;
  }

  .logo-divider {
    width: 60px;
    height: 1px;
  }

  .logo-img {
    height: 32px;
  }

  .logo-text {
    font-size: 10px;
  }
}
</style>
```

### 2.2 Hero Section

```html
<header class="hero-section">
  <h1 class="hero-title">TRACE (DẤU VẾT)</h1>
  <p class="hero-subtitle">Nhabe Scholae × Saigonxanh</p>
  <p class="hero-event">Hozo City Tết Fest 2025</p>
</header>

<style>
.hero-section {
  text-align: center;
  margin-bottom: 64px;
}

.hero-title {
  font-size: clamp(28px, 5vw, 42px);
  font-weight: 700;
  letter-spacing: 0.02em;
  text-transform: uppercase;
  margin-bottom: 24px;
  color: var(--color-text-heading);
}

.hero-subtitle {
  font-size: clamp(16px, 2.5vw, 18px);
  font-weight: 400;
  color: var(--color-text-primary);
  margin-bottom: 16px;
}

.hero-event {
  font-size: 14px;
  color: var(--color-text-secondary);
}
</style>
```

### 2.3 Content Section Template

```html
<!-- Section 1: Artist Statement -->
<section class="content-section">
  <h2 class="section-heading">TRACE (DẤU VẾT) — Artist Statement</h2>

  <div class="section-content">
    <p>Dự án "Trace (Dấu Vết)" là một sắp đặt của văn phòng Nhabe Scholae trong khuôn khổ Mê Vị và Hozo City Tết Fest 2025. 65 khối đất tái sử dụng và làm mới lại từ các khu ngòi của vùng đất Sài Gòn nay được đặt lại vào trong công viên bờ sông, khóa kết một vòng tuần hoàn của sự sống.</p>

    <p>Lấy cảm hứng từ thực phẩm, dinh dưỡng và sức mạnh bền bỉ mà ẩn ngầm của tự nhiên, chúng tôi muốn tạo ra một trải nghiệm trực diện về chất liệu, sẽ được cảm nhận như một hiện diện sống động và màu mỡ, sẽ tác động lên người xem thông qua một nhịp điệu chậm rãi, một vật chất đầy đặn, mạnh mẽ và âm thầm.</p>

    <p>Mặt đất mang theo cả kí ức và sự quên lãng, cả sự bao dung và những bạo lực của con người, đồng thời cũng là một ẩn dụ về tuổi thơ, sự tái sinh, vòng tròn và sự mong manh tự nhiên.</p>
  </div>
</section>

<!-- Divider -->
<hr class="section-divider">

<!-- Section 2: Material Partner Statement -->
<section class="content-section">
  <h2 class="section-heading">Material Partner Statement — Saigonxanh</h2>

  <div class="section-content">
    <p>Saigonxanh tham gia dự án "Trace (Dấu Vết)" với vai trò đối tác vật liệu xanh, cung cấp toàn bộ 65 khối đất cho sắp đặt.</p>

    <p>Toàn bộ khối lượng đất trong công trình này là sản phẩm của quá trình xử lý và tái chế các dòng vật chất hữu cơ phát sinh từ hoạt động thường nhật của Thành phố. Thông qua việc ứng dụng công nghệ sinh học, bao gồm ủ hiếu khí và ủ kỵ khí, các nguồn vật chất sau xử lý được chuyển hóa thành đất sạch giàu hữu cơ, một dạng vật liệu tái sinh, an toàn và có thể đưa trở lại phục vụ đời sống đô thị.</p>

    <p>Trong cách tiếp cận của chúng tôi, phục hồi tài nguyên là tạo cho các dòng vật chất điểm khởi đầu của một vòng đời mới. Việc đưa đất tái sinh trở lại không gian công viên bờ sông Sài Gòn, ngay trung tâm Thành phố, là một hành động mang tính biểu tượng: khép lại một vòng tuần hoàn, nơi những gì được sinh ra từ đô thị được xử lý, tái tạo và trả lại cho chính đô thị ấy.</p>

    <p>Sự hợp tác này phản ánh định hướng phát triển của Thành phố trong việc thúc đẩy vật liệu xanh, kinh tế tuần hoàn và giảm phát thải, đồng thời đồng hành cùng cam kết Net Zero của Việt Nam được công bố tại COP26. Thông qua "Trace", Saigonxanh mong muốn góp phần mở ra một cách nhìn khác về vật liệu tái chế: không chỉ như giải pháp kỹ thuật, mà như một thành tố văn hóa, có khả năng đối thoại với nghệ thuật, không gian công cộng và tương lai bền vững của đô thị.</p>
  </div>
</section>

<hr class="section-divider">

<style>
.content-section {
  margin-bottom: 64px;
}

.section-heading {
  font-size: clamp(20px, 3vw, 24px);
  font-weight: 700;
  letter-spacing: 0.01em;
  color: var(--color-text-heading);
  text-align: left;
  margin-bottom: 24px;
}

.section-content {
  max-width: 100%;
}

.section-content p {
  margin-bottom: 20px;
  text-align: left;
  font-size: clamp(15px, 2.5vw, 16px);
  line-height: 1.75;
}

.section-content p:last-child {
  margin-bottom: 0;
}

.section-divider {
  width: 100%;
  height: 1px;
  background-color: var(--color-border-light);
  border: none;
  margin: 64px 0;
}

@media (max-width: 767px) {
  .content-section {
    margin-bottom: 48px;
  }

  .section-divider {
    margin: 48px 0;
  }
}
</style>
```

### 2.4 About Sections (Two-Column Layout - Pure CSS Grid)

```html
<div class="about-sections">
  <div class="about-grid">

    <!-- About Nhabe Scholae -->
    <div class="about-card">
      <div class="about-logo">
        <!-- Placeholder for logo image -->
        <img src="" alt="Nhabe Scholae Icon" class="about-logo-img" />
      </div>
      <h3 class="about-heading">NHABE / Nhabe Scholae</h3>
      <p class="about-text">Nhabe Scholae là một văn phòng kiến trúc và thực hành sáng tạo do KTS. Nguyễn Anh Cường sáng lập tại TP. Hồ Chí Minh. Hoạt động của studio đặt tại giao điểm giữa kiến trúc, nghệ thuật sắp đặt và nghiên cứu lý luận, với nền tảng đào tạo và kinh nghiệm quốc tế. Các dự án của Nhabe Scholae tập trung khám phá mối quan hệ giữa con người, cảnh quan, vật liệu và các giác quan trong bối cảnh đô thị đương đại, đồng thời mở rộng tư duy kiến trúc ra ngoài những khuôn mẫu công năng và hình thức quen thuộc.</p>
      <a href="http://www.nhabescholae.com/" target="_blank" rel="noopener noreferrer" class="about-link">www.nhabescholae.com</a>
    </div>

    <!-- About Saigonxanh -->
    <div class="about-card">
      <div class="about-logo">
        <!-- Placeholder for logo image -->
        <img src="" alt="Saigonxanh Icon" class="about-logo-img" />
      </div>
      <h3 class="about-heading">About Saigonxanh</h3>
      <p class="about-text">Saigonxanh là doanh nghiệp tiên phong tại Việt Nam trong xử lý các dòng vật chất đô thị theo mô hình tuần hoàn, khép kín và không chôn lấp. Thông qua ứng dụng công nghệ sinh học, Saigonxanh thúc đẩy tái chế và phục hồi tài nguyên, chuyển hóa các nguồn vật chất sau sử dụng thành sản phẩm mới có giá trị. Từ quá trình này, Saigonxanh phát triển các sản phẩm đất sạch giàu hữu cơ, được ứng dụng hiệu quả trong nông nghiệp, cảnh quan và không gian xanh đô thị, với hệ thống ba nhà máy trên cả nước.</p>
      <a href="https://greensaigon.com.vn/" target="_blank" rel="noopener noreferrer" class="about-link">greensaigon.com.vn</a>
    </div>

  </div>
</div>

<style>
.about-sections {
  margin-bottom: 64px;
}

.about-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 32px;
}

@media (min-width: 768px) {
  .about-grid {
    grid-template-columns: 1fr 1fr;
    gap: 48px;
  }
}

.about-card {
  padding: 24px;
  background: rgba(255, 255, 255, 0.5);
  border: 1px solid var(--color-border-light);
  border-radius: 8px;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.about-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.08);
}

.about-logo {
  margin-bottom: 16px;
  height: 32px;
}

.about-logo-img {
  height: 32px;
  width: auto;
  object-fit: contain;
}

/* Hide broken image icon if src is empty */
.about-logo-img[src=""] {
  display: none;
}

.about-heading {
  font-size: 18px;
  font-weight: 700;
  color: var(--color-text-heading);
  margin-bottom: 16px;
}

.about-text {
  font-size: 14px;
  line-height: 1.7;
  color: var(--color-text-primary);
  margin-bottom: 16px;
}

.about-link {
  font-size: 13px;
  color: var(--color-accent-green);
  border-bottom: 1px solid var(--color-accent-green);
  text-decoration: none;
  display: inline-block;
  transition: opacity 0.3s ease;
}

.about-link:hover {
  opacity: 0.7;
}
</style>
```

### 2.5 Footer Section

```html
<footer class="footer-section">
  <div class="footer-content">
    <p>Trace (Dấu Vết)</p>
    <p>Nhabe Scholae × Saigonxanh</p>
    <p>Hozo City Tết Fest 2025</p>
  </div>
</footer>

<style>
.footer-section {
  margin-top: 64px;
  padding-top: 32px;
  border-top: 1px solid var(--color-border-light);
}

.footer-content {
  text-align: center;
}

.footer-content p {
  font-size: 13px;
  line-height: 1.8;
  margin-bottom: 8px;
  color: var(--color-text-secondary);
}

.footer-content p:last-child {
  margin-bottom: 0;
}
</style>
```

---

## Deliverables

✅ Logo section with **image placeholders** (user adds src later)
✅ Hero section with title, subtitle, event info
✅ Content sections (Artist Statement, Material Partner)
✅ About sections (Nhabe Scholae, Saigonxanh) with **image placeholders**
✅ Footer with contact info
✅ Section dividers
✅ **Pure CSS classes** (NO Tailwind utility classes)
✅ Semantic HTML with proper ARIA labels
✅ Proper spacing and typography hierarchy

---

## Important Notes for User

### Logo Images
Các vị trí placeholder cho logo:

1. **Header Logo Section**:
   ```html
   <img src="YOUR_LOGO_URL_HERE" alt="Nhabe Scholae Logo" class="logo-img" />
   <img src="YOUR_LOGO_URL_HERE" alt="Saigonxanh Logo" class="logo-img" />
   ```

2. **About Cards**:
   ```html
   <img src="YOUR_ICON_URL_HERE" alt="Nhabe Scholae Icon" class="about-logo-img" />
   <img src="YOUR_ICON_URL_HERE" alt="Saigonxanh Icon" class="about-logo-img" />
   ```

User chỉ cần thay `src=""` bằng link ảnh thực tế.

---

## Testing Checklist

- [ ] All content sections render correctly
- [ ] Vietnamese text displays without issues
- [ ] Spacing matches design specifications
- [ ] Links are accessible and styled properly
- [ ] Logo placeholders hide gracefully when src is empty
- [ ] About cards have hover effects
- [ ] Footer border displays correctly
- [ ] **NO Tailwind classes used** - all pure CSS

---

## Next Phase

Proceed to **Phase 3: Responsive Design** to optimize layout for mobile, tablet, and desktop devices.
