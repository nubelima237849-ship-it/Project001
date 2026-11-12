# AGENTS.md

Single-page Vite 8 + React 19 app in plain JavaScript (`.jsx`, no TypeScript). Proyecto `humanizador-ia`: aún es la plantilla base; la lógica de humanización de texto está pendiente.

## Commands

- `npm install` — npm only (`package-lock.json` is the lockfile).
- `npm run dev` — Vite dev server with HMR.
- `npm run lint` — Oxlint, not ESLint.
- `npm run build` — production build to `dist/`. It does **not** lint.
- `npm run preview` — serve the built output.

No test runner, typecheck, formatter, or CI is configured. Verify changes with `npm run lint && npm run build`; do not claim tests were run.

Node `^20.19.0 || >=22.12.0` is required by Vite 8.

## Structure

- Entry chain: `index.html` → `src/main.jsx` (`createRoot` + `StrictMode`) → `src/App.jsx`.
- Global tokens/reset live in `src/index.css`; component styles in `src/App.css`.
- `public/` is served at `/`. `public/icons.svg` is an SVG sprite consumed via `<use href="/icons.svg#<id>">` — add new icons to that sprite.
- `README.md` describes how to run the project locally.

## Conventions

- CSS uses native nesting (`&:hover`, nested media queries) as in `src/App.css`; follow that style instead of flattening selectors.
- Oxlint config (`.oxlintrc.json`): `react/rules-of-hooks` is an error and `react/only-export-components` warns — keep non-component exports out of component files.
- React Compiler is intentionally not enabled; don't add it without being asked.
