# TRACE (DẤU VẾT) - Extracted Design Guidelines

**Project**: Open Letter Landing Page
**Context**: Nghệ thuật sắp đặt về tuần hoàn & tái sinh đô thị
**Collaboration**: Nhabe Scholae × Saigonxanh
**Event**: Hozo City Tết Fest 2025
**Design Tone**: Eco-friendly, artistic, minimalist, refined
**Extracted From**: WhatsApp Image 2025-12-23 at 08.42.51.jpeg
**Date Analyzed**: 2025-12-23

---

## 1. Color Palette

### Primary Colors
```css
--color-background: #EBE5D9;      /* Warm beige/cream background */
--color-text-primary: #1A1A1A;    /* Deep black for body text */
--color-text-heading: #000000;    /* Pure black for headings */
--color-accent-green: #4A7C59;    /* Muted sage green for logo/accents */
```

### Supporting Colors
```css
--color-border-light: #D4CEC0;    /* Subtle border for dividers */
--color-text-secondary: #2C2C2C;  /* Slightly lighter for secondary text */
```

### Color Usage Guidelines
- **Background**: Warm beige (#EBE5D9) creates eco-friendly, organic feel
- **Text Contrast**: Black text on beige ensures WCAG AAA readability
- **Green Accent**: Used sparingly for circular logo element and brand identity
- **Monochromatic Approach**: Limited palette reinforces minimalist aesthetic

---

## 2. Typography

### Font Families
```css
--font-heading: 'Times New Roman', 'Georgia', serif;
--font-body: 'Times New Roman', 'Georgia', serif;
--font-accent: 'Arial', 'Helvetica Neue', sans-serif;
```

**Analysis**: Design uses classic serif typography (appears to be Times New Roman or similar) for both headings and body, creating formal, editorial aesthetic. Contact info may use sans-serif.

### Type Scale & Hierarchy

#### H1 - Main Title "TRACE/DẤU VẾT"
```css
font-size: 42px;
font-weight: 700;
line-height: 1.2;
letter-spacing: 0.02em;
text-transform: uppercase;
color: var(--color-text-heading);
margin-bottom: 32px;
```

#### H2 - Section Headers
```css
font-size: 24px;
font-weight: 700;
line-height: 1.3;
letter-spacing: 0.01em;
color: var(--color-text-heading);
margin-bottom: 16px;
```

#### Body Text - Paragraphs
```css
font-size: 16px;
font-weight: 400;
line-height: 1.75;
letter-spacing: 0.005em;
color: var(--color-text-primary);
margin-bottom: 20px;
```

#### Small Text - Footer/Contact
```css
font-size: 13px;
font-weight: 400;
line-height: 1.6;
letter-spacing: 0.01em;
color: var(--color-text-secondary);
```

### Vietnamese Typography Considerations
- Diacritical marks (ă, â, đ, ê, ô, ơ, ư) render cleanly in serif fonts
- Line-height 1.75 provides adequate spacing for Vietnamese accents
- Georgia/Times New Roman have excellent Vietnamese character support

---

## 3. Layout & Spacing

### Container System
```css
--container-max-width: 800px;
--container-padding-desktop: 80px;
--container-padding-tablet: 48px;
--container-padding-mobile: 24px;
```

### Spacing Scale (8px base)
```css
--space-xs: 8px;
--space-sm: 16px;
--space-md: 24px;
--space-lg: 32px;
--space-xl: 48px;
--space-2xl: 64px;
--space-3xl: 80px;
```

### Section Structure

#### Header Section
- Logo: Circular green element, ~80px diameter, centered
- Title: 32px margin-top from logo
- Subtitle/Description: 24px margin-top from title

#### Body Content
- Paragraph spacing: 20px between paragraphs
- Section spacing: 48px between major sections
- Content width: Max 800px, centered

#### Footer Section
- Border-top: 1px solid var(--color-border-light)
- Padding-top: 32px from border
- Margin-top: 64px from last content section
- Contact info: Left-aligned, 16px line-height

### Grid System
```css
display: flex;
flex-direction: column;
align-items: center;
text-align: center; /* For header/title */
text-align: left;   /* For body paragraphs */
```

**Layout Pattern**: Centered vertical layout with left-aligned body text, centered headings.

---

## 4. Visual Hierarchy

### Component Organization (Top to Bottom)

1. **Logo/Brand Identity**
   - Circular green element at top
   - Size: ~80px diameter
   - Margin-bottom: 32px
   - Visual weight: Medium (color accent)

2. **Primary Heading "TRACE/DẤU VẾT"**
   - Uppercase, bold serif
   - Size: 42px
   - Visual weight: Heavy (largest text element)
   - Dual-language presentation (English/Vietnamese)

3. **Subtitle/Description**
   - Regular weight serif
   - Size: 16-18px
   - Visual weight: Light
   - Provides context below title

4. **Body Content Sections**
   - Left-aligned paragraphs
   - Clear paragraph breaks (20px spacing)
   - Visual weight: Medium (primary content)
   - Generous line-height (1.75) for readability

5. **Footer/Contact Information**
   - Border separator above
   - Smaller text (13px)
   - Visual weight: Light (supporting info)
   - Multi-line contact details
   - Social/web links

### Whitespace Strategy
- **Generous vertical spacing**: 48-64px between major sections
- **Contained width**: Max 800px prevents long line lengths
- **Breathing room**: Ample padding around all content
- **Focused attention**: Centered layout draws eye down vertical axis

---

## 5. Component Patterns

### Circular Logo/Accent Element
```css
.logo-circle {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  background-color: var(--color-accent-green);
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 32px;
}
```

### Title Block
```html
<div class="title-block">
  <h1 class="title-primary">TRACE / DẤU VẾT</h1>
  <p class="title-subtitle">An Open Letter on Urban Circulation & Regeneration</p>
</div>
```

### Content Section
```html
<section class="content-section">
  <h2 class="section-heading">Section Title</h2>
  <p class="body-text">Paragraph content...</p>
  <p class="body-text">Paragraph content...</p>
</section>
```

### Footer Contact Block
```html
<footer class="contact-footer">
  <div class="contact-line">Organization Name</div>
  <div class="contact-line">Email: contact@example.com</div>
  <div class="contact-line">Social: @handle</div>
</footer>
```

### Divider Pattern
```css
.section-divider {
  width: 100%;
  height: 1px;
  background-color: var(--color-border-light);
  margin: 64px 0;
}
```

---

## 6. Responsive Behavior

### Desktop (1024px+)
```css
.container {
  max-width: 800px;
  padding: 80px 80px;
}

.title-primary {
  font-size: 42px;
}

.body-text {
  font-size: 16px;
  line-height: 1.75;
}
```

### Tablet (768px - 1023px)
```css
.container {
  max-width: 100%;
  padding: 48px 48px;
}

.title-primary {
  font-size: 36px;
}

.body-text {
  font-size: 16px;
  line-height: 1.7;
}
```

### Mobile (< 768px)
```css
.container {
  padding: 24px 24px;
}

.title-primary {
  font-size: 28px;
  letter-spacing: 0.01em;
}

.section-heading {
  font-size: 20px;
}

.body-text {
  font-size: 15px;
  line-height: 1.65;
}

.logo-circle {
  width: 64px;
  height: 64px;
}

.section-divider {
  margin: 48px 0;
}
```

### Responsive Typography Scaling
- Use `clamp()` for fluid typography:
  ```css
  font-size: clamp(28px, 5vw, 42px); /* Title */
  font-size: clamp(15px, 2.5vw, 16px); /* Body */
  ```

### Touch Target Optimization
- Links/buttons minimum 44x44px on mobile
- Increase footer contact link spacing on mobile

---

## 7. Implementation Recommendations

### HTML Structure
```html
<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>TRACE / DẤU VẾT - Open Letter</title>
</head>
<body>
  <main class="page-container">
    <div class="logo-section">
      <div class="logo-circle">
        <!-- Logo SVG or image -->
      </div>
    </div>

    <header class="title-block">
      <h1 class="title-primary">TRACE / DẤU VẾT</h1>
      <p class="title-subtitle">An Open Letter on Urban Circulation & Regeneration</p>
    </header>

    <section class="content-section">
      <!-- Vietnamese and English content paragraphs -->
    </section>

    <hr class="section-divider">

    <footer class="contact-footer">
      <!-- Contact information -->
    </footer>
  </main>
</body>
</html>
```

### CSS Architecture
```css
/* 1. CSS Variables (Design Tokens) */
:root {
  /* Colors */
  --color-background: #EBE5D9;
  --color-text-primary: #1A1A1A;
  --color-text-heading: #000000;
  --color-accent-green: #4A7C59;
  --color-border-light: #D4CEC0;

  /* Typography */
  --font-heading: 'Times New Roman', Georgia, serif;
  --font-body: 'Times New Roman', Georgia, serif;

  /* Spacing */
  --space-xs: 8px;
  --space-sm: 16px;
  --space-md: 24px;
  --space-lg: 32px;
  --space-xl: 48px;
  --space-2xl: 64px;
  --space-3xl: 80px;

  /* Layout */
  --container-max-width: 800px;
}

/* 2. Base Styles */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: var(--font-body);
  background-color: var(--color-background);
  color: var(--color-text-primary);
  line-height: 1.75;
  -webkit-font-smoothing: antialiased;
}

/* 3. Layout Components */
.page-container {
  max-width: var(--container-max-width);
  margin: 0 auto;
  padding: var(--space-3xl) var(--space-3xl);
}

/* 4. Typography Components */
/* 5. Responsive Media Queries */
```

### Font Loading Strategy
```html
<!-- Fallback to system fonts, no web font loading needed -->
<style>
  body {
    font-family: 'Times New Roman', Georgia, 'Noto Serif', serif;
  }
</style>
```

**Rationale**: Times New Roman has native Vietnamese support, no external font loading reduces performance overhead.

### Accessibility Checklist
- ✅ Color contrast ratio: 13.5:1 (WCAG AAA)
- ✅ Semantic HTML structure (h1, h2, section, footer)
- ✅ Touch targets 44x44px minimum
- ✅ Responsive font scaling
- ✅ Vietnamese character rendering
- ✅ Focus states for interactive elements
- ✅ Alt text for logo/images
- ✅ Lang attribute on html tag

### Performance Optimization
- No external font loading (system fonts)
- Minimal CSS (< 5KB)
- SVG logo (scalable, small filesize)
- No JavaScript required for basic layout
- Mobile-first CSS (progressive enhancement)

### Browser Support
- Modern browsers (Chrome 90+, Firefox 88+, Safari 14+, Edge 90+)
- Graceful degradation for older browsers
- CSS Grid/Flexbox fallbacks

---

## 8. Design Tokens Export

### CSS Variables
```css
:root {
  /* Colors */
  --trace-bg: #EBE5D9;
  --trace-text: #1A1A1A;
  --trace-heading: #000000;
  --trace-accent: #4A7C59;
  --trace-border: #D4CEC0;

  /* Typography */
  --trace-font-heading: 'Times New Roman', Georgia, serif;
  --trace-font-body: 'Times New Roman', Georgia, serif;
  --trace-text-xs: 13px;
  --trace-text-sm: 15px;
  --trace-text-base: 16px;
  --trace-text-lg: 24px;
  --trace-text-xl: 42px;

  /* Spacing */
  --trace-space-1: 8px;
  --trace-space-2: 16px;
  --trace-space-3: 24px;
  --trace-space-4: 32px;
  --trace-space-6: 48px;
  --trace-space-8: 64px;
  --trace-space-10: 80px;
}
```

### JavaScript/JSON Export
```json
{
  "colors": {
    "background": "#EBE5D9",
    "text": {
      "primary": "#1A1A1A",
      "heading": "#000000",
      "secondary": "#2C2C2C"
    },
    "accent": {
      "green": "#4A7C59"
    },
    "border": {
      "light": "#D4CEC0"
    }
  },
  "typography": {
    "fontFamily": {
      "heading": "'Times New Roman', Georgia, serif",
      "body": "'Times New Roman', Georgia, serif"
    },
    "fontSize": {
      "xs": "13px",
      "sm": "15px",
      "base": "16px",
      "lg": "24px",
      "xl": "42px"
    },
    "lineHeight": {
      "tight": 1.2,
      "normal": 1.6,
      "relaxed": 1.75
    }
  },
  "spacing": {
    "xs": "8px",
    "sm": "16px",
    "md": "24px",
    "lg": "32px",
    "xl": "48px",
    "2xl": "64px",
    "3xl": "80px"
  },
  "layout": {
    "containerMaxWidth": "800px"
  }
}
```

---

## 9. Key Design Principles

1. **Minimalism**: Limited color palette, generous whitespace, focused content
2. **Readability**: Large line-height (1.75), optimal line length (< 80 chars), high contrast
3. **Eco-Aesthetic**: Warm beige background, organic green accent, natural feel
4. **Editorial Quality**: Serif typography, formal structure, letter-style format
5. **Bilingual Support**: Vietnamese/English content with proper character rendering
6. **Mobile-First**: Responsive scaling, touch-friendly targets, optimized for all devices
7. **Accessibility**: WCAG AAA contrast, semantic HTML, keyboard navigation
8. **Performance**: Minimal dependencies, system fonts, fast loading

---

## 10. Next Steps for Implementation

1. **Setup Base HTML Structure**
   - Create semantic HTML with proper lang attributes
   - Implement responsive viewport meta tag
   - Add ARIA labels where needed

2. **Apply Design Tokens**
   - Create CSS variables from tokens above
   - Implement mobile-first responsive styles
   - Test Vietnamese character rendering

3. **Build Components**
   - Logo circle element
   - Title block with dual-language support
   - Content sections with proper spacing
   - Footer contact block

4. **Test Responsiveness**
   - Verify layout on mobile (320px+), tablet (768px+), desktop (1024px+)
   - Test typography scaling
   - Validate touch targets on mobile

5. **Accessibility Audit**
   - Run WAVE or axe accessibility checker
   - Test keyboard navigation
   - Verify screen reader compatibility
   - Check color contrast ratios

6. **Performance Optimization**
   - Minimize CSS
   - Optimize logo SVG
   - Lazy-load any additional images
   - Test page load speed

---

**Document Version**: 1.0
**Last Updated**: 2025-12-23
**Maintainer**: UI/UX Design Team
**Status**: Ready for Implementation
