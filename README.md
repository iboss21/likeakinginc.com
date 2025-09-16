# Like A King Inc. — Monorepo

![Org](https://img.shields.io/badge/Org-Like%20A%20King%20Inc.-111111)
![License](https://img.shields.io/badge/License-MIT-2ea44f)
![Made with](https://img.shields.io/badge/Made%20with-Typescript-3178c6)
![CI](https://img.shields.io/badge/CI-GitHub%20Actions-2088FF)
![Design](https://img.shields.io/badge/Design-21st.dev%20%2B%20Glassmorphism-D4AF37)

A modern, multi-product monorepo powering the **Like A King Inc.** ecosystem: luxury-grade web experiences, AI-driven SaaS, e-commerce platforms, and game-mod marketplaces. This repo centralizes shared UI, configuration, CI/CD, and service integrations for consistent quality and speed.

---

## Table of Contents

* [Vision & Principles](#vision--principles)
* [Products & Apps](#products--apps)
* [Architecture](#architecture)
* [Tech Stack](#tech-stack)
* [Repository Structure](#repository-structure)
* [Design System & Brand](#design-system--brand)
* [Getting Started](#getting-started)
* [Configuration](#configuration)
* [Development Workflow](#development-workflow)
* [Quality Gates](#quality-gates)
* [CI/CD](#cicd)
* [Security & Disclosure](#security--disclosure)
* [Contributing](#contributing)
* [Issue Types](#issue-types)
* [Roadmap](#roadmap)
* [License & Trademarks](#license--trademarks)
* [Credits](#credits)

---

## Vision & Principles

**Build premium, honest products** that feel **luxurious** yet **blazingly fast**, with **privacy-first** data practices and transparent governance.

Guiding principles:

* **Design with intent:** Minimal, elegant, accessible.
* **Security by default:** Threat-model early; least privilege everywhere.
* **Monorepo leverage:** One source of truth for UI, config, and infra.
* **Operational excellence:** Lint, type, test, ship.
* **International by design:** English + Georgian (ka) first-class support.

---

## Products & Apps

This monorepo hosts multiple production apps and shared packages used across the Like A King Inc. ecosystem:

* **/apps/likeaking-web** — Corporate marketing site & org portal.
* **/apps/creditfixexpert** — AI consumer-credit SaaS (secure disputes & automations).
* **/apps/govelora** — Marketplace platform for independent sellers.
* **/apps/customteespot** — Print-on-demand storefront with policy tooling.
* **/apps/lux-portal** — Internal admin/ops console (RBAC, billing, analytics).
* **/apps/redm-market** — Game mod storefront (Tebex export tools & docs).

> Shared libraries live under `/packages/*` to ensure a unified experience across apps.

---

## Architecture

High-level view:

```
apps/* (Next.js)
 ├─ public/          # static assets
 ├─ src/
 │   ├─ app/         # Next.js app router
 │   ├─ components/  # app-specific components
 │   └─ pages/       # optional legacy pages
packages/*
 ├─ ui/              # shared UI (shadcn + Tailwind), tokens, icons
 ├─ config/          # eslint, tsconfig, prettier, commitlint
 ├─ tailwind/        # tailwind preset; theming via CSS variables
 ├─ db/              # prisma schema + migrations
 ├─ utils/           # shared TS utilities
services/*
 ├─ auth/            # auth adapter (NextAuth/Auth.js), RBAC, session
 ├─ billing/         # Stripe, webhooks, metered usage
 ├─ media/           # uploads (S3/Cloudflare R2), image pipeline
 ├─ ai/              # model gateways & safety rails
infra/*
 ├─ docker/          # local dev containers (Postgres, Redis, etc.)
 ├─ terraform/       # cloud infra (optional)
 ├─ github/          # workflows, composite actions
docs/*               # brand, ADRs, runbooks, policies
```

Data flows are service-oriented but kept in one repo for speed and consistency. Shared DB models live in `packages/db` with Prisma and are consumed by apps/services.

---

## Tech Stack

**Frontend:** Next.js (App Router), React 18, TypeScript, Tailwind CSS, shadcn/ui, Framer Motion
**Backend:** Next.js (API routes) + server actions, tRPC/REST, Prisma
**Storage:** PostgreSQL, Redis (cache/queues), S3-compatible object storage
**Payments:** Stripe (subscriptions, invoices, webhooks)
**Auth:** Auth.js / NextAuth (OAuth, email magic links), RBAC with middleware
**CI/CD:** GitHub Actions → Vercel (apps) / Docker (services)
**Quality:** ESLint, Prettier, TypeScript strict, Vitest/Jest + Playwright
**Tooling:** TurboRepo, PNPM, Changesets, Commitlint, Husky, lint-staged

---

## Repository Structure

```
/apps
  likeaking-web/
  creditfixexpert/
  govelora/
  customteespot/
  lux-portal/
  redm-market/

/packages
  ui/
  config/
  tailwind/
  db/
  utils/

/services
  auth/
  billing/
  media/
  ai/

/infra
  docker/
  terraform/
  github/

/docs
  brand/
  adr/
  runbooks/
  policies/
```

---

## Design System & Brand

**Tone:** modern luxury, confident and precise.
**Primary palette:**

* Royal Gold: `#D4AF37`
* Deep Charcoal: `#0F0F10`
* Onyx: `#111214`
* Ivory: `#F8F6F2`
* Accent Emerald: `#1C7C54` (sparingly for state/success)

**Typography:** Display—*Playfair Display*; UI—*Inter* (or *Geist*).
**Components:** Based on shadcn/ui; theming via CSS variables for light/dark modes.
**Assets:** Place SVG logos in `apps/*/public/brand/`. Export favicons via RealFaviconGenerator.

> Accessibility: minimum AA contrast for body text; test with Storybook and axe.

---

## Getting Started

**Prerequisites**

* Node.js ≥ 20.x
* PNPM ≥ 9.x (`corepack enable`)
* Docker Desktop (for Postgres/Redis)
* OpenSSL (generate secrets)

**Clone & Install**

```bash
git clone https://github.com/<org>/like-a-king-inc.git
cd like-a-king-inc
pnpm install
```

**Spin up databases (local)**

```bash
docker compose -f infra/docker/compose.dev.yml up -d
```

**Bootstrap env files**

```bash
cp .env.example .env
cp apps/likeaking-web/.env.example apps/likeaking-web/.env
# ...repeat for other apps as needed
```

**Migrate & seed**

```bash
pnpm db:push     # prisma db push
pnpm db:seed     # optional seeding if provided
```

**Run all apps**

```bash
pnpm dev         # turbo runs dev across apps
```

**Build**

```bash
pnpm build
```

---

## Configuration

### Root `.env.example`

```ini
# Shared
DATABASE_URL="postgresql://postgres:postgres@localhost:5432/likeaking"
REDIS_URL="redis://localhost:6379"
NEXTAUTH_SECRET="generate_with: openssl rand -base64 32"
NEXTAUTH_URL="http://localhost:3000"

# Stripe
STRIPE_SECRET_KEY="sk_test_xxx"
STRIPE_WEBHOOK_SECRET="whsec_xxx"

# Storage
STORAGE_BUCKET="lak-app"
STORAGE_REGION="auto"
STORAGE_ENDPOINT="http://127.0.0.1:9000"
STORAGE_KEY="minio_key"
STORAGE_SECRET="minio_secret"
```

Each app also ships its own `apps/<name>/.env.example` for app-specific toggles (feature flags, third-party keys, etc.).

---

## Development Workflow

* **Branching:** trunk-based. Feature branches from `main`: `feat/<scope>`, `fix/<scope>`, `docs/<scope>`.
* **Commits:** [Conventional Commits](https://www.conventionalcommits.org/) enforced (e.g., `feat(ui): add gold button variants`).
* **PRs:** small, focused, with screenshots for UI changes and test coverage for logic changes.
* **Reviews:** one approval minimum; CI must pass.
* **Releases:** Managed via Changesets → version bump → changelog → tag.

**Useful Scripts**

```bash
pnpm dev               # run all dev servers
pnpm dev --filter @apps/likeaking-web
pnpm test              # unit tests
pnpm test:e2e          # e2e (Playwright)
pnpm lint && pnpm typecheck
pnpm format
pnpm db:studio         # open Prisma Studio
```

---

## Quality Gates

* TypeScript strict mode ON across repo
* ESLint + Prettier + import sorting
* Unit tests (Vitest/Jest) required for core logic
* E2E smoke tests per app (Playwright)
* Lighthouse CI for marketing & storefronts
* Bundle size checks (next-bundle-analyzer) on PRs

---

## CI/CD

**GitHub Actions** (see `infra/github/workflows`):

* `ci.yml` — install, typecheck, lint, test, build
* `e2e.yml` — Playwright against preview deployments
* `release.yml` — Changesets release & GitHub Releases
* `audit.yml` — dependency review & license scanning
* `lighthouse.yml` — performance budget reports

**Deployments**

* **Vercel** for Next.js apps (envs: Preview, Staging, Production).
* **Docker** for background services (auth/billing/media/ai).
* **Terraform** optional for cloud infra (RDS/Cloud SQL, S3/R2, etc.).

---

## Security & Disclosure

We practice **privacy-by-design** and **minimal data collection**.

* Never open security issues publicly.
* Use **GitHub Security Advisories** to report vulnerabilities privately (Security tab → “Report a vulnerability”).
* Alternatively, contact our security team via the address in `SECURITY.md`.
* Keys and secrets are managed via environment variables only; no secrets in code or commits.
* Production webhooks (Stripe, auth) are verified and logged.

> We welcome responsible disclosure and will acknowledge valid reports.

---

## Contributing

We love clean PRs that improve performance, security, accessibility, or developer experience.

1. Fork → Feature branch → Commit (Conventional)
2. Ensure `pnpm lint`, `pnpm typecheck`, and tests pass
3. Open PR with clear description and screenshots/video if UI
4. Add/Update docs in `/docs` when necessary

**Local performance tips**

* Filter dev runs: `pnpm dev --filter @apps/govelora`
* Use Turbo’s cache: `pnpm build --force` (to refresh when needed)
* Keep Storybook stories minimal and colocated with components

---

## Issue Types

* **bug:** Something isn’t working
* **feat:** New feature request
* **perf:** Performance improvement
* **a11y:** Accessibility fix/enhancement
* **docs:** Documentation only
* **security:** Security concerns (prefer private advisory)
* **chore:** Build/CI/infra tasks

Please use the provided **Issue** and **PR** templates for consistency.

---

## Roadmap

* **Design System v2:** tokenized color system (Royal Gold, Deep Charcoal, Ivory), motion guidelines, iconography.
* **Billing Unification:** cross-app subscriptions, usage metering, and consolidated invoices via Stripe.
* **Globalization:** English & Georgian parity (copy, dates, currency), locale routing.
* **AI Gateway:** pluggable providers (OpenAI-compatible, local models), strict safety rails, per-app usage limits.
* **Marketplace 2.0:** seller onboarding, dispute workflows, policy templates, and storefront themes.
* **Observability:** OpenTelemetry traces + structured logs across apps/services.
* **Hardening:** threat models & pentest playbooks; periodic dependency audits.

Roadmap is tracked via GitHub Projects and milestone tags.

---

## License & Trademarks

* Code is **MIT** unless a subdirectory indicates otherwise (see `LICENSE` files in each package/app).
* “Like A King”, related logos, and brand assets are **trademarks** of **Like A King Inc.** Do not use without written permission.
* Third-party packages retain their respective licenses.

---

## Credits

* Design language inspired by high-craft luxury interfaces; implemented with **shadcn/ui** and **Tailwind**.
* Icons via **lucide-react**.
* Thanks to contributors and maintainers across the ecosystem.

---

### Quick Links

* `/docs/brand` — logos, color tokens, usage rules
* `/docs/runbooks` — on-call & operations guides
* `/docs/policies` — security, privacy, contribution
* `/infra/github/workflows` — CI definitions
* `/packages/ui` — shared components & tokens

---

**Build boldly. Ship carefully.** Royal quality, modern speed.
