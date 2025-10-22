# Portfolio Website — Build Brief for AI Coding Agent

**Goal:** A single-page, one-column, professional portfolio that helps me land my first Data Analytics role. Deployed on GitHub Pages. Smooth in-page navigation, clean typography, tasteful micro-interactions, and a mint/teal palette on a warm paper background.

---

## 1. Tech & Constraints

- **Stack:** Vanilla HTML + CSS + JS (no frameworks).  
- **Deployment:** GitHub Pages (static).  
- **Fonts:**  
  - Headings: **Raleway** (Google Fonts).  
  - Body: **Satoshi** (self-hosted). Fallbacks: `Inter, Segoe UI, Roboto, system-ui, -apple-system, Arial, sans-serif`.  
  - Provide `@font-face` blocks; I’ll drop `Satoshi` font files in `assets/fonts/`.
- **Icons:** SVG only (inline where needed).
- **Accessibility:** WCAG 2.1 AA: proper landmarks, color contrast ≥ 4.5:1, focus states visible, `prefers-reduced-motion`.
- **Performance:** Lighthouse ≥ 95 on Performance/Best Practices/SEO. No external JS except optional analytics placeholder.

---

## 2. Color & Theme

- **Background (paper):** `#fbf6f1` (primary page background).
- **Palette (from my swatch image):**
  - Dark Teal: `#2f664e`
  - Mint Green: `#62c39b`
  - Soft Mint: `#b7dac6`
  - Mist (very light mint for surfaces): `#e8f3f0`
  - Text Default: `#202124`
  - Neutral Divider/Stroke: `#e6e0d9`
- **Usage:**
  - Primary CTA / accents: `#2f664e`
  - Secondary CTA / chips / badges: `#62c39b`
  - Cards / subtle panels: white `#ffffff` on paper bg `#fbf6f1`, or `#e8f3f0` for muted sections.
  - Hover states: slightly deepen tint or add subtle shadow.
  - Focus states: 2px outline using `#62c39b` on light fields, `#2f664e` on dark.

---

## 3. Page Structure (single file: `index.html`)

**Sticky top nav** (scrolls to sections):
- Links: **Home**, **Projects**, **Contact**, **Download CV**.
- Smooth-scroll behavior, active link highlighting on scroll.
- Mobile: collapsible menu (no overlay; a simple disclosure).

**Sections** (one-column, max-width 880px; generous whitespace):
1. **Home** (`#home`)
   - Left/top: greeting, name, short role line.
   - Underneath: one-sentence value proposition and 3–4 bullet chips (e.g., *SQL*, *Python*, *Tableau*, *Power BI*).
   - **Primary CTA buttons:** “View Projects” (scroll to `#projects`) and “Download CV” (links to `/assets/cv.pdf`).
   - **Profile photo placeholder** (round) on the right on desktop; stacked on mobile.
2. **Projects** (`#projects`)
   - Grid of **project cards** (1 column mobile, 2 columns ≥ 768px).
   - Each card: title, short description, **tags**, 1–2 key outcomes/metrics, and links: **Case Study** (internal section/page placeholder) and **GitHub**.
   - Optional tiny thumbnail (SVG/PNG placeholder).
3. **Contact** (`#contact`)
   - Brief line about availability.
   - **Contact form** (Name, Email, Message) using Formspree (placeholder action) with client-side validation.
   - Also list direct links: Email (mailto), LinkedIn, GitHub.
4. **Download CV** (`#cv`)
   - Short pitch + prominent download card linking to `/assets/cv.pdf`.
5. **Footer**
   - Minimal: © Year • Name • Links to GitHub/LinkedIn • “Built with ♥ and GitHub Pages”.

---

## 4. Interactions & Motion

- **Global:**
  - Smooth anchor scrolling (`scroll-behavior: smooth`).
  - Reveal on scroll (**intersection observer**) with subtle fade/slide (Y: 10–16px, duration 280–360ms, easing `cubic-bezier(.2,.7,.2,1)`).
  - Respect `prefers-reduced-motion`: disable animations/transforms if set.
- **Nav:**
  - Active link indicates current section (underline or 2px bottom border in `#62c39b`).
  - On scroll past hero, nav receives subtle backdrop blur + hairline border (`#e6e0d9`).
- **Buttons:**
  - Hover: elevate by `translateY(-2px)` and soft shadow.
  - Active: `translateY(0)`; shadow reduces.
- **Cards:**
  - Hover: very subtle lift and border-tint to `#b7dac6`.
- **Form:**
  - Inputs focus ring 2px `#62c39b`; invalid shows tiny helper text.

---

## 5. Content Placeholders

Use the following text and replaceable tokens (keep structure intact):

- **Hero Heading (H1):** `Conor Maguire`
- **Role (H2):** `Junior Data Analyst`
- **Tagline (paragraph):**  
  `I turn messy data into clear, actionable insights — with a focus on SQL, Python, and compelling visualizations.`
- **Skill Chips:** `SQL`, `Python`, `Pandas`, `Tableau`, `Power BI`, `A/B Testing`
- **CTA 1:** `View Projects`
- **CTA 2:** `Download CV`
- **Profile Image:** `assets/profile.jpg` (480×480, circle mask).
- **Projects (3 samples):**
  1. **Retail Sales Dashboard (Tableau)**  
     *Built a multi-page Tableau dashboard for a year of POS data; flagged declining SKUs and improved reorder accuracy.*  
     **Highlights:** +9% forecast accuracy; 30% faster weekly reporting.  
     **Tags:** `Tableau`, `SQL`, `Data Viz`  
     **Links:** GitHub: `https://github.com/yourname/retail-dashboard` • Case Study: `#`
  2. **Churn Prediction (Python)**  
     *Preprocessed customer data, engineered features, and trained tree-based models to predict churn.*  
     **Highlights:** ROC-AUC 0.87; SHAP for interpretability.  
     **Tags:** `Python`, `Pandas`, `Scikit-learn`  
     **Links:** GitHub: `https://github.com/yourname/churn-model` • Case Study: `#`
  3. **AB Test Evaluator**  
     *Built a small tool to evaluate experiment results with power calculations and sequential testing notes.*  
     **Highlights:** Clear pass/fail guidance, uplift CI.  
     **Tags:** `Experimentation`, `Statistics`, `Python`  
     **Links:** GitHub: `https://github.com/yourname/ab-evaluator` • Case Study: `#`
- **Contact Copy:**  
  `Currently open to junior data roles and freelance analysis projects.`  
  Links: `mailto:you@example.com`, LinkedIn `https://www.linkedin.com/in/yourhandle/`, GitHub `https://github.com/yourhandle`
- **CV:** Place file at `/assets/cv.pdf`.

---

## 6. File/Folder Layout

/ (repo root)
├─ index.html
├─ /assets
│ ├─ /fonts
│ │ ├─ Satoshi-Variable.woff2
│ │ └─ Satoshi-Regular.woff2
│ ├─ profile.jpg
│ └─ cv.pdf
├─ /css
│ └─ styles.css
└─ /js
└─ main.js


---

## 7. Implementation Details

### 7.1 HTML (`index.html`)
- Landmark order: `<header>` (nav), `<main>` containing `<section id="home">`, `<section id="projects">`, `<section id="contact">`, `<section id="cv">`, then `<footer>`.
- Add `<link rel="preload">` for `Satoshi-Variable.woff2` (as font, crossorigin) and hero profile image.
- SEO:
  - `<title>Conor Maguire — Data Analyst Portfolio</title>`
  - Meta description: `Portfolio of Conor Maguire, Junior Data Analyst specializing in SQL, Python, and data visualization.`
  - OpenGraph/Twitter tags, social preview image placeholder: `assets/preview.png`.
- Nav links use `href="#home"`, `#projects`, `#contact`, `#cv` and a prominent **Download CV** button (`/assets/cv.pdf`, `download` attribute).
- Contact form (Formspree placeholder):

  ```html
  <form action="https://formspree.io/f/yourformid" method="POST">
    <input type="text" name="name" required>
    <input type="email" name="_replyto" required>
    <textarea name="message" required></textarea>
    <button type="submit">Send Message</button>
  </form>

Include a hidden honeypot field for spam.

### 7.2 CSS (/css/styles.css)

Base:

:root vars for colors (see Section 2) and spacing scale.

Set background: #fbf6f1; color: #202124;.

Typography:

h1,h2,h3 { font-family: 'Raleway', sans-serif; }

body, p, li, inputs { font-family: 'Satoshi', Inter, system-ui, ... }

Use fluid type via clamp().

Container: .wrap { max-width: 880px; margin: 0 auto; padding-inline: 24px }

Nav:

Sticky at top; backdrop filter blur(8px); border-bottom 1px solid #e6e0d9.

Active link underline/border with #62c39b.

Buttons:

Primary: dark teal bg, white text, 10px radius, medium shadow, hover lift.

Secondary: mint outline button.

Cards:

Rounded (16px–20px), subtle shadow, 1px border #e6e0d9.

Tag chips with soft mint backgrounds.

Forms:

Inputs 44px min height; focus ring 2px #62c39b.

Utilities:

.visually-hidden for a11y, .sr-only labels where appropriate.

Animations:

.reveal base with opacity:0; transform:translateY(12px);

.reveal.in -> opacity:1; transform:none; transition: 320ms cubic-bezier(.2,.7,.2,1);

@media (prefers-reduced-motion: reduce) → disable transitions/transforms.

### 7.3 JavaScript (/js/main.js)

Smooth-scroll for anchor clicks (with reduced-motion check).

IntersectionObserver to add .in to .reveal elements on enter.

ScrollSpy: observe sections to toggle aria-current="page" on matching nav links.

Mobile menu toggle with aria-expanded.

Contact form client-side validation and success/failure toast (non-blocking).

## 8. Accessibility & Quality Checklist

Semantic headings in order (h1 once; h2 per section).

All interactive elements keyboard reachable; focus visible; skip-to-content link.

Color contrast AA (buttons/text on #fbf6f1 and on mint surfaces).

Images have descriptive alt; decorative SVGs set aria-hidden="true".

Form has labels, aria-invalid on errors, and success message region (role="status").

Lighthouse ≥ 95 on PWA not required, but Performance/SEO/Best Practices/Accessibility targeted.

## 9. Sample CSS Variables
:root {
  --bg-paper: #fbf6f1;
  --ink: #202124;
  --teal-900: #2f664e;
  --mint-500: #62c39b;
  --mint-200: #b7dac6;
  --mint-50: #e8f3f0;
  --stroke: #e6e0d9;

  --radius: 16px;
  --shadow-1: 0 6px 14px rgba(0,0,0,.06), 0 2px 4px rgba(0,0,0,.05);
  --shadow-2: 0 10px 24px rgba(0,0,0,.10), 0 4px 8px rgba(0,0,0,.06);
}

## 10. Acceptance Criteria

Deployed on GitHub Pages at https://<username>.github.io/<repo>/.

All nav links scroll to sections; active state updates as I scroll.

Visuals match palette and background; typography uses Raleway + Satoshi (falling back gracefully).

Animations are subtle and disabled under prefers-reduced-motion.

Projects display as clean cards with tags and links.

Contact form posts to Formspree (I’ll update the endpoint).

Core Web Vitals: LCP < 2.5s (desktop), CLS < 0.1.

Valid HTML (W3C) and no console errors.

## 11. Nice-to-Have (if quick)

Add a tiny downloadable JSON resume endpoint (/resume.json) and link in footer.

Add schema.org JSON-LD for a Person with sameAs links (LinkedIn, GitHub).

Simple “theme seed” in localStorage to slightly vary card tint within the mint range for visual charm.

## 12. To-Do for Me (placeholders you’ll create)

assets/profile.jpg (you can insert a neutral placeholder).

assets/cv.pdf (dummy file).

assets/preview.png (social preview, 1200×630).

Deliverables:

index.html, css/styles.css, js/main.js per above, fully wired.

Minimal README with setup and how to replace placeholders.

Please implement exactly as specified, aiming for a calm, modern aesthetic that feels trustworthy to recruiters.