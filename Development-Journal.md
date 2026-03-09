# Development Journal — Abinaya_RecipeStudio

**Course:** CSC 4370/6370 Web Programming · Spring 2026  
**Project:** Recipe Studio (Track A + Story Pack)  
**Team:** M. Abhinaya (Project Leader), Dhanush Nagarajan (Team Member)  

---

## 1. Project overview and Kanban usage

We used a Trello board titled **"Project Management Abinaya_RecipeStudio"** with columns aligned to the course Kanban guide: **Inbox**, **Backlog**, **TO-DO**, **In Progress**, **Review**, and **Done**. Daily standups (10–15 min) were run by the Project Leader to track progress and move cards.

### Cards per list (snapshot)

From our board metrics:

| List        | Number of cards | Role in workflow |
|------------|-----------------|------------------|
| Backlog    | 4               | Planned, not yet prioritized |
| TO-DO      | 4               | Ready to start               |
| In Progress| 3               | Actively being worked on     |
| Review     | 8               | Completed, awaiting verification |
| Done       | 16              | Completed and verified      |

**Total cards tracked:** 35. The largest share of cards is in **Done** (16), followed by **Review** (8), which reflected our focus on finishing core pages and then verifying them before submission. We kept **In Progress** small (3) to avoid spreading focus across too many tasks at once.

---

## 2. Task breakdown and progress

### Done (completed and verified)

- Create index.html homepage  
- Create recipes.html page  
- Create about.html page (team intro, one-sentence description, contact form)  
- Create recipe detail pages: recipe-biryani.html, recipe-brownie.html, recipe-burger.html, recipe-dosa.html, recipe-pasta.html, recipe-pizza.html  
- Create CSS folder and add base.css, components.css, styles.css  
- Add food images to images/  
- Setup project folder structure  
- Implement homepage layout (hero, highlights, featured recipes, cooking tips)  
- Build recipe pages (card grid, ingredients, instructions)  
- Write project description and setup instructions in README.md  

### In Progress (at time of journal)

- Style website using styles.css  
- Organize reusable styles in components.css  
- Final CSS styling adjustments  

### Review (awaiting verification)

- Test navigation links between pages  
- Check that all images load correctly  
- Verify CSS layout across pages  
- Verify all items before submission  
- Test website in Chrome, Firefox, and Edge  
- Check mobile responsiveness  
- Validate HTML and CSS code  
- Review navigation consistency  

### TO-DO (planned next)

- Write project description in README.md (partially done; can be expanded)  
- Add footer to all pages  
- Optimize food images  
- Improve navigation styling  

### Backlog (future / optional)

- Add more recipe pages  
- Improve website responsiveness (beyond current breakpoints)  
- Add more features: recipe cooking tips and features  
- Add recipe categories  

---

## 3. Design decisions

### Visual design and layout

- **Colors:** We chose a calm, readable palette: primary green (`#2d5016`), secondary brown (`#6b4423`), neutral background and text. This keeps the site focused on content and works well for a recipe context.  
- **Typography:** Playfair Display for headings (via Google Fonts) and system sans-serif for body text. We used a clear hierarchy (section headings with an accent line, card titles, meta text) so users can scan quickly.  
- **Layout:** We used **Flexbox** for the header and main navigation (title and nav on one line at desktop breakpoints) and **CSS Grid** for the highlights bar, recipe cards, and cooking tips. This gave us consistent columns and spacing without extra wrapper divs.

### File and code structure

- **HTML:** One file per page; semantic elements throughout (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`). Each page links to `base.css` and `components.css` so global and component styles apply everywhere.  
- **CSS split:**  
  - **base.css** — Reset, CSS custom properties (`:root`), typography, skip link, header, nav, main content area, and base responsive rules.  
  - **components.css** — Hero, highlights bar, buttons, cards, recipe detail layout, tip cards, contact form, footer.  
  - **styles.css** — Shared design system, animations, reduced-motion handling, and responsive breakpoints.  
  This split let us change the global look in one place and reuse components (cards, buttons) across home, recipes, and recipe detail pages.

### Responsive design

- **Breakpoints:** Mobile-first. We added breakpoints at **36rem**, **48rem**, and **64rem**. At 36rem the highlights bar and card grids move to 2–3 columns; at 48rem the header becomes flex (title + nav inline), hero text scales with `clamp()`, and card grids go to 3 columns where appropriate; at 64rem we increased main content padding and adjusted recipe grid columns.  
- **Images:** `max-width: 100%` and `height: auto` so images scale with the layout. Recipe hero images and card images use the same component classes for consistency.

### Accessibility

- **Skip link:** A skip link is off-screen until focused, then moves into view so keyboard users can jump to main content.  
- **ARIA:** We used `aria-label` on nav, `aria-labelledby` on sections, `aria-current="page"` on the active nav link, and `aria-hidden="true"` on decorative elements (e.g. chapter labels, dividers).  
- **Focus and motion:** Visible focus rings on links and buttons; `@media (prefers-reduced-motion: reduce)` shortens animation and transition durations and disables hover transforms so we respect user preferences.

### Animations (rubric: 3+)

- Card hover: slight lift (`translateY`) and stronger box-shadow.  
- Button hover/active: subtle scale (1.02 / 0.98).  
- Main content: fade-in with slight vertical motion on load (`@keyframes fadeIn` on `#main-content`).  
- All of these are toned down or disabled when `prefers-reduced-motion` is set.

---

## 4. Challenges and solutions

- **Keeping layout consistent across pages:** We defined shared classes (e.g. `.card`, `.btn`, `.site-header`, `.main-nav`) and used the same CSS files on every page. New recipe pages only need the same structure and class names to look consistent.  
- **Responsive header and nav:** On small screens the title and nav stacked; we used a media query at 48rem to switch to flex with `justify-content: space-between` so the header stays usable without JavaScript.  
- **Merge conflicts when combining histories:** When we restored the teammate’s Git history and reapplied our commits, we had conflicts in about.html, README, CSS, and HTML. We resolved them by keeping our additions (e.g. one-sentence project description, expanded README, design system) while preserving the existing structure and content.

---

## 5. Process and collaboration

- **Kanban:** The Project Leader maintained the Trello board and moved cards as tasks moved from TO-DO → In Progress → Review → Done. The “Cards per list” view (pie and bar charts) helped us see that most work was either Done or in Review, with a small In Progress count to avoid overload.  
- **Standups:** Short daily standups (10–15 min) covered: what was completed, what was next, and any blockers. Updates were reflected on the board and in time tracking.  
- **Roles:** The Project Leader handled coordination, Kanban, deliverables, and time tracking; the Team Member focused on development, layout and styling, and documentation. Both contributed to HTML, CSS, and content.

---

## 6. Lessons learned

- **Design system first:** Defining CSS variables and base styles early made it easier to keep colors, spacing, and typography consistent and to add new pages quickly.  
- **Small “In Progress”:** Limiting how many tasks were In Progress at once helped us finish and move cards to Review and Done instead of leaving many tasks half-done.  
- **Testing early:** Moving “Test navigation,” “Check images,” “Validate HTML/CSS,” and “Check mobile responsiveness” into Review made us catch layout and link issues before the final week.  
- **Next time:** We would document the design tokens (variables and breakpoints) in a short cheat sheet from the start and run browser and device checks even earlier in the schedule.

---

## 7. References

- **Board:** Trello — Project Management Abinaya_RecipeStudio (columns: Inbox, Backlog, TO-DO, In Progress, Review, Done).  
- **Repo:** [GitHub — Dhanush-0017/Abinaya_RecipeStudio](https://github.com/Dhanush-0017/Abinaya_RecipeStudio)  
- **Course:** CSC 4370/6370 Web Programming, Spring 2026; 17-day schedule and Kanban guide.

