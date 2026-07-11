# Quick Start & Commands

This project uses **Astro** as the framework and **pnpm** as the package manager. 

*   **Install Dependencies:** `pnpm install`
    *   *Note: If `esbuild` or `sharp` throw security errors on a fresh Mac install, run `pnpm install --config.ignore-scripts=false` to bypass the block.*
*   **Start Local Dev Server:** `pnpm run dev`
*   **Build for Production:** `pnpm run build`
*   **Clear Build Cache:** `rm -rf .astro dist` (Run this if the dev server acts buggy or refuses to update images/icons).

# How to Add New Pages & Content

Astro uses **File-Based Routing**. You do not need to run terminal commands to generate new routes; the file structure dictates the URL.

### 1. Adding a Static Page (e.g., `/about`)
1. Create a new `.astro` file inside the `src/pages/` directory (e.g., `src/pages/about.astro`). 
2. The URL will automatically become `jacoblikins.dev/about`.

### 2. Adding a New Project
Projects are managed using Astro's Content Collections.
1. Navigate to `src/content/projects/`.
2. Create a new Markdown (`.md`) file.
3. Fill out the required frontmatter at the top of the file (title, description, pubDate, heroImage, badge). 
4. The site will automatically generate the project page and add it to the `/projects` grid.

### 3. Adding a New Blog Post
1. Navigate to `src/content/blog/`.
2. Create a new Markdown (`.md`) file.
3. Add the required frontmatter. It will auto-populate on the `/blog` page.

# Important Project Notes 

If you step away from this project for a few months, remember these specific quirks we solved for your Netlify deployment:

*   **Node.js Version:** Netlify is configured to use Node v20 via environment variables (`NODE_VERSION = 20`). Astro requires Node v18+, so do not downgrade this.
*   **The Sitemap Bug:** The project uses `@astrojs/sitemap@3.6.0`. **Do not update this package past 3.6.0** while still using Astro v4. Newer versions rely on Astro v5 hooks and will crash the build with a `reduce` error.
*   **API Routes (RSS):** Any custom API routes (like `src/pages/rss.xml.js`) must export their HTTP methods in strictly **UPPERCASE** (e.g., `export async function GET(context)`). Lowercase `get` will fail.
