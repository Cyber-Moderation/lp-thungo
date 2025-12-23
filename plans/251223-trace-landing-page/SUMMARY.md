# TRACE (DẤU VẾT) Landing Page - Plan Summary

**Plan Path**: `/plans/251223-trace-landing-page/`
**Created**: 2025-12-23
**Status**: ✅ Ready for Implementation

---

## 📋 Overview

Kế hoạch chi tiết để xây dựng landing page HTML **hoàn toàn self-contained** (1 file duy nhất) cho dự án **TRACE (DẤU VẾT)** - nghệ thuật sắp đặt về tuần hoàn và tái sinh đô thị tại Hozo City Tết Fest 2025.

### Deliverables
- ✅ **Single HTML file** (100% self-contained - ZERO external files)
- ✅ **Pure CSS inline** (NO Tailwind, NO CDN, NO frameworks)
- ✅ **Vanilla JS inline** (NO external libraries)
- ✅ Logo placeholders ready for user to add image src
- ✅ Responsive design (mobile-first)
- ✅ Smooth scroll animations & interactive hover states
- ✅ WCAG AAA accessibility
- ✅ Production-ready code

---

## 🎨 Design Specifications

### Color Palette
- Background: `#EBE5D9` (warm beige/cream)
- Text Primary: `#1A1A1A` (deep black)
- Accent Green: `#4A7C59` (muted sage)
- Border Light: `#D4CEC0` (subtle dividers)

### Typography
- Font: Times New Roman, Georgia (serif)
- Scale: 13px → 16px → 24px → 42px
- Line-height: 1.75 (optimized for Vietnamese)

### Layout
- Max-width: 800px
- Spacing: 8px base (8, 16, 24, 32, 48, 64, 80px)
- Mobile-first responsive design

---

## 📁 Plan Structure

```
plans/251223-trace-landing-page/
├── plan.md                    # Master plan document
├── phase-01-foundation.md     # HTML boilerplate & design system
├── phase-02-components.md     # Visual components development
├── phase-03-responsive.md     # Responsive design implementation
├── phase-04-interactions.md   # Animations & interactions
├── phase-05-polish.md         # Final optimization & QA
└── research/                  # (empty - no research needed)
```

---

## 🚀 Implementation Phases

### Phase 1: Foundation Setup (15-20 mins)
**File**: `phase-01-foundation.md`

- Create HTML5 boilerplate with semantic structure
- Integrate Tailwind CSS via CDN
- Define CSS custom properties (design tokens)
- Implement base typography styles
- Configure responsive viewport
- Test Vietnamese character rendering

**Output**: HTML foundation with design system ready

---

### Phase 2: Component Development (25-30 mins)
**File**: `phase-02-components.md`

- Logo section (Nhabe Scholae × Saigonxanh)
- Hero section (title, subtitle, event info)
- Content sections:
  - Artist Statement
  - Material Partner Statement
  - About Nhabe Scholae
  - About Saigonxanh
- Footer with contact info
- Section dividers

**Output**: All visual components with proper semantics

---

### Phase 3: Responsive Design (20-25 mins)
**File**: `phase-03-responsive.md`

- Mobile-first CSS implementation
- Fluid typography using `clamp()`
- Breakpoints: Mobile (< 768px), Tablet (768-1023px), Desktop (1024px+)
- Touch target optimization (44x44px minimum)
- Grid layout for about cards
- Test on multiple device sizes

**Output**: Fully responsive layout

---

### Phase 4: Animations & Interactions (15-20 mins)
**File**: `phase-04-interactions.md`

- Intersection Observer for scroll animations
- Fade-in effects with staggered delays
- Hover states (links, cards, logo)
- Smooth scroll behavior
- Motion preference respect (`prefers-reduced-motion`)
- Performance optimization (GPU acceleration)

**Output**: Smooth, accessible animations

---

### Phase 5: Polish & Optimization (15-20 mins)
**File**: `phase-05-polish.md`

- SEO meta tags (Open Graph, Twitter Cards, JSON-LD)
- Accessibility audit (WCAG AAA)
- Performance optimization (< 50KB file size)
- Cross-browser testing
- Content proofreading
- CSS/JS minification
- Final QA verification

**Output**: Production-ready HTML file

---

## ✅ Success Criteria

### Functional
- ✅ Single HTML file (self-contained)
- ✅ Responsive across all devices
- ✅ Smooth scroll animations
- ✅ Interactive hover states
- ✅ Vietnamese content properly rendered

### Design
- ✅ Matches extracted design guidelines
- ✅ Warm beige aesthetic
- ✅ Serif typography (editorial feel)
- ✅ Generous whitespace
- ✅ Clean, minimalist layout

### Performance
- ✅ Page load < 1 second
- ✅ File size < 50KB
- ✅ Lighthouse score > 95

### Accessibility
- ✅ WCAG AAA compliance
- ✅ Semantic HTML
- ✅ Keyboard navigation
- ✅ Screen reader compatible

---

## 📊 Estimated Timeline

| Phase | Duration | Cumulative |
|-------|----------|------------|
| Phase 1: Foundation | 15-20 mins | 20 mins |
| Phase 2: Components | 25-30 mins | 50 mins |
| Phase 3: Responsive | 20-25 mins | 75 mins |
| Phase 4: Interactions | 15-20 mins | 95 mins |
| Phase 5: Polish | 15-20 mins | 115 mins |

**Total**: 90-115 minutes (1.5-2 hours)

---

## 🎯 Next Steps

1. **Review Plan**: Xem xét kế hoạch chi tiết trong mỗi phase file
2. **Approve**: Xác nhận approach và specifications
3. **Implement**: Thực thi từng phase theo thứ tự
4. **Test**: Kiểm tra sau mỗi phase
5. **Deploy**: Upload file HTML lên hosting

---

## 📚 References

- Design Guidelines: `/docs/design-guidelines/trace-extracted-design.md`
- Reference Image: `/assets/WhatsApp Image 2025-12-23 at 08.42.51.jpeg`
- Tailwind CSS: https://tailwindcss.com/docs
- WCAG Guidelines: https://www.w3.org/WAI/WCAG21/quickref/

---

## 📞 Support Resources

### Technical Documentation
- HTML5: https://developer.mozilla.org/en-US/docs/Web/HTML
- CSS: https://developer.mozilla.org/en-US/docs/Web/CSS
- JavaScript: https://developer.mozilla.org/en-US/docs/Web/JavaScript
- Intersection Observer: https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API

### Validation Tools
- HTML Validator: https://validator.w3.org/
- Accessibility Checker: https://wave.webaim.org/
- Lighthouse: Chrome DevTools
- Mobile-Friendly Test: https://search.google.com/test/mobile-friendly

---

**Plan Status**: ✅ Complete & Ready
**Implementation Ready**: Yes
**Estimated Complexity**: Medium
**Confidence Level**: High

---

*Kế hoạch này cung cấp hướng dẫn chi tiết từng bước để tạo landing page TRACE (DẤU VẾT) với chất lượng production-ready, tối ưu performance, và accessibility.*
