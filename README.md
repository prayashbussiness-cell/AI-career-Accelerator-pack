# AI Career Accelerator Pack — Landing Page

A premium, high-converting, single-product landing page built with plain HTML5, CSS3, and
under 100 lines of vanilla JavaScript. No frameworks, no build step — open `index.html`
or deploy the folder as-is to GitHub Pages, Netlify, Vercel, or any static host.

## Files

```
index.html          Markup + SEO meta + JSON-LD schema
style.css            All styling (CSS variables, Grid, Flexbox, CSS-only animation)
script.js             Mobile nav, FAQ accordion, scroll-reveal, sticky CTA bar (~90 lines)
assets/
  product-hero.webp   Hero product image, optimized (WebP, ~116 KB, was 1.85 MB as PNG)
README.md
```

## Before you launch — 3 required edits

1. **Payment link.** Open `index.html`, search for `YOUR_RAZORPAY_LINK` (it appears on
   every "Buy Now" button) and replace it with your real Razorpay payment link or
   checkout URL.

2. **Canonical URL + Open Graph URL.** Search for `https://YOUR-DOMAIN.example` in
   `index.html` and replace every instance with your live domain (used in the canonical
   tag, Open Graph, Twitter Card, and the Product schema).

3. **Social preview image.** The Open Graph/Twitter meta tags point at
   `assets/product-hero.webp`. Most social platforms still prefer a JPG/PNG at
   1200×630 for previews — if you want a crisper share card, export one at that size
   and update the `og:image` / `twitter:image` tags.

Everything else (copy, testimonials, FAQ, pricing) is placeholder-free and ready to use,
but feel free to edit the copy in `index.html` to match your exact offer.

## Performance choices already made

- **One Google Font family** (Inter, 4 weights, `display=swap`, preconnected).
- **Hero image is WebP**, `fetchpriority="high"` + `<link rel="preload">` for fast LCP;
  every other image on the page is `loading="lazy"`.
- **No JavaScript animation** — all motion (fade-up, hover lift, glow, button shine,
  floating badge, background glow) is CSS `transition`/`animation` using `transform`
  and `opacity` only, so it stays off the main thread and respects
  `prefers-reduced-motion`.
- **No external libraries** — no Bootstrap/Tailwind/jQuery/React, no icon font (icons
  are inline SVG), no animation library.
- JS is a single deferred file, ~90 lines, doing only: mobile menu toggle, FAQ
  accordion, `IntersectionObserver` scroll-reveal, and a sticky mobile buy bar.
- CSS uses variables, Grid for section layout, Flexbox for components, and a mobile-first
  responsive scale (mobile → tablet → laptop → desktop).
- Semantic HTML5 landmarks, visible focus states, sufficient color contrast on gold-on-black
  text, and full meta/SEO/JSON-LD Product schema for search + social.

## Testing Lighthouse locally

```bash
npx serve .
# then run Lighthouse in Chrome DevTools against http://localhost:3000
```

Because everything is static with a single ~116 KB hero image and no render-blocking
scripts, this should land comfortably in the 90s across Performance, Accessibility,
Best Practices, and SEO — final numbers depend on your hosting's TTFB/CDN.

## Customizing colors

All theme colors live as CSS custom properties at the top of `style.css` under
`:root`. Change them once there and the whole page updates.
