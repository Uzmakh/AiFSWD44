# Glide JS Slider - Quick Reference Guide

## Current Setup Summary

Your slider is now active with these specifications:

| Feature | Value |
|---------|-------|
| **Type** | Carousel (loops continuously) |
| **Autoplay** | 4 seconds (4000ms) |
| **Animation Speed** | 800ms |
| **Slides Per View** | 1 image at a time |
| **Navigation** | Arrow buttons + keyboard + swipe |
| **Pause on Hover** | Yes |
| **Mobile Support** | Full swipe/touch support |

---

## Common Code Examples

### Example 1: Adding More Slides
```html
<li class="glide__slide">
  <img src="https://images.unsplash.com/photo-YOUR-IMAGE-ID?w=800" />
</li>
```

### Example 2: Faster Autoplay (2 seconds)
```javascript
const glide = new Glide(".glide", {
  autoplay: 2000,  // Changed from 4000
  // ... rest of config
});
```

### Example 3: Slower Animations
```javascript
const glide = new Glide(".glide", {
  animationDuration: 1200,  // Changed from 800ms
  // ... rest of config
});
```

### Example 4: Disable Autoplay (Manual Only)
```javascript
const glide = new Glide(".glide", {
  autoplay: false,  // Disable auto-rotation
  // ... rest of config
});
```

### Example 5: Add Keyboard & Remove Swipe
```javascript
const glide = new Glide(".glide", {
  keyboard: true,      // Keep keyboard nav
  bound: false,        // Disable swipe drag
  dragThreshold: 0,    // No mouse drag
  swipeThreshold: 0,   // No swipe
  // ... rest of config
});
```

### Example 6: Event Listeners
```javascript
glide.on("move", () => {
  console.log("Currently on slide:", glide.index);
});

glide.on("run.before", () => {
  console.log("Transition starting");
});

glide.on("run.after", () => {
  console.log("Transition complete");
});

glide.on("play", () => {
  console.log("Autoplay started");
});

glide.on("pause", () => {
  console.log("Autoplay paused");
});
```

### Example 7: Programmatic Control
```javascript
// Navigate to specific slide
glide.go("=2");  // Go to slide 2

// Go to next slide
glide.go(">");

// Go to previous slide
glide.go("<");

// Start autoplay
glide.play();

// Pause autoplay
glide.pause();
```

---

## CSS Customization

### Change Arrow Button Color
In `style.css`, find `.glide__arrow` and modify:
```css
.glide__arrow {
    color: #0077ff;  /* Change this to your color */
    background: rgba(255, 255, 255, 0.8);
}

.glide__arrow:hover {
    background: rgba(255, 255, 255, 1);
}
```

### Change Banner Height
```css
.cars-page-banner {
    height: 500px;  /* Adjust this value */
}

@media (max-width: 768px) {
    .cars-page-banner {
        height: 300px;  /* Mobile height */
    }
}
```

### Customize Arrow Size
```css
.glide__arrow {
    width: 50px;      /* Button diameter */
    height: 50px;
    font-size: 18px;  /* Arrow icon size */
}
```

### Change Gradient Overlay
```css
.cars-banner-content {
    background: linear-gradient(to top, rgba(0, 0, 0, 0.8), transparent);
    /* 0.8 = darkness level (0 = transparent, 1 = fully black) */
}
```

---

## Advanced Configuration Options

### All Available Options
```javascript
const glide = new Glide(".glide", {
  // Basic
  type: "carousel",                    // or "slider"
  startAt: 0,                         // Starting slide index
  perView: 1,                         // Slides visible at once
  focusAt: 0,                         // Focus position
  gap: 0,                             // Space between slides
  
  // Autoplay
  autoplay: 4000,                     // ms between slides (false to disable)
  hoverpause: true,                   // Pause on hover
  
  // Animation
  animationDuration: 800,             // Animation speed in ms
  animationTimingFunc: "ease-in-out", // Easing function
  
  // Controls
  keyboard: true,                     // Arrow key navigation
  bound: true,                        // Prevent dragging past edges
  dragThreshold: 80,                  // Desktop drag sensitivity
  swipeThreshold: 80,                 // Mobile swipe sensitivity
  touchRatio: 0.5,                    // Touch drag ratio
  peek: 0,                            // Peek at adjacent slides
});
```

---

## Troubleshooting Checklist

- [ ] CDN link loads: `https://cdn.jsdelivr.net/npm/@glidejs/glide`
- [ ] Core CSS loaded: `glide.core.min.css`
- [ ] Theme CSS loaded: `glide.theme.min.css`
- [ ] Main CSS loaded: `style.css`
- [ ] Images are accessible (check console for 404s)
- [ ] `data-glide-el="track"` on track div
- [ ] `data-glide-el="controls"` on controls div
- [ ] `data-glide-dir="<"` and `data-glide-dir=">"` on buttons
- [ ] `.glide` class on main slider container

---

## Browser Console Debug

If something isn't working, paste this in browser console (F12):

```javascript
// Check if Glide is loaded
console.log(window.Glide);

// Check current slide
console.log(glide.index);

// Check config
console.log(glide.settings);

// Check if autoplay is running
console.log(glide.autoplaying);

// Manually go to next slide
glide.go(">");
```

---

## Useful Links

- **Glide.js GitHub**: https://github.com/glidejs/glide/releases/tag/v3.7.1
- **Official Docs**: https://glidejs.com
- **API Reference**: https://glidejs.com/docs/api
- **Unsplash Images**: https://unsplash.com (where your car images come from)

---

## Summary

Your Glide slider is:
✓ Fully functional with 4 car images  
✓ Auto-rotating every 4 seconds  
✓ Touch/swipe enabled for mobile  
✓ Keyboard navigation enabled  
✓ Fully responsive  
✓ Production-ready  

**No additional setup needed!** Just open `cars.html` in your browser. 🚗
