# Arteiros Personalizados - Central Documentation

## 1. Project Overview

**Arteiros Personalizados** is a static web project providing premium landing pages for personalized products. It currently hosts two distinct product lines/brands within the same repository:
- **Arteiros Personalizados**: Focused on customized ecobags, necessaires, and small bags.
- **Silk Centro Camisetas**: Focused on premium customized t-shirts with a minimum order requirement.

The project is designed with a modern, responsive, and dynamic aesthetic, utilizing pure HTML and Vanilla CSS without the overhead of heavy JavaScript frameworks.

---

## 2. Architecture & Tech Stack

- **Core Structure**: HTML5 for semantic structure.
- **Styling**: Vanilla CSS embedded directly within the HTML files (`<style>` tags). This allows for single-file, self-contained landing pages which are extremely fast to load.
- **Design System**: Employs CSS Variables (`:root`) extensively to maintain design consistency and allow for easy theming across different landing pages.
- **Typography**: Uses Google Fonts (`Fraunces` for headings, `Source Sans 3` for body text).
- **Icons**: FontAwesome (via CDN) and custom SVG/PNG icons stored locally.
- **Deployment**: Configured for continuous deployment via **Vercel**.

---

## 3. Directory Structure

```text
arteirospersonalizados/
├── index.html        # Main landing page (Arteiros Personalizados)
├── camisetas.html    # Secondary landing page (Silk Centro Camisetas)
├── assets/           # Directory containing all static images, icons, and graphics
└── vercel.json       # Deployment and HTTP header configuration for Vercel
```

---

## 4. Pages Detail

### 4.1. Arteiros Personalizados (`index.html`)
- **Theme**: Vibrant, professional palette featuring Dark Green (`#081F33`) and highlights of CTA Yellow (`#FFB300`).
- **Product Focus**: Ecobags, sacochilas, necessárias, and saquinhos.
- **Key Sections**:
  - **Topbar**: Highlights promotional offers.
  - **Header**: Sticky navigation with a mobile-responsive sidebar menu.
  - **Hero Section**: High-impact background image with a clear value proposition.
  - **Products**: Grid layout showcasing different bag types with hover micro-animations.
  - **Materials**: Section detailing premium material quality.
  - **Testimonials**: Interactive carousel displaying customer reviews and a Google Rating box.
  - **Contact/CTA**: Integrated form and Google Maps embed, plus a floating WhatsApp button for direct communication.

### 4.2. Silk Centro Camisetas (`camisetas.html`)
- **Theme**: Premium monochromatic palette (Black `#111111`, White `#FFFFFF`, and Grays) to emphasize exclusivity and quality.
- **Product Focus**: Customized black and white t-shirts (Minimum order: 10 pieces).
- **Key Sections**:
  - Similar structural layout to `index.html` but re-skinned.
  - Emphasizes the "Silk Centro" branding.
  - Features dark-mode aesthetics for the 'Sobre' (About) section and Testimonial carousel.

---

## 5. Styling & Design Patterns

The project follows strict design patterns to ensure a premium feel:
- **CSS Variables**: Centralized theming in `:root`. Example: `--verde-principal`, `--amarelo-cta` for Arteiros; `--cor-principal`, `--cor-escura` for Silk Centro.
- **Responsive Design**: Uses `clamp()`, flexible grids, flexbox, and media queries (`@media (max-width: 992px)`) to adapt layouts for mobile and tablet devices.
- **Micro-Animations**: Extensive use of CSS transitions and keyframe animations (e.g., hovering over product cards, gradient animation on buttons, floating badges) to make the interface feel alive.
- **Modularity**: Code is logically grouped by comments (e.g., `1. VARIÁVEIS E RESET`, `2. COMPONENTES`, `3. ESTRUTURA DE LAYOUT`) to make maintenance easier despite the CSS being inline.

---

## 6. Deployment Configuration (`vercel.json`)

The project is optimized for deployment on Vercel. The `vercel.json` file includes:
- **Caching**: Configures aggressive caching (`public, max-age=31536000, immutable`) for all files within the `/assets/` directory to improve load times and reduce bandwidth.
- **Security Headers**: Applies essential security headers across all routes (`X-Content-Type-Options`, `X-Frame-Options`, `Referrer-Policy`).

---

## 7. Future Maintenance & Development

- **Adding a New Page**: To add a new product line, duplicate an existing HTML file, update the meta tags, content, and tweak the CSS variables in the `:root` pseudo-class to match the new brand identity.
- **Updating Assets**: Place any new images in the `assets/` folder and reference them using relative paths (e.g., `assets/new-image.png`). Be mindful to optimize images (WebP/JPEG) before uploading to maintain performance.
- **Global Changes**: Since CSS is currently embedded, any global layout changes (like the header or footer structure) must be updated in both `index.html` and `camisetas.html`.
