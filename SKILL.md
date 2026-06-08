---
name: social-post-gen
description: Generate minimal, interactive HTML post pages from user-provided images and topics. Covers tech showcases, event recaps, gathering reviews, and social sharing pages. Use when the user asks to create a post, article page, showcase page, event recap, gathering review, or similar image-based pages. Triggers on requests like "生成帖子", "做个页面", "展示图片", "活动回顾", "聚餐帖子", "活动介绍页", etc. Style should be modern, minimal, and interactive.
---

# Social Post Generator

Generate minimal, interactive HTML pages from user-provided images and topics. Zero JavaScript, pure CSS.

## Core Rules

- **Zero JavaScript** — strictly CSS and HTML only. No `<script>` tags, no JS APIs.
- **No page header/footer** — start directly with content, no navigation bars or site footers.
- **Rich interaction via CSS only** — hover effects, scroll-triggered reveals, smooth transitions, gallery switches via `:checked`.
- **Image handling** — always preserve original aspect ratio (`object-fit: contain` or natural height). Never stretch or squash images. Use CSS Grid/Flexbox for layout.
- **No external dependencies** — all CSS inline. Image URLs may be placeholders for image beds.

## Page Types

### 1. Tech Showcase / Topic Post
Apple-inspired aesthetic. Generous whitespace, refined typography, subtle gradients, glassmorphism, rounded corners (~20-24px). Tech feel but soft — avoid cyberpunk/hardcore tech.

### 2. Event Recap / Gathering Review
Result-oriented post (not invitation). Warm, dopamine-friendly palette. Gallery-style image reveal where users click text/numbers to view photos. Mystery and elegance.

## Page Structure

### Tech Showcase
1. **Topic introduction** — brief, plain concept explanation (not too text-heavy)
2. **Concept imagery** — sprinkle images throughout the text section, not just at the end
3. **User image gallery** — masonry-style or asymmetric grid showcasing provided images
4. **Optional CTA** — subtle closing action area if contextually appropriate

### Event Recap / Gathering Review
1. **Hero** — event title + date/venue (as narrative, not invitation) + one-sentence summary
2. **Atmosphere note** — brief paragraph about the vibe (no agenda, no host, just people)
3. **Gallery reveal** — one large image frame + clickable text/number navigation. Default shows 1st image only; others revealed on click. Captions fade in with images.
4. **Closing quote** — one poetic line. No signup/fee/RSVP.

## Style Rotation

Each invocation should pick a different visual style from this pool (cycle through them):

| # | Name | Key Traits |
|---|------|-----------|
| 1 | **Deep Space** | Dark bg (#050507), floating colored orbs, blue/purple ambient glow, glass cards |
| 2 | **Paper Light** | Off-white bg (#fafafa), subtle shadows, warm gray text, clean editorial layout |
| 3 | **Aurora** | Gradient mesh background (green/teal/blue), light theme, soft color transitions |
| 4 | **Monochrome** | Black & white with single accent color, high contrast, Swiss typography |
| 5 | **Silicon Dawn** | Soft peach/sand background, rose gold accents, warm tech aesthetic |
| 6 | **Warm Gathering** | Warm cream bg (#FFF8F0), bronze/dopamine orange accents (#FF6B35), serif headlines, framed gallery |

## Interaction Patterns (CSS Only)

- **Scroll reveal**: CSS Scroll-driven Animations (`animation-timeline: view()`) with `@supports` graceful fallback (if unsupported, elements show immediately without animation).
- **Hover lift**: `transform: translateY(-4px)` + `box-shadow` on cards/images
- **Image zoom**: `transform: scale(1.03)` on hover with `overflow: hidden`
- **Ambient motion**: Slow CSS keyframe animations on background elements (orbs, gradients)
- **Stagger**: Use `animation-range` offsets (entry 10% cover 30%, entry 15% cover 35%, etc.) for sequential reveals
- **Pulse/glow**: Subtle `box-shadow` or `opacity` keyframe animations on accent elements
- **Gallery switch (radio-based)**: Hidden `<input type="radio">` + `<label>` navigation. `opacity` + `transform: scale()` + `filter: grayscale()` transitions for image reveal. Only one image visible by default; others revealed on click.

## Image Layout Guidelines

- **Single image**: Full width with generous border-radius, max-height ~500px, `object-fit: contain`
- **2 images**: Side by side on desktop, stacked on mobile
- **3+ images**: Asymmetric grid (e.g., 12-column CSS Grid with varying spans: 7+5, 6+6, etc.)
- **Gallery (masonry)**: Masonry feel with mixed column spans. Each card has hover overlay with caption.
- **Gallery (reveal)**: One large framed image area (16:9 or 4:3) + text/number navigation below. Click to switch.
- **Aspect ratio**: Never set fixed height that distorts images. Let images determine height or use `aspect-ratio` with `object-fit: cover` only if the image is purely decorative.

## Typography

```css
font-family: -apple-system, BlinkMacSystemFont, "SF Pro Display", "Segoe UI", "PingFang SC", sans-serif;
```

- Headlines: `font-weight: 700`, `letter-spacing: -0.03em`, gradient text fill on hero
- Body: `font-size: 17px`, `line-height: 1.8`, `color: #86868b` on secondary text
- Small labels: `font-size: 13px`, uppercase or all-caps with wide tracking
- For **Warm Gathering** style: use serif font for headlines: `"Noto Serif SC", "Songti SC", serif`

## Workflow

1. Parse user's topic, images, and page type (tech showcase vs event recap)
2. Pick a style from the rotation pool (different from last used if known)
3. Write semantic HTML with no external dependencies except image URLs
4. Implement all animations and interactions with CSS only
5. Ensure images keep original proportions
6. Output complete standalone `.html` file with **zero JavaScript**

## Assets

- `assets/template.html` — complete working example (Deep Space variant) demonstrating all patterns.
- `assets/gathering-template.html` — complete working example (Warm Gathering / Event Recap variant) with CSS-only gallery reveal.
