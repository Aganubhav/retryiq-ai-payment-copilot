# RetryIQ

## Overview

Payment intelligence dashboard powered by Gemini AI. Two features: analyze payment failures (cause, explanation, recovery) and predict payment risk (low/medium/high) before a payment is processed. No database — all analysis is AI-powered in real-time.

## Stack

- **Monorepo tool**: pnpm workspaces
- **Node.js version**: 24
- **Package manager**: pnpm
- **TypeScript version**: 5.9
- **Frontend**: React + Vite (artifacts/retryiq)
- **API framework**: Express 5 (artifacts/api-server)
- **AI**: Gemini via Replit AI Integrations (`@workspace/integrations-gemini-ai`)
- **Validation**: Zod (`zod/v4`)
- **API codegen**: Orval (from OpenAPI spec)
- **Build**: esbuild (CJS bundle)

## Key Files

- `artifacts/retryiq/src/pages/dashboard.tsx` — Main dashboard page with tabs
- `artifacts/retryiq/src/components/failure-analyzer.tsx` — Failure analysis form + results
- `artifacts/retryiq/src/components/risk-predictor.tsx` — Risk prediction form + results
- `artifacts/api-server/src/routes/payments/index.ts` — Gemini-powered API routes
- `lib/api-spec/openapi.yaml` — API contract

## Key Commands

- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- `pnpm --filter @workspace/api-server run dev` — run API server locally

See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details.
