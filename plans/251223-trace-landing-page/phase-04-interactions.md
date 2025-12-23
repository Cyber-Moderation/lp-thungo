# Phase 4: Animations & Interactions

**Duration**: 15-20 minutes
**Dependency**: Phase 3 (Responsive Design)
**Output**: Smooth scroll animations, hover effects, and interactive behaviors

---

## Objectives

1. Implement Intersection Observer for scroll animations
2. Create fade-in effects for content sections
3. Add hover states for interactive elements
4. Configure smooth scroll behavior
5. Implement staggered animation delays
6. Ensure animations respect prefers-reduced-motion

---

## Animation Strategy

### Philosophy
- **Subtle and elegant**: Minimal motion, maximum impact
- **Performance-first**: CSS transitions over JavaScript animations
- **Accessible**: Respect user motion preferences
- **Progressive enhancement**: Content visible without JavaScript

---

## 4.1 Scroll Animations (Intersection Observer)

### HTML - Add animation classes

```html
<!-- Add fade-in classes to sections -->
<section class="content-section fade-in mb-12 md:mb-16">
  <!-- Content -->
</section>

<div class="about-sections fade-in mb-12 md:mb-16">
  <!-- About cards -->
</div>

<footer class="footer-section fade-in mt-12 md:mt-16">
  <!-- Footer -->
</footer>
```

### CSS - Fade-in animation styles

```css
/* Initial state - hidden */
.fade-in {
  opacity: 0;
  transform: translateY(30px);
  transition: opacity 0.8s ease, transform 0.8s ease;
}

/* Visible state - triggered by Intersection Observer */
.fade-in.visible {
  opacity: 1;
  transform: translateY(0);
}

/* Staggered delays for sequential animations */
.fade-in:nth-child(1) {
  transition-delay: 0ms;
}

.fade-in:nth-child(2) {
  transition-delay: 100ms;
}

.fade-in:nth-child(3) {
  transition-delay: 200ms;
}

.fade-in:nth-child(4) {
  transition-delay: 300ms;
}

.fade-in:nth-child(5) {
  transition-delay: 400ms;
}

/* Respect user motion preferences */
@media (prefers-reduced-motion: reduce) {
  .fade-in {
    opacity: 1;
    transform: none;
    transition: none;
  }
}
```

### JavaScript - Intersection Observer implementation

```html
<script>
  // Intersection Observer for scroll animations
  document.addEventListener('DOMContentLoaded', function() {
    // Check if user prefers reduced motion
    const prefersReducedMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches;

    if (prefersReducedMotion) {
      // Skip animations if user prefers reduced motion
      document.querySelectorAll('.fade-in').forEach(el => {
        el.classList.add('visible');
      });
      return;
    }

    // Create Intersection Observer
    const observerOptions = {
      root: null,
      rootMargin: '0px 0px -100px 0px', // Trigger 100px before element enters viewport
      threshold: 0.1 // Trigger when 10% of element is visible
    };

    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
          // Optional: Stop observing after animation triggers (one-time animation)
          // observer.unobserve(entry.target);
        }
      });
    }, observerOptions);

    // Observe all elements with fade-in class
    document.querySelectorAll('.fade-in').forEach(el => {
      observer.observe(el);
    });
  });
</script>
```

---

## 4.2 Hover Effects

### Link Hover States

```css
/* Base link styles */
a {
  color: var(--color-text-primary);
  text-decoration: none;
  border-bottom: 1px solid var(--color-border-light);
  transition: color 0.3s ease, border-color 0.3s ease, transform 0.2s ease;
  display: inline-block;
}

/* Hover state */
a:hover {
  color: var(--color-accent-green);
  border-bottom-color: var(--color-accent-green);
  transform: translateY(-1px);
}

/* Focus state for accessibility */
a:focus {
  outline: 2px solid var(--color-accent-green);
  outline-offset: 2px;
}

/* Active state */
a:active {
  transform: translateY(0);
}
```

### Logo Circle Hover

```css
.logo-circle {
  transition: transform 0.4s ease, box-shadow 0.4s ease;
  cursor: default;
}

.logo-circle:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 20px rgba(74, 124, 89, 0.15);
}
```

### About Card Hover Effects

```css
.about-card {
  transition: transform 0.3s ease, box-shadow 0.3s ease, border-color 0.3s ease;
  cursor: pointer;
}

.about-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.12);
  border-color: var(--color-accent-green);
}

/* Reduce motion for users who prefer it */
@media (prefers-reduced-motion: reduce) {
  .about-card:hover {
    transform: none;
  }
}
```

---

## 4.3 Smooth Scroll Behavior

### CSS Smooth Scroll

```css
/* Enable smooth scrolling globally */
html {
  scroll-behavior: smooth;
}

/* Disable for users who prefer reduced motion */
@media (prefers-reduced-motion: reduce) {
  html {
    scroll-behavior: auto;
  }
}
```

### JavaScript Enhanced Smooth Scroll (Optional)

```html
<script>
  // Enhanced smooth scroll for anchor links
  document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', function(e) {
      const targetId = this.getAttribute('href');

      // Skip if href is just "#"
      if (targetId === '#') return;

      const targetElement = document.querySelector(targetId);

      if (targetElement) {
        e.preventDefault();

        // Smooth scroll to target
        targetElement.scrollIntoView({
          behavior: 'smooth',
          block: 'start'
        });

        // Update URL without jumping
        history.pushState(null, null, targetId);
      }
    });
  });
</script>
```

---

## 4.4 Micro-Interactions

### Button/Link Ripple Effect (Optional)

```css
/* Subtle scale effect on click */
a,
.about-card {
  position: relative;
}

a:active,
.about-card:active {
  transform: scale(0.98);
}
```

### Section Heading Underline Animation

```css
.section-heading {
  position: relative;
  display: inline-block;
}

/* Animated underline */
.section-heading::after {
  content: '';
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 0;
  height: 2px;
  background-color: var(--color-accent-green);
  transition: width 0.6s ease;
}

.section-heading.visible::after {
  width: 60px;
}
```

---

## 4.5 Loading Animation (Optional)

### Page Load Fade-In

```css
/* Body fade-in on page load */
body {
  animation: pageLoad 0.6s ease;
}

@keyframes pageLoad {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

/* Respect reduced motion preference */
@media (prefers-reduced-motion: reduce) {
  body {
    animation: none;
  }
}
```

---

## 4.6 Complete JavaScript Implementation

```html
<script>
  (function() {
    'use strict';

    // Check for reduced motion preference
    const prefersReducedMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches;

    // ==========================================
    // 1. Intersection Observer for Scroll Animations
    // ==========================================
    function initScrollAnimations() {
      if (prefersReducedMotion) {
        // Make all elements visible immediately
        document.querySelectorAll('.fade-in').forEach(el => {
          el.classList.add('visible');
        });
        return;
      }

      const observerOptions = {
        root: null,
        rootMargin: '0px 0px -100px 0px',
        threshold: 0.1
      };

      const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            entry.target.classList.add('visible');
          }
        });
      }, observerOptions);

      // Observe all fade-in elements
      document.querySelectorAll('.fade-in').forEach(el => {
        observer.observe(el);
      });

      // Observe section headings for underline animation
      document.querySelectorAll('.section-heading').forEach(el => {
        observer.observe(el);
      });
    }

    // ==========================================
    // 2. Smooth Scroll for Anchor Links
    // ==========================================
    function initSmoothScroll() {
      document.querySelectorAll('a[href^="#"]').forEach(anchor => {
        anchor.addEventListener('click', function(e) {
          const targetId = this.getAttribute('href');
          if (targetId === '#') return;

          const targetElement = document.querySelector(targetId);
          if (targetElement) {
            e.preventDefault();
            targetElement.scrollIntoView({
              behavior: prefersReducedMotion ? 'auto' : 'smooth',
              block: 'start'
            });
            history.pushState(null, null, targetId);
          }
        });
      });
    }

    // ==========================================
    // 3. Initialize on DOM Ready
    // ==========================================
    document.addEventListener('DOMContentLoaded', function() {
      initScrollAnimations();
      initSmoothScroll();
    });

  })();
</script>
```

---

## Performance Optimization

### GPU Acceleration

```css
/* Force GPU acceleration for smooth animations */
.fade-in,
.logo-circle,
.about-card {
  will-change: transform, opacity;
}

/* Remove will-change after animation completes */
.fade-in.visible {
  will-change: auto;
}
```

### Debouncing Scroll Events (If Needed)

```javascript
// Only if using custom scroll handlers (not needed with Intersection Observer)
function debounce(func, wait) {
  let timeout;
  return function executedFunction(...args) {
    clearTimeout(timeout);
    timeout = setTimeout(() => func(...args), wait);
  };
}
```

---

## Accessibility Considerations

### Motion Preferences

```css
/* Always respect user motion preferences */
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```

### Focus Management

```css
/* Ensure focus states are always visible */
*:focus-visible {
  outline: 2px solid var(--color-accent-green);
  outline-offset: 2px;
}

/* Hide outline for mouse users, show for keyboard users */
*:focus:not(:focus-visible) {
  outline: none;
}
```

---

## Testing Checklist

- [ ] Fade-in animations trigger on scroll
- [ ] Staggered delays create smooth sequence
- [ ] Hover effects work on desktop
- [ ] Touch interactions work on mobile
- [ ] Smooth scroll behavior functions correctly
- [ ] Animations respect prefers-reduced-motion
- [ ] No janky scrolling or layout shifts
- [ ] Focus states visible for keyboard navigation
- [ ] Animations perform well on low-end devices

---

## Deliverables

✅ Intersection Observer implementation
✅ Fade-in scroll animations
✅ Hover states for all interactive elements
✅ Smooth scroll behavior
✅ Staggered animation delays
✅ Motion preference respect
✅ Accessible focus states
✅ Performance-optimized animations

---

## Next Phase

Proceed to **Phase 5: Polish & Optimization** for final quality checks, SEO optimization, and production preparation.
