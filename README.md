# BHARAT-AI
Bharat Pratap Singh aur hai aur aap ka 
Diff: replit.md
replit.md
-12
+21

_Replace the heading above with the project's name, and this line with one sentence describing what this app does for users._
A boilerplate HTML, CSS & JavaScript web app for the Bharat AI brand — built with Vite for instant auto-refresh during development.
## Run & Operate
- `pnpm --filter @workspace/bharat-ai run dev` — run the frontend (auto-refresh via Vite HMR)
- `pnpm --filter @workspace/api-server run dev` — run the API server (port 5000)
- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from the OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- Required env: `DATABASE_URL` — Postgres connection string
## Stack
- pnpm workspaces, Node.js 24, TypeScript 5.9
- Frontend: Vite + vanilla TypeScript (no framework)
- API: Express 5
- DB: PostgreSQL + Drizzle ORM
- Validation: Zod (`zod/v4`), `drizzle-zod`
- API codegen: Orval (from OpenAPI spec)
- Build: esbuild (CJS bundle)
- DB: PostgreSQL + Drizzle ORM (not yet used)
- Auto-refresh: Vite HMR
## Where things live
_Populate as you build — short repo map plus pointers to the source-of-truth file for DB schema, API contracts, theme files, etc._
- `artifacts/bharat-ai/index.html` — main HTML page (source of truth for markup)
- `artifacts/bharat-ai/src/style.css` — all CSS styles
- `artifacts/bharat-ai/src/main.ts` — all JavaScript logic
- `artifacts/bharat-ai/vite.config.ts` — Vite config (no React plugin; pure vanilla)
## Architecture decisions
_Populate as you build — non-obvious choices a reader couldn't infer from the code (3-5 bullets)._
- Pure vanilla TypeScript — no React or other UI framework, keeps the bundle tiny and the code approachable.
- Vite is used solely for dev-server HMR and production bundling; no JSX transform needed.
- IntersectionObserver drives scroll-in card animations and counter animations without a library.
- CSS custom properties (variables) define the entire design token system — saffron/green palette reflecting the Indian tricolour.
## Product
_Describe the high-level user-facing capabilities of this app once they exist._
Bharat AI landing page boilerplate with:
- Sticky nav with mobile hamburger toggle
- Hero section with animated stat counters
- 6-card features grid with scroll-in animations
- About section with language pills and metric bars
- Email sign-up CTA form
- Footer with links
## User preferences
-1
+2
## Gotchas
_Populate as you build — sharp edges, "always run X before Y" rules._
- Entry point is `src/main.ts` (not main.tsx) — no React in this artifact.
- Always run `pnpm install` after adding new packages to a workspace package.
## Pointers
