# Ganesh Gone — Portfolio

A single-page developer portfolio: canvas frame-sequence hero, floating glass navbar, About, Projects, Tech Stack, Reviews, and Contact — built in vanilla HTML/CSS/JS, no frameworks.

## Files

- `index.html` — markup only
- `style.css` — all styling, including design tokens (`:root` custom properties)
- `script.js` — hero canvas sequence, data-driven rendering (projects/tech/reviews/socials), nav behavior, and the new interaction layer described below

## What's new in this pass

**Scroll-reveal animations** — section headers, the About copy, stat cards, project cards, tech badges, review cards, and the contact block fade + slide up as they enter the viewport, with a light stagger so groups of cards don't animate as one flat block. Uses `IntersectionObserver`; each element only animates once.

**Tilt-on-hover project cards** — the project cards in `#projectsGrid` tilt in 3D toward the cursor position and snap back on mouse-leave. Desktop/mouse only.

**Custom magnetic cursor** — a small dot plus a trailing ring replace the system cursor and expand when hovering links, buttons, project cards, tech badges, and social links. Desktop/mouse only.

**Animated stat counters** — the four numbers in the About section (`4+`, `30+`, `12`, `100%`) count up from zero the first time they scroll into view, preserving their original suffix.

All of the above are skipped automatically for:
- Touch/coarse-pointer devices (tilt, cursor)
- `prefers-reduced-motion: reduce` (everything — reveals show immediately, counters set their final value instantly)

## Before you deploy

The file still has a few placeholders to swap in:

- **Projects, tech stack, testimonials, socials** — edit the arrays near the top of `script.js` (`projects`, `techStack`, `testimonials`, `socials`). Repo/live links currently point at `your-username` placeholders.
- **Resume** — `#contact` links to `/assets/Ganesh-Gone-Resume.pdf`; add the actual file at that path.
- **Project preview images** — each card currently renders a glyph/emoji; swap the `<span class="glyph">` in `renderProjects()` (in `script.js`) for an `<img>` once you have real screenshots.

## Browser support notes

- Canvas frame sequence, `IntersectionObserver`, and the cursor/tilt logic all have graceful fallbacks (reveals default to visible, counters default to final value) if a browser lacks a feature.
- No build step — open `index.html` directly or serve the folder with any static file server.
- 
