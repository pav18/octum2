# AGENTS.md - OpenCode Assistant Guidance

## Setup
- Copy `.env.example` to `.env` and set `DATABASE_URL` and Kimi OAuth credentials
- Install dependencies: `npm install`
- Initialize database: `npm run db:push` (or `npx drizzle-kit push`)

## Development
- Start dev server: `npm run dev`
- TypeCheck: `npm run check`
- Lint: `npm run lint`
- Format: `npm run format`
- Run tests: `npm test`

## Database
- Push schema changes: `npm run db:push`
- Generate migrations: `npm run db:generate`
- Run migrations: `npm run db:migrate`
- Seed starter notes: `npx tsx db/seed.ts <userId>`

## Configuration
- Client UI strings: `src/config.ts`
- Server starter notes: `api/notes-router.ts`
- Do not modify component logic unless fixing real bugs
- Wiki-link targets must match note titles (case-insensitive)

## Project Structure
- `api/`: tRPC routers, Hono server, Kimi OAuth
- `contracts/`: Shared tRPC types
- `db/`: Drizzle schema, migrations, seed
- `src/`: React components, hooks, config, store
- `public/`: Static assets

## Build & Deploy
- Build: `npm run build`
- Start production: `npm start` (NODE_ENV=production node dist/boot.js)
- Preview: `npm run preview`

## Conventions
- Editable content lives in config files, not components
- localStorage fallback (`src/store.ts`) enables unauthenticated use
- tRPC contracts enforce API consistency between client/server