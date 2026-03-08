# Abinaya_RecipeStudio

**Recipe Studio** — A portfolio-ready recipe microsite built with HTML and CSS for CSC 4370/6370, Spring 2026.

## Project story

Recipe Studio is a static, mobile-first recipe site that puts clarity first: one place to browse recipes, read ingredients and steps, and get quick cooking tips—without clutter or pop-ups. The site uses semantic HTML5, a shared CSS design system (variables, Flexbox, Grid), and responsive breakpoints so it works on phone or laptop. No JavaScript or backend; pure HTML and CSS.

## Setup

1. **Clone the repo**
   ```bash
   git clone https://github.com/Dhanush-0017/Abinaya_RecipeStudio.git
   cd Abinaya_RecipeStudio
   ```

2. **Run locally**  
   Open `index.html` in a browser, or use a local server (e.g. `python -m http.server 8000` or Live Server in VS Code) and visit the root.

3. **Upload to CODD**  
   Upload the entire folder (HTML, `css/`, `images/`) to your CODD account. Keep the same folder structure so paths like `css/base.css` and `images/pasta.jpg` still work.

## Folder structure

```
Abinaya_RecipeStudio/
├── index.html          # Home
├── recipes.html        # Recipe listing
├── recipe-pasta.html   # (and other recipe-*.html)
├── about.html          # About & contact (team intro)
├── css/
│   ├── base.css        # Reset, variables, typography, header, nav
│   ├── components.css # Hero, cards, buttons, recipe detail, tips, footer
│   └── styles.css      # Design system, animations, breakpoints
├── images/             # Recipe images and assets
└── README.md
```

## Design trade-offs

- **Mobile-first:** Base styles target small screens; media queries at 36rem, 48rem, and 64rem scale up to multi-column grids and inline header/nav.
- **CSS variables:** Colors, spacing, typography, and transitions live in `:root` so we could change the look site-wide from one place.
- **Base vs components:** `base.css` holds global layout and typography; `components.css` holds reusable pieces (cards, buttons, hero). This kept styling consistent and made it easy to add new recipe pages without duplicating layout code.
- **Accessibility:** Skip link, ARIA labels, visible focus states, and `prefers-reduced-motion` support so the site stays usable for keyboard and motion-sensitive users.

## Team

- **M. Abhinaya** (Project Leader) — coordination, Kanban, deliverables, daily standups  
- **Dhanush Nagarajan** — development, layout and styling, documentation  

CSC 4370/6370 Web Programming · Spring 2026 · Georgia State University
