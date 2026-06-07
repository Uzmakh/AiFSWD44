# Glide JS Slider - Complete Code Reference

## 📝 Exact Code Changes Made

### File 1: cars.html - JavaScript Section

**Location**: Lines 180-210 at the end of `<body>` before `</body>`

```html
<!-- glide.js link -->
<script src="https://cdn.jsdelivr.net/npm/@glidejs/glide"></script>
<script>
  // Initialize Glide slider with enhanced configuration
  const glide = new Glide(".glide", {
    type: "carousel",           // or "slider" for non-looping
    startAt: 0,                 // start at slide 0
    perView: 1,                 // show 1 slide at a time
    focusAt: 0,                 // focus on the center slide
    gap: 0,                     // gap between slides
    autoplay: 4000,             // autoplay every 4 seconds
    hoverpause: true,           // pause on hover
    animationDuration: 800,     // animation duration in ms
    animationTimingFunc: "ease-in-out", // easing function
    peek: 0,                    // don't peek at next/prev slides
    keyboard: true,             // enable keyboard navigation (arrow keys)
    bound: true,                // bound the dragging
    dragThreshold: 80,          // drag threshold
    swipeThreshold: 80,         // swipe threshold
    touchRatio: 0.5,            // touch ratio for dragging
  });

  glide.mount();

  // Optional: Add event listeners for additional functionality
  glide.on("move", () => {
    console.log("Slide changed to:", glide.index);
  });

  glide.on("run.before", () => {
    console.log("Transition starting");
  });

  glide.on("run.after", () => {
    console.log("Transition complete");
  });
</script>
```

---

### File 2: style.css - Glide Slider CSS

**Location**: Lines 304-418 in `css/style.css`

```css
/* ==========================
   CARS PAGE CSS
========================== */

/* Glide Slider Styling */
.cars-page-banner {
    position: relative;
    height: 500px;
    overflow: hidden;
}

.slider-container {
    position: relative;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
}

.glide {
    position: relative;
    width: 100%;
    height: 100%;
}

.glide__track {
    overflow: hidden;
    width: 100%;
    height: 100%;
}

.glide__slides {
    display: flex;
    list-style: none;
    margin: 0;
    padding: 0;
    height: 100%;
}

.glide__slide {
    width: 100%;
    height: 100%;
    flex-shrink: 0;
    position: relative;
}

.glide__slide img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
}

/* Glide Arrow Controls */
.glide__arrows {
    position: absolute;
    top: 50%;
    width: 100%;
    transform: translateY(-50%);
    display: flex;
    justify-content: space-between;
    padding: 0 20px;
    z-index: 10;
    pointer-events: none;
}

.glide__arrow {
    pointer-events: all;
    background: rgba(255, 255, 255, 0.8);
    border: none;
    width: 50px;
    height: 50px;
    border-radius: 50%;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 18px;
    font-weight: bold;
    color: #0077ff;
    transition: all 0.3s ease;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
}

.glide__arrow:hover {
    background: rgba(255, 255, 255, 1);
    transform: scale(1.1);
    box-shadow: 0 6px 20px rgba(0, 0, 0, 0.3);
}

.glide__arrow--left {
    margin-right: auto;
}

.glide__arrow--right {
    margin-left: auto;
}

/* Banner Content Overlay */
.cars-banner-content {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    background: linear-gradient(to top, rgba(0, 0, 0, 0.8), transparent);
    color: white;
    padding: 60px 8%;
    animation: fadeUp 1s ease;
    z-index: 5;
}

.cars-banner-content h1 {
    font-size: 60px;
    margin-bottom: 15px;
    color: #fff;
}

.cars-banner-content p {
    font-size: 20px;
    color: rgba(255, 255, 255, 0.9);
}
```

**Plus Responsive Media Queries** (lines 419-475):

```css
/* Responsive */

@media (max-width: 991px) {
    .hero {
        flex-direction: column;
        text-align: center;
    }

    .hero-image img {
        width: 100%;
        margin-top: 40px;
    }

    .feature-container,
    .car-container {
        flex-direction: column;
    }

    nav {
        display: none;
    }

    /* Responsive Glide Slider */
    .cars-page-banner {
        height: 400px;
    }

    .glide__arrow {
        width: 45px;
        height: 45px;
        font-size: 16px;
    }

    .cars-banner-content {
        padding: 40px 5%;
    }

    .cars-banner-content h1 {
        font-size: 42px;
    }

    .cars-banner-content p {
        font-size: 16px;
    }
}

@media (max-width: 768px) {
    .cars-page-banner {
        height: 300px;
    }

    .glide__arrows {
        padding: 0 10px;
    }

    .glide__arrow {
        width: 40px;
        height: 40px;
        font-size: 14px;
    }

    .cars-banner-content {
        padding: 30px 5%;
    }

    .cars-banner-content h1 {
        font-size: 32px;
        margin-bottom: 10px;
    }

    .cars-banner-content p {
        font-size: 14px;
    }
}

@media (max-width: 480px) {
    .cars-page-banner {
        height: 250px;
    }

    .glide__arrow {
        width: 35px;
        height: 35px;
        font-size: 12px;
    }

    .glide__arrows {
        padding: 0 5px;
    }

    .cars-banner-content {
        padding: 20px 3%;
    }

    .cars-banner-content h1 {
        font-size: 24px;
        margin-bottom: 8px;
    }

    .cars-banner-content p {
        font-size: 12px;
    }
}
```

---

## 🔄 Before vs After Comparison

### BEFORE: Basic Glide Setup
```javascript
const config = {
  type: "carousel",
  perView: 2,
};
new Glide(".glide", config).mount();
```

### AFTER: Enhanced Glide Setup
```javascript
const glide = new Glide(".glide", {
  type: "carousel",              // ✨ Continuous loop
  startAt: 0,                    // ✨ Begin at first slide
  perView: 1,                    // ✨ Show one at a time (fixed)
  focusAt: 0,
  gap: 0,
  autoplay: 4000,                // ✨ Auto-rotate every 4 seconds (NEW)
  hoverpause: true,              // ✨ Pause on hover (NEW)
  animationDuration: 800,        // ✨ Smooth animation (NEW)
  animationTimingFunc: "ease-in-out", // ✨ Easing function (NEW)
  peek: 0,
  keyboard: true,                // ✨ Keyboard nav enabled (NEW)
  bound: true,
  dragThreshold: 80,             // ✨ Desktop drag (NEW)
  swipeThreshold: 80,            // ✨ Mobile swipe (NEW)
  touchRatio: 0.5,               // ✨ Touch sensitivity (NEW)
});

glide.mount();

// ✨ Event listeners (NEW)
glide.on("move", () => {
  console.log("Slide changed to:", glide.index);
});
```

**Changes Made**: ✅ 9 new features added, 1 bug fixed (perView: 2 → 1)

---

## 🎯 Configuration Options Explained

```javascript
{
  // NAVIGATION & TYPE
  type: "carousel",              // Loops continuously. Alternatives: "slider"
  startAt: 0,                    // Begin at slide index 0 (first slide)
  perView: 1,                    // Show 1 slide at a time
  focusAt: 0,                    // Focus/center on this slide
  
  // AUTOPLAY
  autoplay: 4000,                // Auto-advance every 4000ms (4 seconds)
                                 // Set to false to disable autoplay
  hoverpause: true,              // Stop autoplay when mouse hovers
  
  // SPACING
  gap: 0,                        // No space between slides
                                 // Set to 20 for 20px gaps
  
  // ANIMATION
  animationDuration: 800,        // Slide transition takes 800ms
  animationTimingFunc: "ease-in-out", // Smooth easing function
  
  // CONTROLS
  keyboard: true,                // Arrow keys work
                                 // Set to false to disable
  bound: true,                   // Smooth boundary handling
  peek: 0,                       // Don't show next/prev slides
                                 // Set to 50 to peek 50px
  
  // TOUCH/DRAG
  dragThreshold: 80,             // Desktop drag sensitivity
  swipeThreshold: 80,            // Mobile swipe sensitivity
  touchRatio: 0.5,               // How far touch moves slider
}
```

---

## 📊 CSS Breakdown

| CSS Class | Purpose | Key Properties |
|-----------|---------|-----------------|
| `.cars-page-banner` | Main banner container | 500px height, relative position |
| `.glide` | Slider wrapper | 100% width/height, relative |
| `.glide__track` | Slide container | overflow hidden for clipping |
| `.glide__slides` | Slides list | flex display, height 100% |
| `.glide__slide` | Individual slide | width 100%, height 100% |
| `.glide__slide img` | Slide image | object-fit cover, display block |
| `.glide__arrows` | Arrow controls container | absolute position, flex layout |
| `.glide__arrow` | Arrow buttons | 50px circles, hover effects |
| `.cars-banner-content` | Text overlay | absolute bottom, gradient bg |

---

## 🎨 Color & Size Reference

```css
/* Colors */
Background (Arrow): rgba(255, 255, 255, 0.8)  /* Semi-transparent white */
Arrow Icon: #0077ff                             /* Blue */
Overlay: rgba(0, 0, 0, 0.8)                    /* 80% dark overlay */
Text: white                                     /* White text */

/* Sizes - Desktop */
Banner Height: 500px
Arrow Size: 50px × 50px
Arrow Font: 18px

/* Sizes - Tablet (≤991px) */
Banner Height: 400px
Arrow Size: 45px × 45px
Arrow Font: 16px

/* Sizes - Mobile (≤768px) */
Banner Height: 300px
Arrow Size: 40px × 40px
Arrow Font: 14px

/* Sizes - Small Mobile (≤480px) */
Banner Height: 250px
Arrow Size: 35px × 35px
Arrow Font: 12px
```

---

## 🚀 How to Modify

### 1. Change Autoplay Speed
```javascript
autoplay: 2000,  // 2 seconds instead of 4
```

### 2. Change Animation Speed
```javascript
animationDuration: 1200,  // 1.2 seconds instead of 0.8
```

### 3. Disable Autoplay
```javascript
autoplay: false,  // Manual navigation only
```

### 4. Change Button Color
```css
.glide__arrow {
    color: #ff0000;  /* Red instead of blue */
}
```

### 5. Change Banner Height
```css
.cars-page-banner {
    height: 600px;  /* Taller banner */
}
```

### 6. Add More Slides
```html
<li class="glide__slide">
  <img src="https://images.unsplash.com/photo-NEW-ID?w=800" />
</li>
```

---

## ✅ Files Updated

| File | Lines | Changes |
|------|-------|---------|
| `cars.html` | 180-210 | JavaScript initialization added |
| `style.css` | 304-475 | Complete Glide CSS + responsive styles |

---

## 🎉 Result

Your slider now has:
- ✅ Automatic image rotation (4 seconds)
- ✅ Click navigation (prev/next buttons)
- ✅ Keyboard navigation (arrow keys)
- ✅ Touch/swipe support (mobile)
- ✅ Smooth animations (800ms)
- ✅ Hover pause (pauses on mouse hover)
- ✅ Responsive design (all screen sizes)
- ✅ Beautiful UI with gradient overlay

---

## 📚 Reference Documents

All documentation files created:
1. `GLIDE_SLIDER_SETUP.md` - Setup overview
2. `GLIDE_QUICK_REFERENCE.md` - Code snippets
3. `GLIDE_IMPLEMENTATION_COMPLETE.md` - Full guide
4. `SUMMARY.md` - Project summary
5. `CODE_REFERENCE.md` - This file

---

## 🎯 Quick Start

1. Open `cars.html` in your browser
2. See 4 car images rotating automatically
3. Click arrows or press keyboard keys to navigate
4. Swipe on mobile to change slides
5. All features work out of the box! ✨
