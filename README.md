Ledger Sherlock

Ledger Sherlock is a premium AI-assisted finance reconciliation and exception-control workspace built for Razorpay Buildathon Track 4. It combines evidence-first deterministic matching, bounded AI investigation for unresolved cases, policy gates, human approval, and audit-ready escalation context.

Included in this repository

The repository contains the React frontend, Express/tRPC server, Drizzle schema and migrations, shared types, automated tests, project configuration, and panel/demo documentation.

Local setup

Use Node.js 22 or newer and pnpm. Install dependencies with pnpm install. Provide the environment values required by your own deployment through your local secret manager or platform configuration; never commit them to GitHub. Start the development server with pnpm dev; run tests with pnpm test; run TypeScript checks with pnpm check; and create a production build with pnpm build.

The application uses the managed platform integrations for authentication, database access, storage, and the built-in LLM. Do not commit .env, API keys, JWT secrets, database credentials, or uploaded customer files.

Product scope note

The Track 4 proof console currently evaluates a versioned synthetic 60-case corpus and sends only bounded unresolved cases to AI. Uploaded files are stored through the protected managed-storage flow with metadata persistence; automatic CSV parsing and mapping into the deterministic matcher is a future integration and should not be described as live functionality yet.

Main directories

•
client/ — React application and UI components

•
server/ — Express, tRPC procedures, database helpers, storage, and tests

•
drizzle/ — schema and migration files

•
shared/ — shared constants and types

•
*-guide.md and *-script.md — panel and walkthrough material

