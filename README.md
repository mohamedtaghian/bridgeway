# Bridgeway — Landing Page

## 1. How to Run the Project

### Prerequisites

- Node.js 22.18.0+ or >=24.12.0
- npm 10+

### Setup & Development

```bash
# 1. Install dependencies
npm install

# 2. Start development server (hot-reload enabled)
npm run dev

# 3. Build for production
npm run build

# 4. Preview production build locally
npm run preview

# 5. Run linter and formatting checks
npm run lint
```

---

## 2. Project Structure & Architecture

The project strictly follows the rule of **Vue.js and Tailwind only**, without any third-party UI kits, icon packs, or animation libraries.

```text
bridgeway/
├── public/
├── src/
│   ├── assets/
│   │   ├── images/              # High-resolution image assets (hero-bridge, pos-terminal)
│   │   ├── svg/                 # Extracted vector icons, partner logos, and graphic shapes
│   │   └── main.css             # Tailwind v4 configuration, theme tokens, and custom keyframes
│   ├── components/
│   │   ├── Navbar.vue           # Header navigation, brand logo, anchor links, and CTA button
│   │   ├── HeroSection.vue      # Hero banner (dual organic curves, bridge graphic, headline, arrow CTA)
│   │   ├── LogoTicker.vue       # Partner logos with infinite marquee animation & edge fade masks
│   │   ├── BenefitsSection.vue  # 6 alternating checkerboard benefit cards (dark/light)
│   │   ├── CtaSection.vue       # POS terminal image, floating brand card, and yellow arch shape
│   │   └── FooterSection.vue    # Brand summary, interactive social links, and decorative arch pillars
│   ├── router/
│   │   └── index.js             # Vue Router configuration
│   ├── views/
│   │   └── HomeView.vue         # Main assembled landing page view
│   ├── App.vue
│   └── main.js
├── index.html                   # HTML entry with font preconnects & SEO metadata
├── tailwind.config.js / main.css
└── vite.config.js
```

### Why this structure was chosen:

- **Component Reusability & Single Responsibility**: Each section of the landing page is isolated in its own component under `src/components/`, making code easy to read, test, and maintain.
- **Design Token Centralization**: The brand colors (`#EEF36A` lime yellow, `#3F3047` dark purple, `#5171A5` blue, `#9BC995` sage green, `#E8F0EC` light tint, `#E8DDDD` border) and typography scales are defined centrally in `main.css` using Tailwind v4 `@theme`.
- **Zero Third-Party Bloat**: All 21 icons and illustrations are raw, lightweight SVG assets directly imported into the components, keeping bundle size minimal and page load instantaneous.

---

## 3. The Hardest Part, and How It Was Solved

### The Challenge: The Organic Dual-Curved Hero Section

The Figma desktop hero layout features an intricate combination of organic shapes:

1. A deep purple (`#3F3047`) container spanning from the top-left with custom corner rounding.
2. An asymmetric lime-yellow (`#EEF36A`) background curve on the right.
3. A horizontal organic bridge vector containing masked photography with a subtle blue tint spanning across both backgrounds.
4. Two-tone typography where the first part of the headline (`Your way to`) sits over the dark background, while the second part (`better payments`) sits over the yellow shape.

### The Solution:

- Extracted the exact vector path geometry and image patterns directly from the Figma file.
- Implemented layered composition using CSS positioning, relative z-indexing, and responsive scaling so the headline aligns naturally over both background tones across varying screen widths.
- For tablet and mobile viewports, cleanly transitioned to a unified dark container that preserves visual hierarchy and eliminates awkward text clipping.

---

## 4. What Would Be Improved With More Time

1. **Interactive Contact Drawer / Modal**: Clicking "Contact Us" or "Get Started" currently scrolls smoothly to the relevant section; with more time, a slide-over contact drawer with accessible form validation would enhance conversion.
2. **Scroll-Driven Micro-Interactions**: Utilize native CSS scroll-driven animations (`animation-timeline: view()`) to add subtle entry reveals to the benefit cards as the user scrolls.

---

## 5. Anything Deliberately Done Differently From the Design

1. **Animated Partner Logo Marquee**: In the Figma static frame, the partner logos (Google, Adobe, Stripe, Coinbase, GitHub, Uber) are stationary and partially truncated on narrower desktop screens. A smooth infinite CSS marquee loop with left and right gradient fade masks was added, pausing gracefully on hover.
2. **Fluid Tablet Adaptation**: The Figma file provided only Desktop (1440px) and Mobile (393px) frames without a tablet specification. The page was designed to adapt seamlessly:
   - Benefit cards switch from 3 columns (desktop) to 2 columns (tablet) to 1 column (mobile).
   - Hero and CTA layouts maintain balanced typography and spacing without horizontal overflow.
3. **Smooth Scroll & Focus Accessibility**: Added smooth anchor scrolling for `#benefits` and `#contact`, alongside accessible keyboard focus rings (`focus-visible:ring-2`) and ARIA labels on all interactive buttons and social links.
