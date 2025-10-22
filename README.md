## Portfolio Website — Sandra López

This repository contains the single-page portfolio site for Sandra López, designed to showcase junior data analytics projects with a calm mint/teal visual identity.

### Project Structure
- `index.html` — main page markup and structured data.
- `css/styles.css` — typography, layout, responsive design, and interaction styles.
- `assets/` — drop-in folder for fonts, imagery, and downloadable files.
- `resume.json` — lightweight machine-readable resume endpoint.

### Getting Started
1. Serve the site locally to avoid `file://` CORS issues (e.g., `python3 -m http.server 8000` from the project root and visit `http://localhost:8000/`).
2. Replace placeholder assets:
   - Add your `assets/profile.jpg` (480×480 recommended).
   - Replace `assets/cv.pdf` with your current CV.
   - Update `assets/preview.png` with a 1200×630 social preview.
   - The layout already uses Google-hosted Inter and Raleway, so no self-hosted fonts are required.
3. Update external links (LinkedIn, GitHub, email) in `index.html` and `resume.json`.

### Deployment
Push to the `main` branch of a GitHub repository and enable GitHub Pages (root `/`). Meta tags and assets are already configured for static hosting.

### Customisation Tips
- Adjust the color palette or spacing via CSS custom properties in `css/styles.css`.
- Section blocks include a lightweight `.reveal` class you can keep or remove with no functional impact.
- Schema.org JSON-LD data is embedded near the end of `index.html`; update once your final links are confirmed.

### Development Notes
- The page is fully static (no client-side JavaScript dependency).
- Lighthouse targets ≥95 on Performance, Best Practices, and SEO; keep external dependencies minimal to maintain scores.
