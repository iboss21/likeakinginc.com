# Like A King Inc. — Professional Business Services

![Org](https://img.shields.io/badge/Org-Like%20A%20King%20Inc.-111111)
![Focus](https://img.shields.io/badge/Focus-Professional%20Services%20%7C%20Engineering%20%7C%20Logistics-D4AF37)
![Regions](https://img.shields.io/badge/Regions-US%20%7C%20EU%20%7C%20GE-0F0F10)
![License](https://img.shields.io/badge/Code-MIT-informational)
![Security](https://img.shields.io/badge/Security-Privacy%20by%20Design-success)

This repository is the public overview and documentation hub for **Like A King Inc.**—a multi-disciplinary services company delivering **logistics & trucking operations**, **web & product engineering**, **AI/data solutions**, **SaaS incubation**, and **low-voltage/CCTV installation & integration**. We combine hands-on field expertise with modern software practices to ship reliable systems end-to-end.

---

## Table of Contents

* [What We Do](#what-we-do)
* [Flagship Projects & Brands](#flagship-projects--brands)
* [Industries Served](#industries-served)
* [Engagement Models](#engagement-models)
* [Service Catalog](#service-catalog)
* [Process & Delivery](#process--delivery)
* [Technology & Tooling](#technology--tooling)
* [Security, Privacy & Compliance](#security-privacy--compliance)
* [SLA & Support](#sla--support)
* [Roadmap](#roadmap)
* [Contributing](#contributing)
* [Repository Layout](#repository-layout)
* [Legal & Trademarks](#legal--trademarks)
* [Contact](#contact)

---

## What We Do

**Like A King Inc.** is built to be a single accountable partner for both the **physical layer** (logistics, cabling, CCTV, on-site installs) and the **digital layer** (web, AI, SaaS). We design, build, and operate systems that real businesses depend on—whether that’s keeping freight moving, securing facilities, or launching high-traffic web platforms.

**Core pillars**

* **Logistics & Trucking Ops** — Dispatch optimization, load workflows, route planning, ELD/TMS integrations.
* **Web & Product Engineering** — Full-stack development, design systems, UX, performance, accessibility.
* **AI & Data** — LLM applications, automations, analytics, retrieval systems, and data pipelines.
* **SaaS Incubator** — From concept to subscription billing, with CI/CD and operational runbooks.
* **Cable Management & CCTV** — Structured cabling, PoE networks, IP cameras, NVR/DVR, secure VLAN design.
* **Systems Integration** — Stitching together payments, identity, storage, telemetry, and vendor APIs.

---

## Flagship Projects & Brands

* **EcoShine Pro** — *ecoshine.pro*
  Smart service platform experiences (booking, CRM-lite, ops dashboards) with modern UX and performance budgets.

* **GoVelora** — *govelora.com · govelora.fr · govelora.ge* (expanding to more ccTLDs)
  Marketplace foundation for multi-vendor commerce, policy tooling, onboarding, and storefront themes.

* **DaviDio** — *davidio.dev*
  Engineering portfolio and product lab showcasing development standards, component libraries, and experiments.

* **…and active internal SaaS initiatives** that blend logistics ops, AI copilots, and business automation.

> Some properties are in active development; see [Roadmap](#roadmap) for status.

---

## Industries Served

* **Transportation & Logistics** (carriers, dispatch, 3PL/4PL)
* **Retail & Marketplaces** (multi-vendor, DTC)
* **Professional Services & Trades** (field service, appointment ops)
* **Hospitality & Facilities** (access control, CCTV, structured cabling)
* **Media & Gaming Adjacent** (storefronts, digital goods, community portals)

---

## Engagement Models

* **Advisory** — Architecture reviews, cost/perf audits, security posture, vendor selection.
* **Build** — Fixed-scope implementations or milestone-based delivery with shared success criteria.
* **Operate** — Ongoing maintenance, SRE/DevOps, analytics, and feature iteration with SLAs.

**Commercial options**: fixed bid, time & materials, or hybrid retainers.

---

## Service Catalog

### Logistics & Trucking

* Dispatch workflows, lane strategy, and load board automations
* ELD/TMS integrations (REST/CSV), document capture, e-signature
* Route optimization, geofencing, telematics and simple dashboards
* KPI design: on-time %, dwell time, cost per mile, driver utilization

### Web & Product Engineering

* Next.js/React apps with App Router, API routes, and server actions
* Design systems (Tailwind + shadcn/ui), component libraries, Storybook
* Performance engineering (Core Web Vitals, edge caching, image pipeline)
* Accessibility (WCAG 2.2 AA goals), internationalization (EN/KA and more)

### AI & Data

* LLM applications: retrieval-augmented generation (RAG), chat tools, assistants
* ETL/data pipelines (PostgreSQL, DuckDB/Parquet, warehouse adapters)
* Vector search and document processing; embeddings and guardrails
* Analytics: event capture, warehouse modeling, dashboarding

### SaaS Projects

* Subscription billing & metered usage (Stripe), tax and invoicing
* Tenant & role models (RBAC), org workspaces, audit logs
* CI/CD pipelines, environment promotion, feature flags
* Support tooling, docs sites, changelog automation

### Cable Management & CCTV

* Structured cabling (Cat6/Cat6a), labeling and documentation
* PoE switching, VLAN segmentation, hardened subnets for cameras/NVRs
* IP camera planning, ONVIF profiles, retention policies
* Secure remote access and network monitoring

### Systems Integration

* Identity (OAuth, email magic links), SSO/SCIM where applicable
* Storage (S3-compatible, CDN), media pipelines, PDF/CSV tooling
* Payments, webhooks, background jobs, queue-based workers
* Observability: logs, traces, metrics, and uptime monitoring

---

## Process & Delivery

1. **Discovery & Planning**
   Problem definition, constraints, and a cost–value map. Clear acceptance criteria.

2. **Architecture & UX**
   Decision records (ADRs), data flows, low-fidelity UX, and threat models.

3. **Build**
   Trunk-based development with preview environments, code owners, and automated checks.

4. **Hardening**
   Performance budgets, security reviews, disaster-recovery drills, and load tests (where relevant).

5. **Launch & Operate**
   Runbooks, monitoring, SLAs, and a measured release plan with rollback paths.

---

## Technology & Tooling

**Web/App:** Next.js, React 18, TypeScript, Tailwind, shadcn/ui, Framer Motion
**Backend:** API routes/server actions, tRPC/REST, Prisma, Node.js
**Data:** PostgreSQL, Redis, object storage (S3-compatible), event capture
**AI:** OpenAI-compatible APIs or local engines; vector DB options; RAG pipelines
**DevOps:** GitHub Actions, Vercel (apps), Docker (services), Infrastructure as Code (where applicable)
**Quality:** TypeScript strict, ESLint/Prettier, Vitest/Jest, Playwright, Lighthouse CI
**Security:** Secrets via envs, signed webhooks, role-based access, least privilege

> Tooling is selected per engagement; we also integrate with your existing stack when preferred.

---

## Security, Privacy & Compliance

* **Privacy by Design:** Collect only what’s needed; minimize retention.
* **Network Hygiene:** Segmented VLANs for CCTV/IoT; deny-by-default firewalling.
* **Data Handling:** Structured logs, PII tagging, and rotation policies.
* **Web Security:** CSRF, CSP, strict cookies, authenticated webhooks.
* **Compliance:** We align to common controls (SOC 2 style practices, GDPR/CCPA considerations) when relevant to scope.

Security issues should be reported privately—see `SECURITY.md` (or open a GitHub Security Advisory).

---

## SLA & Support

* **Priority 1 (Critical):** service down, active data loss → immediate triage.
* **Priority 2 (High):** core feature degradation → same-day response.
* **Priority 3 (Normal):** routine bugs/requests → scheduled into the next sprint.

Custom SLAs available under Operate engagements.

---

## Roadmap

Public highlights (non-exhaustive):

* **GoVelora multi-region rollout:** `.fr`, `.ge`, additional country TLDs with localized policies and payments.
* **EcoShine Pro upgrades:** booking UX, ops dashboards, automated reminders, and performance budgets.
* **AI Assistants:** back-office copilots for logistics paperwork and marketplace moderation.
* **CCTV Playbooks:** standardized PoE/VLAN designs, camera layout templates, and retention calculators.
* **Shared Design System:** tokenized themes (gold/charcoal/ivory), component docs, and Storybook.

---

## Contributing

This repository contains public docs, issue templates, and (when applicable) open-source packages we maintain.

* Use **Conventional Commits** (`feat:`, `fix:`, `docs:`…).
* For documentation fixes or suggestions, open a PR with screenshots when helpful.
* For security matters, do **not** open public issues; use private advisories.

---

## Repository Layout

```
.
├─ docs/                 # Service guides, playbooks, ADRs, brand assets
├─ examples/             # Example integrations and code snippets
├─ packages/             # OSS packages (if any) extracted from client work
├─ .github/
│  ├─ ISSUE_TEMPLATE/    # Bug/feature request templates
│  └─ workflows/         # CI for docs/lint/examples
└─ SECURITY.md           # Private disclosure process
```

---

## Legal & Trademarks

* Unless noted, code here is released under the **MIT License**.
* **Like A King Inc.**, **GoVelora**, **EcoShine Pro**, and associated marks are trademarks or service marks of their respective owners.
* Third-party names/logos belong to their owners and do not imply endorsement.

---

## Contact

* **Website/Brands:**

  * EcoShine Pro — [https://ecoshine.pro](https://ecoshine.pro)
  * GoVelora — [https://govelora.com](https://govelora.com) · [https://govelora.fr](https://govelora.fr) · [https://govelora.ge](https://govelora.ge)
  * DaviDio — [https://davidio.dev](https://davidio.dev)
* **Business inquiries:** open a GitHub issue in this repo or reach out via the contact form on any of the sites above.

---

### Short Version

We integrate **real-world operations** (logistics, installs, CCTV) with **modern software** (web, AI, SaaS). One accountable partner. Production-ready work. Clear SLAs. Expandable across regions and markets.
