<!-- Purpose: concise, actionable guidance for AI coding agents working in this repo -->
# Copilot / AI agent instructions — astrotutorial

This repository is a minimal Astro site (created with `npm create astro@latest -- --template minimal`). These notes tell an AI assistant what matters here so you can be productive immediately.

- **Big picture:** a tiny static site built with Astro (see `package.json` -> `astro` dependency v5.x). Pages live under `src/pages/` as `.astro` files and are served as routes (filename -> route).

- **Key files/directories:**
  - `package.json` — dev/build scripts (`dev`, `build`, `preview`) and Astro dependency.
  - `astro.config.mjs` — project config (currently empty/default).
  - `README.md` — template notes and commands; follow its scripts for workflows.
  - `src/pages/*.astro` — canonical place for routes. Example: `about.astro` -> `/about/`.
  - `public/` — static assets (referenced from root paths like `/favicon.svg`).

- **Developer workflows / commands** (run from repo root):
  - Install: `npm install`
  - Dev server: `npm run dev` (local server, default port 4321)
  - Build: `npm run build` (outputs `./dist/`)
  - Preview build: `npm run preview`
  - Astro CLI: `npm run astro -- --help`

- **Project-specific patterns & conventions**
  - Routes are file-based: add/update pages in `src/pages/` to change routes. Keep filenames consistent with trailing-slash linking used in templates (e.g. `<a href="/about/">`).
  - Pages include frontmatter (the `---` block) even when empty; preserve or update it when adding imports or props.
  - Static assets are referenced from `public/` by absolute paths (e.g. `/favicon.svg`).
  - There is no `src/components/` folder yet — if you add components, place them under `src/components/` and import them into pages via frontmatter.

- **Integration points & external deps**
  - Only external dependency is `astro` (no adapters, no framework integrations). If you add an adapter or framework, update `package.json` and update `astro.config.mjs` accordingly.

- **Editing guidelines for AI changes**
  - Keep diffs small and focused: prefer adding a single page/component per PR.
  - Preserve the existing HTML page scaffolding and frontmatter unless intentionally refactoring.
  - Do not change `package.json` `type: "module"` without cause.
  - If you add runtime dependencies, run `npm install` and add them to `package.json` scripts as needed.

- **Examples from this repo**
  - Route example: `src/pages/blog.astro` contains `<a href="/blog/">Blog</a>` and a top-level `<h1>Blog</h1>` — follow the same linking/heading style for new pages.
  - Frontmatter: pages begin with `---` then a blank line. When importing components, add the imports inside that frontmatter block.

- **What this repo does not include** (so do not assume):
  - No tests, no CI, no adapter/deployment config, no components directory, and no lockfile checked in.

If anything in these notes is unclear or you'd like more detail about routing, adding components, or a recommended CI config, tell me which area to expand and I'll update this file.
