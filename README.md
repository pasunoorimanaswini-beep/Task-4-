# Task 4 – Make a Website Mobile-Friendly Using CSS Media Queries

**Web Development Internship – Elevate Labs**

A desktop-only landing page (Brewhouse Roasters) converted into a responsive layout using CSS media queries.

## Files
| File | Purpose |
|---|---|
| `index.html` | Page markup (includes the viewport meta tag and a small nav-toggle script) |
| `style.css` | Desktop styles + `@media (max-width: 768px)` and `@media (max-width: 480px)` |
| `images/hero.svg` | Hero image (fixed 480px wide on desktop, scales down on mobile) |

## What I did (following the task hints)
1. **Opened the page in VS Code.**
2. **Identified fixed-width elements:** `.container` (1100px), `.hero-text` (520px), hero image (480px), `.card` (340px), `.col` (530px), `.table-wrap` (1100px), `.contact-form` (600px), footer columns (250px).
3. **Wrote media queries** for `max-width: 768px` (tablet/phone) and `max-width: 480px` (small phones).
4. **Adjusted layout:** fixed `px` widths became `100%`, columns stack vertically (`flex-direction: column`), headings are smaller (`h1` 3rem → 2rem → 1.65rem), footer becomes a 2-column then 1-column grid.
5. **Nav menu collapses:** on mobile the links hide behind a **Menu** button and stack vertically when opened.
6. **Tested with Chrome DevTools** device toolbar (iPhone SE, iPhone 12 Pro, Pixel 7, iPad Mini) and by dragging the viewport from 1200px down to 320px.
7. **Fixed overflow:** the prices table scrolls horizontally inside its own wrapper, so the page itself never scrolls sideways.
8. **Images scale:** `img { max-width: 100%; height: auto; }`.

Also added: viewport meta tag, `box-sizing: border-box`, `rem` font sizes, visible keyboard focus styles, and larger tap targets on mobile.

## How to run
Open `index.html` in a browser. Press **F12 → Ctrl+Shift+M** (Chrome DevTools device toolbar) to test mobile sizes.

## Key concepts used
Media queries, responsive web design, viewport meta tag, CSS units (`%`, `rem`), flexbox, CSS grid.

## Interview questions – short answers
1. **What are media queries?** CSS rules that apply only when conditions such as viewport width are met, e.g. `@media (max-width: 768px) { ... }`.
2. **Mobile-first vs desktop-first?** Mobile-first writes base styles for phones and adds `min-width` queries for larger screens. Desktop-first starts with the full layout and uses `max-width` queries to simplify it (this project).
3. **How do you test responsiveness?** Chrome DevTools device toolbar, resizing the browser window, and testing on real devices.
4. **Best units?** `%`, `rem`/`em`, `vw`/`vh`, `fr`, and `clamp()`. Avoid fixed `px` for widths.
5. **Viewport meta tag?** `<meta name="viewport" content="width=device-width, initial-scale=1.0">` tells mobile browsers to use the device width instead of a zoomed-out ~980px canvas.
6. **How does flexbox help?** `flex-wrap`, `flex-direction`, and `flex: 1` let items resize, wrap, or stack without fixed widths.
7. **Absolute vs relative units?** Absolute (`px`, `cm`, `pt`) are fixed. Relative (`%`, `em`, `rem`, `vw`) depend on a parent, root font size, or viewport.
8. **Images?** `max-width: 100%; height: auto;`, plus `srcset`/`<picture>` for different sizes.
9. **Adaptive vs responsive?** Adaptive switches between a few fixed layouts at set breakpoints. Responsive uses fluid grids and flexible units so the layout changes continuously.
10. **CSS grid responsiveness?** `grid-template-columns: repeat(auto-fit, minmax(250px, 1fr))` creates columns that wrap automatically; media queries can also redefine the grid.
