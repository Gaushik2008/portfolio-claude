# Gaushik Kumar Ganesan — Personal Portfolio

A single-file, interactive personal portfolio built with **HTML, CSS, and vanilla JavaScript**. The site presents my introduction, technical skills, selected projects, certifications, and contact information through a bold, animated visual experience.

**Live portfolio:** https://gaushikkumarganesan.vercel.app/  
**Repository:** https://github.com/Gaushik2008/Portfolio-Website

---

## Table of contents

- [Overview](#overview)
- [Highlights](#highlights)
- [Portfolio sections](#portfolio-sections)
- [Technology](#technology)
- [Project structure](#project-structure)
- [Run locally](#run-locally)
- [Customize the portfolio](#customize-the-portfolio)
- [Add or update certificates](#add-or-update-certificates)
- [Deployment](#deployment)
- [Accessibility and performance notes](#accessibility-and-performance-notes)
- [Troubleshooting](#troubleshooting)
- [Contact](#contact)

---

## Overview

This portfolio is designed as a compact, dependency-light website rather than a framework-based application. Its main experience is contained in `index.html`, so it can be opened directly in a browser or hosted as a static site.

The visual direction combines oversized display typography, a colour-changing gradient background, a floating interactive hero illustration, translucent surfaces, and motion-based section reveals. The content is organized into clear sections so visitors can quickly learn about my work and find ways to connect.

The site currently includes content for:

- **About:** a short introduction and profile highlights.
- **Skills:** a visual overview of technical areas and tools.
- **Projects:** selected work, including UrbanPulse, M.I.L.O, this portfolio, and FORTIS.
- **Certifications:** certificate previews and links.
- **Contact:** email, GitHub, and LinkedIn links.

> Content in the website is maintained directly in the HTML and the configuration objects near the beginning of its JavaScript. Update those values when your profile, projects, or links change.

---

## Highlights

### Interactive hero

- Large animated headline that cycles through **PLAN**, **DESIGN**, **BUILD**, and **DEPLOY**.
- Floating device illustration with pointer-based parallax and drag interaction.
- Decorative particle/firefly canvas effect.
- Theme selector with animated colour transitions.
- Introductory loading animation.

### Visual design and navigation

- Violet and pastel-blue colour themes.
- Responsive navigation with a mobile menu.
- Fixed navigation bar with a scroll-state treatment.
- Scroll progress indicator and active-section navigation state.
- Large typography, gradient lighting, glass-like surfaces, and subtle texture.
- Hover treatments for cards, buttons, and interactive elements.

### Motion and interaction

- Scroll-triggered reveal animations.
- Animated text and marquee rows.
- Interactive tilt effects on selected cards.
- Magnetic movement on selected controls.
- Automatic hero headline rotation.
- Certificate preview lightbox.
- Copy-to-clipboard interaction for the email address.

### Responsive experience

The layout uses flexible sizing, responsive grids, and mobile navigation to adapt to different viewport widths. The interface also accounts for device safe-area insets where supported.

---

## Portfolio sections

| Section | Purpose |
| --- | --- |
| Hero | Introduces the portfolio and provides the main visual interaction. |
| About | Presents a short profile and selected highlights. |
| Skills | Displays technical skills in a visual format. |
| Projects | Showcases selected projects and their descriptions. |
| Certifications | Provides certificate previews and document links. |
| Contact | Makes it easy to reach me through email and social profiles. |

### Featured projects currently shown

- **UrbanPulse** — an AI-powered, multi-fleet road intelligence concept featuring a priority engine, warranty-based repair routing, and multi-step verification.
- **M.I.L.O** — an agentic AI companion concept for understanding priorities, planning tasks, and supporting personal productivity.
- **Portfolio Website** — this single-file portfolio, with animated themes and interactive visual elements.
- **FORTIS** — Financial Oversight, Risk Tracking & Intelligence System.

Project descriptions and destination links are part of the page content. Review them before publishing so that each card points to the correct project repository or demo.

---

## Technology

| Technology | Usage |
| --- | --- |
| HTML5 | Page structure and semantic content |
| CSS3 | Layout, responsive styling, gradients, animations, and visual effects |
| Vanilla JavaScript | Theme switching, navigation, interactions, observers, and dynamic content |
| Canvas 2D API | Lightweight decorative particle animation |
| Google Fonts | Anton and Figtree typography |
| Browser APIs | Intersection Observer, Clipboard API, Pointer Events, and Web Animations |

### External resources

The page loads Google Fonts (Anton and Figtree) from Google Fonts. An internet connection is therefore needed for those fonts to load. The core page does not require a package installation or JavaScript framework.

---

## Project structure

The repository is intentionally simple. The main website is contained in `index.html`.

```text
Portfolio-Website/
├── index.html          # Main page: markup, styles, and JavaScript
├── README.md           # Project documentation
└── certs/              # Certificate preview images and PDF files (if included)
    ├── python.jpg
    ├── python.pdf
    ├── ibm.jpg
    ├── ibm.pdf
    ├── java.jpg
    ├── java.pdf
    ├── git.jpg
    └── git.pdf
```

The certificate paths above describe the filenames referenced by the page. Keep the matching files in the `certs/` directory for the certificate previews and PDF links to work.

---

## Run locally

No build step, package manager, or development server is required for the basic static page.

### Option 1: Open in a browser

1. Clone the repository:

   ```bash
   git clone https://github.com/Gaushik2008/Portfolio-Website.git
   ```

2. Move into the project directory:

   ```bash
   cd Portfolio-Website
   ```

3. Open `index.html` in your browser.

### Option 2: Use a local development server

If you prefer to test through a local HTTP server, run:

```bash
python3 -m http.server 8000
```

Then visit:

```text
http://localhost:8000
```

Stop the server with `Ctrl+C`.

---

## Customize the portfolio

Most frequently changed profile settings are grouped near the beginning of the main script in `index.html`.

### 1. Update your name and email

Find the `ME` object:

```js
const ME = {
  name: 'Gaushik Kumar Ganesan',
  email: 'gaushikkumarganesan@gmail.com'
};
```

Change the values to update the name and email displayed by the page. The script uses these values to populate matching profile elements and the contact actions.

### 2. Change the hero words and symbols

Edit the `THEMES` array:

```js
const THEMES = [
  { word: 'PLAN', glyph: '{ }' },
  { word: 'DESIGN', glyph: '✦' },
  { word: 'BUILD', glyph: '</>' },
  { word: 'DEPLOY', glyph: '▶' }
];
```

Each entry controls one hero headline and its corresponding device symbol. Keep the `word` and `glyph` properties when adding or editing entries.

### 3. Customize the colour themes

Find the `VIBES` array. Each theme contains:

- `label`: accessible name and tooltip for the theme selector.
- `bg`: primary background colour.
- `surf`: surface colour.
- `acc`: accent colour.
- `lt`: lighter highlight colour.
- `tx`: foreground text colour.
- `gp` and `tr`: gradient presentation values.

Example:

```js
{
  label: 'Violet',
  bg: '#5b0fa8',
  surf: '#1c0a38',
  acc: '#8a3df0',
  lt: '#e3d2ff',
  tx: '#ffffff',
  gp: '100%',
  tr: 'color-mix(in srgb,#8a3df0 45%,transparent)'
}
```

When adding a theme, provide all the expected properties and check text contrast against the new colours.

### 4. Update about and skills content

Edit the corresponding HTML sections in `index.html`. Update the introduction, profile highlights, skill labels, and visual icons together. Avoid leaving placeholder or outdated claims in the published version.

### 5. Update project cards

Find the section with `id="projects"`. Each project is represented by a project card containing:

- Project name.
- Technology or category label.
- Short description.
- Link to its repository or live demonstration.
- Decorative project artwork.

Replace the card text and link with verified project information. If you add a project, follow the structure of an existing card so that the layout and styling remain consistent.

### 6. Update social and contact links

Find the contact section near the bottom of `index.html`. Update the email address and the GitHub and LinkedIn URLs. Check that every external link opens the intended destination.

---

## Add or update certificates

The certificate section references preview images and PDF files in the `certs/` directory.

To add a certificate:

1. Add the certificate preview image to `certs/`.
2. Add the corresponding PDF if you want visitors to access the document.
3. Add a certificate card in the section with `id="certifications"`.
4. Set the preview image path in the card's image and `data-cert` attributes.
5. Set the PDF path in `data-pdf` if you maintain a PDF link or download action for it.
6. Test the preview and document links locally.

The current page includes references for Python Programming (Infosys Springboard), Getting Started with Artificial Intelligence (IBM), Java (Basic) (HackerRank), and GitHub Workflow Mastery (Unstop). Keep these entries only while the corresponding certificate files and details are accurate.

**Privacy note:** Publish certificate images and PDFs only if you are comfortable making the information visible to anyone who can access the website. Hide or redact personal identifiers that should not be public.

---

## Deployment

This is a static website and can be hosted by any service that serves HTML, CSS, JavaScript, and static assets.

### Vercel

1. Import the GitHub repository into Vercel.
2. Select the repository's production branch.
3. Configure the project as a static site if Vercel does not detect it automatically.
4. Keep the project root as the repository root.
5. No build command is needed for the current single-file implementation.
6. Deploy and verify the resulting URL.

When you push changes to the connected production branch, Vercel can build and publish the updated site automatically according to the project's deployment settings.

### Other static hosting

The repository can also be hosted through GitHub Pages or another static hosting provider. Configure the host to serve `index.html` from the selected branch and directory, and ensure the `certs/` assets are included.

---

## Accessibility and performance notes

The implementation includes several accessibility- and performance-conscious choices:

- Semantic page sections and descriptive navigation links.
- Visible keyboard focus styling.
- Accessible labels and expanded state for the mobile menu.
- Alternative text for certificate preview images.
- A `prefers-reduced-motion` check that reduces or disables several motion effects.
- Lazy loading for certificate preview images.
- Device-pixel-ratio limiting for the decorative canvas.
- No framework runtime or third-party JavaScript package is required by the current page.

These measures do not replace a full accessibility audit. When changing the page, test keyboard navigation, colour contrast, reduced-motion behaviour, small-screen layouts, and the certificate lightbox.

---

## Troubleshooting

| Problem | What to check |
| --- | --- |
| Fonts look different | Check the internet connection and Google Fonts availability. |
| Certificate image is missing | Confirm the filename, extension, letter case, and path under `certs/`. |
| Certificate PDF does not open | Confirm the matching PDF exists and the link points to the correct file. |
| Email copy button does not work | Clipboard access may require HTTPS or localhost. Use the displayed email address as a fallback. |
| Theme or animation does not respond | Check the browser console for JavaScript errors and confirm the relevant element IDs still exist. |
| Mobile menu does not open | Check that the menu and burger element IDs have not been changed independently of the script. |
| Project link is incorrect | Update the corresponding project card's `href` in `index.html`. |

---

## Contact

**Gaushik Kumar Ganesan**

- Portfolio: https://gaushikkumarganesan.vercel.app/
- GitHub: https://github.com/Gaushik2008
- LinkedIn: https://www.linkedin.com/in/gaushikkumarganesan/
- Email: gaushikkumarganesan@gmail.com

---

## License

No license file was identified as part of the documentation currently inspected. Unless a license is added to this repository, do not assume that the source code is licensed for reuse, redistribution, or modification by others. Add a `LICENSE` file if you want to grant explicit permissions.

---

*Designed and built by Gaushik Kumar Ganesan.*
