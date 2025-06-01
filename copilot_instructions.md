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
- To deploy: commit to `main`. GitHub Actions auto-publishes with Wrangler.
- Use `CACHE.get/put` for fast reads.
- Use `env.DB.prepare` for SQL queries via Drizzle.
- AI available via `env.AI.run()` calls.

## Best Prompts for Copilot
- "Generate Durable Object to store session data."
- "Write SQL schema for user metadata."
- "Use AI binding to classify text