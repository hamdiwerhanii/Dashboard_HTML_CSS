# Dashboard_HTML_CSS

A responsive, multi-page admin dashboard template built with plain HTML5 and CSS3. It uses no frameworks and no JavaScript.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![Font Awesome](https://img.shields.io/badge/Font%20Awesome-6.5.1-528DD7?logo=fontawesome&logoColor=white)
![Google Fonts](https://img.shields.io/badge/Google%20Fonts-Open%20Sans-4285F4?logo=googlefonts&logoColor=white)
![No JavaScript](https://img.shields.io/badge/JavaScript-none-lightgrey)

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Pages](#pages)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Customization](#customization)
- [Known Issues](#known-issues)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)
- [Author](#author)

---

## Overview

**Dashboard_HTML_CSS** is a front-end practice project: an eight-page admin and user dashboard UI built by hand with semantic HTML and custom CSS. It shows how to:

- build a full application layout with a fixed sidebar and a content area, using only **Flexbox** and **CSS Grid**
- write a small **utility-class framework** (`framework.css`) and use it on every page
- make a layout **responsive** with media queries (breakpoint at `767px`), including a sidebar that collapses to icons only on small screens
- build common dashboard widgets (stat cards, progress bars, timelines, tables, pricing cards and toggle switches) using CSS only

All content is static placeholder data. The project is a **UI template**. It has no backend, no data persistence and no JavaScript behaviour.

---

## Features

### Layout and navigation
- A shared **sidebar** on every page links to Dashboard, Settings, Profile, Projects, Courses, Friends, Files and Plans. Each link has a Font Awesome icon, and the current page is highlighted.
- A **top header** with a search input, a notification bell with a red indicator dot, and a user avatar.
- **Responsive design:** below `767px` the sidebar shrinks to a 58px icon-only rail, grids become a single column, and some decorative images are hidden (`.hide-mobile`).

### Dashboard widgets (`Template4.html`)
- **Welcome card** with avatar, name, project count, earnings and a "Profile" button
- **Quick Draft** form (title and text area)
- **Yearly Targets** with coloured progress bars (Money, Projects, Team)
- **Tickets Statistics** with Total, Pending, Closed and Deleted counters
- **Latest News**, **Latest Tasks** (one task shown as done) and **Top Search Items**
- **Latest Uploads** list with file-type icons (PDF, AVI, PSD, ZIP, DLL, EPS)
- **Latest Project Progress** timeline, where the current step's marker blinks through a CSS `@keyframes` animation
- **Reminders**, **Latest Post** and **Social Media Stats** (Twitter, Facebook, YouTube, LinkedIn)
- A **Projects table** with team avatars and coloured status labels (Pending, In Progress, Completed, Rejected), inside a horizontally scrollable wrapper

### CSS-only components
- **Toggle switches** made from a hidden checkbox and a styled sibling (`.toggle-checkbox` and `.toggle-switch`), with Font Awesome icons drawn in `::before`
- **Custom radio "server" cards** that highlight when selected (`input:checked + .server`)
- **Progress bars**, rating stars, level bars and pricing cards
- A **custom scrollbar** styled through `::-webkit-scrollbar`
- **Hover animations**, such as the bouncing upload icon on the Files page (`up-and-down` keyframes)

---

## Pages

| Page | File | Contents |
|------|------|----------|
| Dashboard | [`Template4.html`](Template4.html) | The main overview with all the widgets listed above and the projects table |
| Settings | [`Settings.html`](Settings.html) | Site Control (maintenance toggle and close message), General Info, Security Info (password, 2FA toggle, devices), Social Info, Widgets Control checkboxes, Backup Manager (backup frequency and server choice) |
| Profile | [`Profile.html`](Profile.html) | Avatar with level bar and rating, General / Personal / Job / Billing information rows with toggles, My Skills, Latest Activities |
| Projects | [`Projects.html`](Projects.html) | Project cards with date, description, team avatars, service tags, a progress bar and the price |
| Courses | [`Courses.html`](Courses.html) | Course cards with cover image, instructor avatar, description, a "Course Info" button, student count and price |
| Friends | [`Friends.html`](Friends.html) | Friend cards with contact icons, role, friend/project/article counts, a VIP badge, join date, and Profile/Remove buttons |
| Files | [`Files.html`](Files.html) | A grid of file cards (type icon, owner, date, size) and a Files Statistics panel with an Upload button |
| Plans | [`Plans.html`](Plans.html) | Pricing cards (Free at $0.00, Basic at $7.99, and Premium) with feature check-lists and Join buttons |

---

## Tech Stack

| Category | Technology |
|----------|------------|
| Markup | HTML5 |
| Styling | CSS3 (custom properties, Flexbox, Grid, media queries, `@keyframes`, pseudo-elements) |
| Utility layer | `Css/framework.css`, a custom set of utility classes (spacing, colours, flex helpers, typography, border radius) |
| Icons | [Font Awesome Free 6.5.1](https://fontawesome.com/), self-hosted (`Css/all.min.css` and `webfonts/`) |
| Font | [Open Sans](https://fonts.google.com/specimen/Open+Sans) from Google Fonts |
| JavaScript | None |

---

## Project Structure

```
Dashboard_HTML_CSS/
├── Template4.html      # Main dashboard page (entry point)
├── Settings.html       # Account and site settings
├── Profile.html        # User profile, skills and activities
├── Projects.html       # Project cards
├── Courses.html        # Course catalogue
├── Friends.html        # Friends / team members
├── Files.html          # File manager and storage statistics
├── Plans.html          # Pricing plans
├── Css/
│   ├── Template4.css   # Main stylesheet: layout, widgets and page-specific styles
│   ├── framework.css   # Reusable utility classes and colour variables
│   ├── all.min.css     # Font Awesome 6.5.1 (Free)
│   └── normalize.css   # normalize.css (included, not linked by the pages)
├── Images/             # Avatars, course covers, news/activity images, file-type SVG icons
└── webfonts/           # Font Awesome font files
```

---

## Getting Started

### Prerequisites
- Any modern web browser (Chrome, Firefox, Edge or Safari)
- Optional: an internet connection so the Open Sans font loads from Google Fonts. Without it, the pages fall back to the default sans-serif font.

### Installation

```bash
git clone https://github.com/hamdiwerhanii/Dashboard_HTML_CSS.git
cd Dashboard_HTML_CSS
```

### Running the project

You don't need to build or install anything. Pick one of these:

- **Open the file directly:** double-click `Template4.html`.
- **VS Code Live Server:** right-click `Template4.html` and choose **Open with Live Server**.
- **Any static server**, for example:
  ```bash
  npx serve .
  # or
  python -m http.server 8000
  ```
  Then open `http://localhost:8000/Template4.html`.

---

## Customization

- **Colours:** change the CSS custom properties in `:root`, which appear in both `Css/framework.css` and `Css/Template4.css`:
  ```css
  --blue-color: #0075ff;
  --blue-alt-color: #0d69d5;
  --orange-color: #f59e0b;
  --green-color: #22c55e;
  --red-color: #f44336;
  --grey-color: #888;
  --main-duration: 0.3s;
  ```
- **Utility classes:** spacing (`p-20`, `mt-15`, `mb-10`, and so on), colours (`bg-blue`, `c-grey`), layout (`d-flex`, `d-grid`, `between-flex`, `center-flex`) and radius (`rad-6`, `rad-10`) are all defined in `Css/framework.css`. Reuse them when you add new widgets.
- **Content:** every number, name and image is hard-coded in the HTML. Edit the markup directly.

---

## Known Issues

- The dashboard's "Profile" button in `Template4.html` links to `profile.html` (lowercase), but the file is named `Profile.html`. The link works on Windows and macOS but breaks on case-sensitive hosts such as GitHub Pages or most Linux servers.
- `Template4.html` has the generic `<title>Document</title>`.
- There is no `index.html`, so a static host will not serve the dashboard at the root URL.
- `Css/normalize.css` is included in the repository, but none of the pages link to it.
- Forms, toggles, checkboxes, "Save", "Upload", "Join" and "Remove" are visual only. Nothing is submitted or saved.
- Some placeholder data (for example on the Profile page) is sample content and not real user information.

---

## Roadmap

- [ ] Rename `Template4.html` to `index.html` and fix the `profile.html` link casing
- [ ] Give each page a meaningful `<title>` and add `alt` text to images for accessibility
- [ ] Add JavaScript for interactivity: saving drafts, deleting tasks, toggling widgets and searching
- [ ] Move the repeated sidebar and header markup into a shared component (for example with a templating tool or a framework)
- [ ] Add a dark mode using the existing CSS variables
- [ ] Deploy a live demo, for example on GitHub Pages

---

## Contributing

Contributions, issues and suggestions are welcome:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/my-improvement`
3. Commit your changes: `git commit -m "Add my improvement"`
4. Push the branch: `git push origin feature/my-improvement`
5. Open a Pull Request

---

## License

No license file is currently included; all rights reserved by the author.

---

## Author

**Hamdi Werhani**, GitHub: [@hamdiwerhanii](https://github.com/hamdiwerhanii)
