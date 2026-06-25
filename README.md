# Monelyx

Monelyx is a workspace-native finance platform that brings together personal money management, collaborative finance operations, accounting workflows, AI-assisted insights, and third-party financial connectivity in a single backend platform.

This profile highlights the product and platform capabilities behind Monelyx.

## What Monelyx Powers

- Personal finance workflows for accounts, transactions, budgets, goals, subscriptions, debts, and financial planning
- Shared workspaces for individuals, families, and business teams with role-based access control
- Business-grade accounting features including ledger operations, reconciliation, invoicing, profit and loss, and balance sheets
- AI-assisted experiences such as financial summaries, health insights, anomaly detection, and chat-based assistance
- Banking and billing connectivity through providers such as Plaid, Stripe, and RevenueCat

## Platform Highlights

- Workspace-first multi-tenancy with clear data isolation and scoped access
- HTTP API with generated OpenAPI documentation and structured route contracts
- Authentication via bearer sessions and API keys
- Background job processing for sync, reporting, alerts, analytics, and operational maintenance
- Webhook-driven integrations for billing, banking, and messaging providers
- File and asset support through object storage compatible with R2-style services

## Core Product Domains

- Accounts and transactions
- Budgets, goals, and forward planning
- Reports, search, and AI
- Workspaces and collaboration
- Billing and subscription lifecycle
- Banking connectivity and sync
- Accounting, reconciliation, and invoicing

## Architecture At A Glance

Monelyx Backend follows a modular monolith design. Business capabilities are organized by domain, shared infrastructure is centralized, and persistence is handled through PostgreSQL with Prisma.

Typical request flow:

1. Global middleware handles security, timing, error processing, compression, CORS, rate limiting, and auth parsing.
2. Route-level middleware applies workspace resolution, access checks, and domain-specific protections.
3. Controllers and services execute business logic.
4. Prisma persists tenant-aware financial data.

The platform also runs scheduled jobs for recurring financial processing, imports and exports, reporting, notifications, anomaly detection, and integration maintenance.

## Technology Stack

- Bun
- Bklar
- TypeScript
- PostgreSQL
- Prisma ORM
- Zod
- Swagger / OpenAPI
- Redis
- R2-compatible object storage

## Integrations

- Plaid for bank connectivity and transaction sync
- Stripe for billing and payment operations
- RevenueCat for subscription lifecycle events
- Google AI / Gemini for AI-assisted product capabilities
- Firebase and messaging channels for communication workflows

## Documentation

- Public architecture and API overview: [Outline Collection](https://outline.monelyx.com/collection/api-docs-6n4fsFmqSd)
- Interactive API documentation: `/docs`
- Health check endpoint: `/health`

## Guiding Principles

- Build finance tooling that works for both personal and collaborative use cases
- Keep accounting-grade controls available where teams need stronger operational rigor
- Treat AI as assistive, not as the source of truth
- Design integrations and background jobs around idempotency, auditability, and safe retries

## Status

Monelyx is actively evolving as a modern finance platform that combines planning, analysis, collaboration, and operational finance in one system.
