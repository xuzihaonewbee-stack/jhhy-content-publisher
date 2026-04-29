# B2B Content SEO System

This repository now follows the required TypeScript monorepo architecture for the B2B Content SEO system.

## Stack

- Frontend: Next.js + TypeScript
- Backend: NestJS
- Database: PostgreSQL + Prisma
- Queue: Redis + BullMQ
- Storage: adapter boundary for S3 / R2
- AI: adapter boundary for OpenAI / Claude

## Directory Structure

- `apps/web`: management UI
- `apps/api`: API layer and server-side orchestration
- `packages/core`: business rules, contracts, state machine
- `packages/adapters`: external service adapters only
- `packages/db`: Prisma schema and DB client
- `workers/content-jobs`: async workers
- `docs/architecture`: architecture docs and ADRs
- `reference`: stable business references

## Enforced Rules

- API keys are server-side only
- The frontend does not control permissions, SEO checks, or publishing logic
- Business logic does not call third-party APIs directly
- Every external integration must go through an adapter
- Publishing cannot bypass the article state machine
- Final publishing target is the JHHY dashboard

## ADR Policy

Every architecture change must be recorded under `docs/architecture/ADR-xxxx.md`.

## Source of Truth

- `PRD.md`
- `ARCH.md`
- `Project.md`

Code changes must stay aligned with these three files. Major changes are not ready to merge until all three are updated together.

## Current Scope

This is a production-oriented scaffold, not a finished product. It gives us:

- the required monorepo structure
- the required Prisma models
- a backend article module with state-machine enforcement
- explicit AI and CMS adapter boundaries
- a worker entry point for async pipelines
