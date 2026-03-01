# GEMINI.md - Context for Jeffrey Yeung's Personal Site

## Project Overview
This project is a personal portfolio website for Jeffrey Yeung, designed for hosting on GitHub Pages. It is a lightweight, static site built using modern web standards without external dependencies or build tools.

### Technologies
- **HTML5:** Semantic structure for content.
- **CSS3:** Responsive design, custom properties for theming, and smooth transitions. Styles are embedded directly within `<style>` tags in each page.
- **Vanilla JavaScript:** Simple interactions for the sidebar menu and dark/light mode toggling.

### Architecture
The site consists of several top-level HTML files and a sub-directory for detailed project pages:
- `index.html`: The landing page with a hidden sidebar navigation.
- `projects.html`: A grid-based listing of various projects.
- `ideas.html`: A simple list for notes and future project concepts.
- `contact.html`: Links to professional and personal contact methods.
- `projects/`: Contains specific project pages (e.g., `epq.html`) and associated assets like PDFs and images.

## Building and Running
Since this is a pure static site, there is no build step.

- **Development:** Open any `.html` file directly in a web browser.
- **Local Server (Optional):** To test features like local storage or absolute paths accurately, use a simple HTTP server:
  ```bash
  # Using Python
  python3 -m http.server 8000
  # Using Node.js (if available)
  npx serve .
  ```
- **Deployment:** Automatically deployed via GitHub Pages when changes are pushed to the main branch.

## Development Conventions
- **Single-File Components:** Each page is largely self-contained. CSS and JS specific to a page's layout or interactive elements are kept within that file to minimize network requests.
- **Theme Consistency:** A theme-toggling script is present on every page. It uses `localStorage` (key: `jy-theme`) to persist the user's preference and checks `prefers-color-scheme` for the initial default.
- **Responsive Design:** Uses `clamp()` for fluid typography and media queries to adapt the sidebar and project grid for mobile devices.
- **Navigation:** The sidebar on the home page is revealed by a hitbox on the left edge or by clicking the toggle button. Sub-pages include a simple "back" link to return to the home page.
- **Adding Projects:** 
  1. Create a new HTML file in `projects/` (or use `epq.html` as a template).
  2. Add a new `<article>` entry to the grid in `projects.html`.
  3. Place supporting assets (PDFs, images) in the `projects/` directory.
