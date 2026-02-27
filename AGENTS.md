# AGENTS.md

## Cursor Cloud specific instructions

**Giftsity Client** is a frontend-only React SPA (Vite 6 + React 18 + Tailwind CSS 3). The backend APIs are in separate repositories and not included here.

### Running the app

- `npm run dev` starts the Vite dev server on port 5173 with HMR.
- The Vite proxy forwards `/api` to `localhost:5000` (main API) and `/api/seller` to `localhost:5001` (seller API). Without these backends running, API-dependent features (auth, product listing, orders) will show errors — static pages (Home, About, Shop UI, Contact, policies) still render fully.
- Copy `.env.example` to `.env` before first run. The env vars (`VITE_API_URL`, `VITE_SELLER_API_URL`, `VITE_CORPORATE_API_URL`) are only used in production builds; dev mode relies on the Vite proxy.

### Build

- `npm run build` produces a production bundle in `dist/`.

### Lint / Test

- No ESLint config or test framework is configured in this repo. There are no `lint` or `test` scripts in `package.json`.

### Notes

- Package manager: **npm** (lockfile is `package-lock.json`).
- Node v22+ works fine.
- The corporate API has no Vite proxy entry configured; if needed locally, add a proxy rule in `vite.config.js` or set `VITE_CORPORATE_API_URL` in `.env`.
