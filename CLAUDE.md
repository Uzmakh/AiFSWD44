# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**DriveEase Car Rental System** - A multi-page static website for a car rental company built with HTML, CSS, and JavaScript.

### Architecture

**Frontend Stack**:
- **HTML5**: Multi-page structure (index, cars, services, pricing, contact, book)
- **CSS3**: Responsive design with flexbox/grid, mobile-first approach
- **JavaScript**: Glide.js slider library for image carousels
- **External Libraries**: 
  - Glide.js (v3.7.1) - image slider via CDN
  - Font Awesome (v6.5.1) - icons via CDN

**Key Structure**:
- `AiFSWD44/` - Main project folder
  - `*.html` - Page files (6 pages total)
  - `css/style.css` - Main stylesheet with all page styles organized by section
  - `css/glide.*.css` - Glide.js stylesheets (required and optional theme)
  - `doc/` - Comprehensive documentation (28 files)

### Page Organization

Each HTML page follows this pattern:
1. Header with logo, navigation, and "Book Now" button (sticky)
2. Page-specific content sections
3. Footer
4. External CDN links for dependencies (Font Awesome, Glide.js)

**Pages**:
- `index.html` - Homepage with hero section, features, cars showcase, CTA, booking process
- `cars.html` - Cars page with Glide.js slider banner and car grid
- `services.html` - Services listing with service cards
- `pricing.html` - Pricing plans with featured plan highlight
- `contact.html` - Contact form and info cards
- `book.html` - Booking form with multi-field input

### CSS Architecture

**Color Scheme**:
- Primary Blue: `#0077ff` (buttons, accents)
- Gray: `#718cab` (headings), `#868282` (body text), `#6d7884` (logo)
- Background: `#dee5eb` (light)
- White: `#fff` (cards, header)

**Responsive Breakpoints**:
- `@media (max-width: 991px)` - Tablets
- `@media (max-width: 768px)` - Mobile (optional, some pages)

**Layout Patterns**:
- Header: sticky flexbox with 8% padding
- Sections: 80px padding top/bottom, 8% horizontal padding
- Cards: flexbox/grid with 30px gaps, hover effects (translateY, scale, shadow)
- Responsive: flex-direction: column on smaller screens

### Glide.js Slider (cars.html)

**Implementation Details**:
- Located in `.cars-page-banner` section
- Configuration in `cars.html` lines 180-210
- CSS styling in `style.css` lines 304-475
- Features: autoplay (4s), keyboard nav, touch swipe, hover pause
- 4 car images from Unsplash (rotating)
- Navigation: Previous/Next buttons, auto-rotation, keyboard arrows, swipe gestures

**Key Classes**:
- `.glide` - Main slider container
- `.glide__track` - Track element (overflow hidden)
- `.glide__slides` - Flex container for slides
- `.glide__slide` - Individual slide (100% width, height)
- `.glide__arrow` - Navigation buttons (50px circles, blue #0077ff)
- `.cars-banner-content` - Text overlay with gradient

---

## Development Workflow

### Viewing Pages

Since this is a static site with no build tools:

1. **Local server** (recommended):
   ```bash
   python -m http.server 8000
   # or
   npx http-server
   ```
   Then open `http://localhost:8000/AiFSWD44/`

2. **Direct file opening**:
   Open HTML files directly in browser (works but may have CORS issues with some features)

### Modifying Pages

**Add/Edit Content**:
1. Edit `.html` file directly
2. Modify `.css` for styling (keep organized by page section)
3. Refresh browser to see changes

**Styling Guidelines**:
- Use existing color palette (avoid adding new colors)
- Maintain 8% horizontal padding on sections
- Keep hover effects consistent (translateY -10px or scale 1.05)
- Update media queries if adding new layout patterns
- Follow existing comment structure (/* Section Name */)

### Common Tasks

**Add a new page**:
1. Create `page-name.html` in `AiFSWD44/`
2. Copy header/footer structure from existing page
3. Add styles to `css/style.css` under page-specific section
4. Link from navigation menu in all pages

**Modify Glide slider**:
- Configuration: Edit lines 190-199 in `cars.html`
- Common changes:
  - `autoplay: 4000` → change for different interval
  - `animationDuration: 800` → change animation speed
  - `keyboard: false` → disable keyboard nav
  - `autoplay: false` → disable autoplay

**Update styling**:
- Colors in `style.css` are centralized (search for hex values)
- Responsive breakpoints at end of each section
- Card/button hover effects defined near their main styles

---

## Important Files & Locations

| File | Purpose |
|------|---------|
| `AiFSWD44/css/style.css` | All styling (1100+ lines) |
| `AiFSWD44/cars.html` | Glide.js slider implementation |
| `doc/GLIDE_QUICK_REFERENCE.md` | 50+ Glide.js code examples |
| `doc/CODE_REFERENCE.md` | Exact code changes documented |
| `doc/00_START_HERE.md` | Quick start guide |

---

## External Dependencies

**CDN Links** (in each HTML file):
- Font Awesome: `https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css`
- Glide.js (cars.html only): `https://cdn.jsdelivr.net/npm/@glidejs/glide`

**Glide.js CSS Files** (local):
- `css/glide.core.min.css` - Required
- `css/glide.theme.min.css` - Optional theme

---

## Notes for Future Work

1. **No build tools**: This is vanilla HTML/CSS/JS. No npm, webpack, or compilation needed.
2. **Static site**: No backend server required. Can be deployed as-is to any static host.
3. **External images**: All car images from Unsplash CDN (ensure internet access).
4. **Cross-browser**: Tested on Chrome, Firefox, Safari, Edge (see documentation).
5. **Responsive**: Mobile-first design with CSS media queries (not Bootstrap/Tailwind).
6. **Documentation**: 28 comprehensive guides in `doc/` folder covering all aspects.

---

## Quick Reference

**Glide.js Configuration** (cars.html lines 184-199):
- `type: "carousel"` - Continuous loop
- `autoplay: 4000` - Auto-advance every 4 seconds
- `animationDuration: 800` - 800ms slide animation
- `keyboard: true` - Arrow key navigation
- `swipeThreshold: 80` - Mobile swipe sensitivity

**CSS Organization** (style.css):
- Lines 1-50: Global styles, header
- Lines 77-280: Homepage sections
- Lines 304-475: Cars page (includes Glide styling)
- Lines 434-598: Services page
- Lines 600-813: Pricing page
- Lines 815-987: Contact page
- Lines 1001-1142: Booking page
- Lines 989-1000+: Responsive media queries

**Color Palette**:
- Primary: `#0077ff` (blue)
- Secondary: `#718cab` (muted blue)
- Text: `#868282` (gray)
- Background: `#dee5eb` (light gray)
- Dark: `#111` (footer)

