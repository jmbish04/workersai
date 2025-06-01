# Copilot Instructions for `workersai`

This project runs on Cloudflare Workers with advanced features:

## Tech Stack
- Cloudflare Workers (backend runtime)
- Durable Objects for long-lived state
- KV for caching (`CACHE`)
- D1 (SQL) with Drizzle ORM (`DB`)
- AI Binding for Workers AI
- Vite frontend deployed to static assets

## Repo Structure
```
backend/
  drizzle/         # Drizzle ORM schema
  src/             # Worker code (entry: index.ts)
  wrangler.jsonc   # Main config for deployment
frontend/
  build/client/    # Static assets served by Worker
.github/workflows/
  deploy.yml       # CI/CD for Worker
```

## Useful Tips
- To deploy: commit to `main`. GitHub Actions auto-deploys with Wrangler.
- Use `CACHE.get/put` for fast reads.
- Use `env.DB.prepare` for SQL queries via Drizzle.
- AI available via `env.AI.run()` calls.

## Default Package Manager
- Use `pnpm` for all installs and builds
- Install it locally with: `npm install -g pnpm`

## Best Prompts for Copilot
- "Genera