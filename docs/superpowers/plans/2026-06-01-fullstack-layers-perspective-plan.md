# Full-Stack Layers Perspective Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Create a complementary 13-layer perspective on fullstack development as a parallel volume to the existing 12 factors.

**Architecture:** Flat `layers/` directory with 1 intro + 13 layer articles + 1 cross-reference matrix, plus housekeeping (rename `assests/`, create `VISION.md`/`CONTRIBUTING.md`, update README/CODEOWNERS).

**Tech Stack:** Markdown, Git

---

## Article Format Template (All Layer Articles)

Every layer article follows this exact structure. The template is defined here once — each task below only specifies the unique content for that layer.

```markdown
# Layer N: [Layer Name]
![cover](../images/layerN.png)

## TL;DR
[One-paragraph summary of what this layer covers and why it matters]

## Why This Layer Matters
[Strategic importance from a fullstack developer's perspective. 2-3 paragraphs explaining why understanding this layer is critical.]

## Key Considerations for Fullstack Developers
[Essential concepts and trade-offs. Numbered or bulleted list with brief explanations of each.]

## Implementation Patterns & Technologies
[Common approaches, tools, frameworks, and services. Code examples where relevant with language annotations.]

## Common Pitfalls
[Anti-patterns, gotchas, and lessons learned. Drawing on Tikal's consulting experience. 3-5 items with explanations.]

## How This Layer Connects to the 12 Factors
[Explicit cross-references to relevant existing factors, with specific links to their article files. This section varies most per layer — see each task for the exact cross-refs.]

## Case Study
[Real-world example from Tikal's experience. Match the narrative style of existing factor case studies — a named client, a problem, the approach, the outcome.]

## Conclusion
[Key takeaways and call to action. 1-2 paragraphs tying back to the fullstack developer's daily work.]

_This article is part of Tikal's Modern Full-Stack Developer's Guide: A 12-Factor Approach series. For the application architecture perspective, see the [main 12 factors](../articles/00-Intro.md)._
```

---

## File Structure

### New files to create:
| File | Responsibility |
|------|---------------|
| `layers/00-Intro.md` | Overview of the 13-layer model, how it complements the 12 factors |
| `layers/LAYERS-MATRIX.md` | Bidirectional cross-reference between layers and factors |
| `layers/01-Layer-1-Frontend.md` | Frontend layer — UI framework, component architecture, build tools |
| `layers/02-Layer-2-APIs-and-Backend-Logic.md` | Backend layer — REST, GraphQL, gRPC, WebSocket, server logic |
| `layers/03-Layer-3-Database-and-Storage.md` | Data layer — SQL, NoSQL, object storage, data modeling |
| `layers/04-Layer-4-Auth-and-Permissions.md` | Auth layer — authentication, authorization, token management, RBAC |
| `layers/05-Layer-5-Hosting-and-Deployment.md` | Deployment layer — platforms, environments, rollout strategies |
| `layers/06-Layer-6-Cloud-and-Compute.md` | Compute layer — cloud providers, serverless, containers, edge |
| `layers/07-Layer-7-CICD-and-Version-Control.md` | Automation layer — CI/CD pipelines, version control strategies |
| `layers/08-Layer-8-Security-and-RLS.md` | Security layer — RLS policies, input validation, CSP, CORS |
| `layers/09-Layer-9-Rate-Limiting.md` | Rate limiting layer — throttling, quotas, DDoS protection |
| `layers/10-Layer-10-Caching-and-CDN.md` | Caching layer — HTTP caching, in-memory caches, CDN, stale-while-revalidate |
| `layers/11-Layer-11-Load-Balancing-and-Scaling.md` | Scaling layer — horizontal/vertical scaling, load balancers, auto-scaling |
| `layers/12-Layer-12-Error-Tracking-and-Logs.md` | Observability layer — logging, error tracking, monitoring, alerting |
| `layers/13-Layer-13-Availability-and-Recovery.md` | Resilience layer — HA, DRP, backups, circuit breakers, chaos engineering |
| `VISION.md` | Project vision statement (referenced in README, currently missing) |
| `CONTRIBUTING.md` | Contribution guidelines (referenced in README, currently missing) |

### Existing files to modify:
| File | Change |
|------|--------|
| `README.md` | Add layers table of contents, reference layers perspective |
| `CODEOWNERS` | Add `layers/* @mavishay` |
| `assests/` → `assets/` | Rename (fix typo), update any internal references |

### Images to create:
| File | Purpose |
|------|---------|
| `images/layers-intro.png` | Cover for layers intro article |
| `images/layer1.png` – `images/layer13.png` | Cover for each layer article |

---

### Task 1: Fix assests/ typo and create missing repo docs

**Files:**
- Rename: `assests/` → `assets/`
- Create: `VISION.md`
- Create: `CONTRIBUTING.md`
- Modify: any article referencing `assests/`

- [ ] **Step 1: Search for internal references to `assests/`**

Run: `rg 'assests' . --type md`

Expected: Any markdown files referencing the misspelled path.

- [ ] **Step 2: Rename directory with git mv**

Run: `git mv assests assets`

- [ ] **Step 3: Fix any internal references found in Step 1**

If any files reference `assests/`, update to `assets/`.

- [ ] **Step 4: Create VISION.md**

Write to `VISION.md`:
```markdown
# Vision

The Modern Full-Stack Developer's Guide: A 12-Factor Approach aims to define a comprehensive, practical methodology for building modern full-stack web applications. Drawing on the collective experience of 50+ Tikal full-stack experts, this guide updates the original 12-factor app methodology for a world where frontend complexity, cloud infrastructure, and developer experience are first-class concerns.

Our vision is a guide that:
- Serves as the definitive reference for fullstack developers at every career stage
- Bridges the gap between frontend, backend, and infrastructure concerns
- Provides actionable patterns, not abstract theory
- Evolves through community contribution and real-world practice
- Covers the full stack from UI components to cloud deployment

This repository contains the source text for the guide. The latest stable version is published on Medium. The `main` branch represents the current approved version; development happens in feature branches and the `next` branch until maintainers agree updates are complete.
```

- [ ] **Step 5: Create CONTRIBUTING.md**

Write to `CONTRIBUTING.md`:
```markdown
# Contributing

We welcome contributions from Tikal team members and the broader fullstack community.

## How to Contribute

1. **Discuss first** — Open an issue or start a discussion to propose changes before writing
2. **Branch strategy** — All work happens on feature branches (e.g., `factor-N-topic`). The `next` branch accumulates changes for the next release. `main` is the current approved version.
3. **Style guide** — Follow the existing article format: cover image, consistent heading hierarchy, case studies grounded in real experience, code examples with language annotations, cross-references to related factors.
4. **Review** — All articles require review by a maintainer. CODEOWNERS defines who must approve changes to each directory.
5. **Commit messages** — Use conventional commits format: `feat:`, `fix:`, `docs:`, `refactor:`
6. **Images** — Place cover images in `images/`. Source files (PSD, Sketch, Figma) go in `assets/`.

## Getting Started

- Read `VISION.md` to understand the project's goals
- Check the README table for articles needing owners
- Review existing articles for style and structure

## Code of Conduct

Be respectful, constructive, and inclusive. Focus on what's best for the guide and its readers.
```

- [ ] **Step 6: Commit housekeeping**

```bash
git add VISION.md CONTRIBUTING.md
git add assets/  # renamed directory
git commit -m "chore: fix assests typo, add VISION.md and CONTRIBUTING.md"
```

---

### Task 2: Update README and CODEOWNERS

**Files:**
- Modify: `README.md`
- Modify: `CODEOWNERS`

- [ ] **Step 1: Add layers section to CODEOWNERS**

Read the current `CODEOWNERS` file first. Then add a new line for the layers directory.

Edit `CODEOWNERS` to add:
```
layers/* @mavishay
```

- [ ] **Step 2: Add Layers table to README.md**

Read the current `README.md`. After the existing "Table of Contents" section (the articles table), add a new section:

```markdown
## Layers Perspective (Complementary View)

A second lens on fullstack development — covering the backend, infrastructure, and operations layers that complement the 12 factors above.

| Layer | Owner | Created | Approved | Published |
|-------|-------|---------|----------|-----------|
| [Intro](layers/00-Intro.md) | @mavishay | ⚪️ | ⚪️ | ⚪️ |
| [Layer 1: Frontend](layers/01-Layer-1-Frontend.md) | @mavishay | ⚪️ | ⚪️ | ⚪️ |
| [Layer 2: APIs & Backend Logic](layers/02-Layer-2-APIs-and-Backend-Logic.md) | @mavishay | ⚪️ | ⚪️ | ⚪️ |
| [Layer 3: Database & Storage](layers/03-Layer-3-Database-and-Storage.md) | @mavishay | ⚪️ | ⚪️ | ⚪️ |
| [Layer 4: Auth & Permissions](layers/04-Layer-4-Auth-and-Permissions.md) | @mavishay | ⚪️ | ⚪️ | ⚪️ |
| [Layer 5: Hosting & Deployment](layers/05-Layer-5-Hosting-and-Deployment.md) | @mavishay | ⚪️ | ⚪️ | ⚪️ |
| [Layer 6: Cloud & Compute](layers/06-Layer-6-Cloud-and-Compute.md) | @mavishay | ⚪️ | ⚪️ | ⚪️ |
| [Layer 7: CI/CD & Version Control](layers/07-Layer-7-CICD-and-Version-Control.md) | @mavishay | ⚪️ | ⚪️ | ⚪️ |
| [Layer 8: Security & RLS](layers/08-Layer-8-Security-and-RLS.md) | @mavishay | ⚪️ | ⚪️ | ⚪️ |
| [Layer 9: Rate Limiting](layers/09-Layer-9-Rate-Limiting.md) | @mavishay | ⚪️ | ⚪️ | ⚪️ |
| [Layer 10: Caching & CDN](layers/10-Layer-10-Caching-and-CDN.md) | @mavishay | ⚪️ | ⚪️ | ⚪️ |
| [Layer 11: Load Balancing & Scaling](layers/11-Layer-11-Load-Balancing-and-Scaling.md) | @mavishay | ⚪️ | ⚪️ | ⚪️ |
| [Layer 12: Error Tracking & Logs](layers/12-Layer-12-Error-Tracking-and-Logs.md) | @mavishay | ⚪️ | ⚪️ | ⚪️ |
| [Layer 13: Availability & Recovery](layers/13-Layer-13-Availability-and-Recovery.md) | @mavishay | ⚪️ | ⚪️ | ⚪️ |
| [Cross-Reference Matrix](layers/LAYERS-MATRIX.md) | @mavishay | ⚪️ | ⚪️ | ⚪️ |
```

- [ ] **Step 3: Update the README's intro text to mention the layers perspective**

Edit `README.md` to add a sentence referencing the new layers perspective after the existing vision/participation text.

- [ ] **Step 4: Commit**

```bash
git add README.md CODEOWNERS
git commit -m "docs: add layers perspective section to README and update CODEOWNERS"
```

---

### Task 3: Create layers directory, intro article, and cross-reference matrix

**Files:**
- Create: `layers/00-Intro.md`
- Create: `layers/LAYERS-MATRIX.md`

- [ ] **Step 1: Create layers directory**

Run: `mkdir -p layers`

- [ ] **Step 2: Read existing articles 00-Intro.md and a few factor articles for format reference**

Read: `articles/00-Intro.md`, `articles/01-Factor-1.md`, `articles/06-Factor-6.md`, `articles/11-Factor-11.md`

- [ ] **Step 3: Write layers/00-Intro.md**

```markdown
# The Full-Stack Layers: A Complementary Perspective
![cover](../images/layers-intro.png)

## Beyond the 12 Factors

The 12 factors focus primarily on frontend-heavy fullstack concerns — UI components, routing, state management, forms, design systems, rendering strategies, i18n, and more. They represent the **application architecture** view.

But a fullstack developer doesn't just work with application architecture. They navigate infrastructure, operations, security, and deployment concerns daily. This complementary **13-layer perspective** captures that side of the stack.

Where the 12 factors ask "How should I structure my frontend?", the 13 layers ask "What do I need to know about every layer between the browser and the database?"

## The 13 Layers at a Glance

| # | Layer | What It Covers |
|---|-------|----------------|
| 1 | Frontend | UI frameworks, component architecture, build tooling, asset pipeline |
| 2 | APIs & Backend Logic | REST, GraphQL, gRPC, WebSocket, server-side business logic |
| 3 | Database & Storage | SQL, NoSQL, object storage, data modeling, migrations |
| 4 | Auth & Permissions | Authentication, authorization, token management, RBAC/ABAC |
| 5 | Hosting & Deployment | Deployment platforms, environments, rollout strategies |
| 6 | Cloud & Compute | Cloud providers, serverless, containers, edge computing |
| 7 | CI/CD & Version Control | Pipelines, branching strategies, automated testing, release management |
| 8 | Security & RLS | Row-level security, input validation, CSP, CORS, secret management |
| 9 | Rate Limiting | Throttling, quota management, DDoS protection, API governance |
| 10 | Caching & CDN | HTTP caching, in-memory caches, content delivery networks |
| 11 | Load Balancing & Scaling | Horizontal/vertical scaling, load balancers, auto-scaling policies |
| 12 | Error Tracking & Logs | Structured logging, error monitoring, alerting, observability |
| 13 | Availability & Recovery | High availability, disaster recovery, backups, circuit breakers |

## How to Read This Perspective

Each layer article follows the same structure:
- **Why This Layer Matters** — strategic importance for fullstack developers
- **Key Considerations** — essential concepts and trade-offs
- **Implementation Patterns & Technologies** — common approaches and tools
- **Common Pitfalls** — anti-patterns and hard-won lessons
- **How This Layer Connects to the 12 Factors** — explicit cross-references
- **Case Study** — real-world example

The [Cross-Reference Matrix](LAYERS-MATRIX.md) shows the bidirectional mapping between layers and factors.

_This article is part of Tikal's Modern Full-Stack Developer's Guide: A 12-Factor Approach series. For the application architecture perspective, see the [main 12 factors](../articles/00-Intro.md)._
```

- [ ] **Step 4: Write layers/LAYERS-MATRIX.md**

```markdown
# Layers-to-Factors Cross-Reference Matrix

This document maps the relationship between the 13 fullstack layers and the original 12 factors. Use it to navigate between the two perspectives.

## Layer → Factors

| Layer | Related Factors |
|-------|----------------|
| 1. Frontend | [Factor 1](../articles/01-Factor-1.md) (UI Libraries), [Factor 3](../articles/03-Factor-3.md) (Design Systems), [Factor 4](../articles/04-Factor-4.md) (Routing), [Factor 5](../articles/05-Factor-5.md) (State), [Factor 7](../articles/07-Factor-7.md) (Rendering), [Factor 8](../articles/08-Factor-8.md) (Forms), [Factor 9](../articles/09-Factor-9.md) (i18n), [Factor 12](../articles/12-Factor-12.md) (A11y/SEO/Perf) |
| 2. APIs & Backend Logic | [Factor 10](../articles/10-Factor-10.md) (BFF), [Factor 11](../articles/11-Factor-11.md) (API Patterns) |
| 3. Database & Storage | [Factor 6](../articles/06-Factor-6.md) (Auth — user data storage), [Factor 11](../articles/11-Factor-11.md) (API — data persistence patterns) |
| 4. Auth & Permissions | [Factor 6](../articles/06-Factor-6.md) (Auth) |
| 5. Hosting & Deployment | [Factor 2](../articles/02-Factor-2.md) (Repo Strategy — monorepo deployment), [Factor 7](../articles/07-Factor-7.md) (Rendering — SSR hosting) |
| 6. Cloud & Compute | [Factor 7](../articles/07-Factor-7.md) (Rendering — serverless/edge), [Factor 10](../articles/10-Factor-10.md) (BFF — edge compute) |
| 7. CI/CD & Version Control | [Factor 2](../articles/02-Factor-2.md) (Repo Strategy) |
| 8. Security & RLS | [Factor 6](../articles/06-Factor-6.md) (Auth — authorization), [Factor 12](../articles/12-Factor-12.md) (A11y/SEO/Perf — security perf) |
| 9. Rate Limiting | [Factor 11](../articles/11-Factor-11.md) (API Patterns) |
| 10. Caching & CDN | [Factor 4](../articles/04-Factor-4.md) (Routing — prefetching), [Factor 7](../articles/07-Factor-7.md) (Rendering — ISR), [Factor 12](../articles/12-Factor-12.md) (Performance) |
| 11. Load Balancing & Scaling | [Factor 7](../articles/07-Factor-7.md) (Rendering — SSR scaling) |
| 12. Error Tracking & Logs | [Supplemental Factor 2](../articles/14-Supplemental-factor-2.md) (Observability) |
| 13. Availability & Recovery | [Factor 7](../articles/07-Factor-7.md) (Rendering — fallback strategies), [Factor 10](../articles/10-Factor-10.md) (BFF — resilience) |

## Factor → Layers

| Factor | Related Layers |
|--------|---------------|
| [Factor 1](../articles/01-Factor-1.md): UI Libraries | Layer 1 (Frontend) |
| [Factor 2](../articles/02-Factor-2.md): Repo Strategy | Layer 7 (CI/CD & Version Control) |
| [Factor 3](../articles/03-Factor-3.md): Design Systems | Layer 1 (Frontend) |
| [Factor 4](../articles/04-Factor-4.md): Routing | Layer 1 (Frontend), Layer 10 (Caching & CDN) |
| [Factor 5](../articles/05-Factor-5.md): State Management | Layer 1 (Frontend) |
| [Factor 6](../articles/06-Factor-6.md): Auth | Layer 3 (Database), Layer 4 (Auth & Permissions), Layer 8 (Security) |
| [Factor 7](../articles/07-Factor-7.md): Rendering | Layer 1 (Frontend), Layer 5 (Hosting), Layer 6 (Cloud), Layer 10 (Caching), Layer 11 (Scaling), Layer 13 (Availability) |
| [Factor 8](../articles/08-Factor-8.md): Forms | Layer 1 (Frontend) |
| [Factor 9](../articles/09-Factor-9.md): i18n | Layer 1 (Frontend) |
| [Factor 10](../articles/10-Factor-10.md): BFF | Layer 2 (APIs), Layer 6 (Cloud), Layer 13 (Availability) |
| [Factor 11](../articles/11-Factor-11.md): API Patterns | Layer 2 (APIs), Layer 3 (Database), Layer 9 (Rate Limiting) |
| [Factor 12](../articles/12-Factor-12.md): A11y/SEO/Perf | Layer 1 (Frontend), Layer 8 (Security), Layer 10 (Caching) |
| [Supp Factor 1](../articles/13-Supplemental-factor-1.md): Testing | Layer 7 (CI/CD) |
| [Supp Factor 2](../articles/14-Supplemental-factor-2.md): Observability | Layer 12 (Error Tracking & Logs) |
| [Supp Factor 3](../articles/15-Supplemental-factor-3.md): Micro-Frontends | Layer 1 (Frontend), Layer 5 (Hosting), Layer 7 (CI/CD) |
| [Supp Factor 4](../articles/16-Supplemental-factor-4.md): Responsive | Layer 1 (Frontend), Layer 10 (Caching & CDN) |
```

- [ ] **Step 5: Verify markdown renders correctly**

Run: `find layers -name '*.md' -exec echo "Checking {}" \;`

- [ ] **Step 6: Commit**

```bash
git add layers/
git commit -m "feat: add layers intro and cross-reference matrix"
```

---

### Task 4: Write Layer 1 — Frontend

**Files:**
- Create: `layers/01-Layer-1-Frontend.md`

- [ ] **Step 1: Read existing articles for style reference**

Read: `articles/01-Factor-1.md` (UI Libraries) and `articles/03-Factor-3.md` (Design Systems) to understand the existing voice.

- [ ] **Step 2: Write Layer 1 — Frontend article**

Write `layers/01-Layer-1-Frontend.md` following the Article Format Template above.

Content briefing (expand each section into full prose):
- **TL;DR** — The frontend layer encompasses everything the user sees: UI frameworks, component architecture, build tooling, asset pipelines, browser runtime. Fullstack developers must balance DX, performance, a11y, and cross-browser compat.
- **Why This Layer Matters** — The frontend is the user's interface to every other layer. Framework choice (React/Angular/Vue/Svelte/Solid/Qwik) determines team hiring, ecosystem access, build tooling, and rendering strategy. Component architecture patterns (composition, compound components) directly impact maintainability at scale. Build tooling (Vite, Turbopack) determines iteration speed.
- **Key Considerations** — Framework selection and its downstream effects; component architecture patterns; build tooling and bundle optimization; asset pipeline (fonts, images, SVGs, code splitting); browser API constraints
- **Implementation Patterns** — Component composition vs inheritance; styling approaches (CSS modules, CSS-in-JS, utility-first); code splitting by route; lazy loading of below-fold assets; web workers for CPU-intensive tasks
- **Common Pitfalls** — Bundle bloat from unused dependencies; over-abstracting too early; ignoring cumulative layout shift; assuming all browsers support same APIs; neglecting error boundaries
- **Cross-Refs** — Factor 1 (UI Libraries — every tooling decision flows from this); Factor 3 (Design Systems — design tokens enforced in this layer); Factor 4 (Routing — code-splitting boundaries); Factor 5 (State — client-side architecture); Factor 7 (Rendering — CSR/SSR/SSG/ISR delivery); Factor 8 (Forms — frontend concern with backend implications); Factor 9 (i18n — every visible string); Factor 12 (A11y/SEO/Perf — measured in the frontend)
- **Case Study** — Tikal helped a fintech startup migrate from a jQuery monolith to a React component architecture. Lead time for new features dropped from 3 weeks to 4 days. Key: incremental migration via micro-frontend pattern (Module Federation), shared design system built in parallel, phased rollout by product area.
- **Aim for 300-600 lines of content, matching the depth of existing factor articles.**

- [ ] **Step 3: Review for formatting consistency**

Check that headings, image paths, and cross-reference links follow the established format.

- [ ] **Step 4: Commit**

```bash
git add layers/01-Layer-1-Frontend.md
git commit -m "feat: add Layer 1 - Frontend article"
```

---

### Task 5: Write Layer 2 — APIs & Backend Logic

**Files:**
- Create: `layers/02-Layer-2-APIs-and-Backend-Logic.md`

- [ ] **Step 1: Read existing articles for cross-reference context**

Read: `articles/10-Factor-10.md` (BFF), `articles/11-Factor-11.md` (API Patterns)

- [ ] **Step 2: Write Layer 2 — APIs & Backend Logic article**

Write `layers/02-Layer-2-APIs-and-Backend-Logic.md` following the Article Format Template.

Key content to cover:
- API styles: REST, GraphQL, gRPC, WebSocket — tradeoffs and use cases
- Backend architecture: monolithic vs microservices vs serverless
- Request lifecycle from client to database and back
- Error handling patterns, validation, middleware
- Cross-references to Factor 10 (BFF) and Factor 11 (API Patterns)

- [ ] **Step 3: Commit**

```bash
git add layers/02-Layer-2-APIs-and-Backend-Logic.md
git commit -m "feat: add Layer 2 - APIs & Backend Logic article"
```

---

### Task 6: Write Layer 3 — Database & Storage

**Files:**
- Create: `layers/03-Layer-3-Database-and-Storage.md`

- [ ] **Step 1: Write Layer 3 — Database & Storage article**

Write `layers/03-Layer-3-Database-and-Storage.md`.

Key content:
- SQL vs NoSQL decision framework
- Object storage (S3, blob storage) and CDN integration
- Data modeling: normalization, denormalization, indexing
- Migration strategies
- Connection pooling, query optimization
- Cross-refs: Factor 6 (Auth — user data), Factor 11 (API — data persistence)

- [ ] **Step 2: Commit**

```bash
git add layers/03-Layer-3-Database-and-Storage.md
git commit -m "feat: add Layer 3 - Database & Storage article"
```

---

### Task 7: Write Layer 4 — Auth & Permissions

**Files:**
- Create: `layers/04-Layer-4-Auth-and-Permissions.md`

- [ ] **Step 1: Read Factor 6 for cross-reference alignment**

Read: `articles/06-Factor-6.md` (Authentication & Authorization)

- [ ] **Step 2: Write Layer 4 — Auth & Permissions article**

Write `layers/04-Layer-4-Auth-and-Permissions.md`.

Key content:
- Authentication: OAuth2, OIDC, SAML, passwordless, MFA
- Authorization: RBAC, ABAC, PBAC — when to use which
- Token lifecycle: JWTs, refresh tokens, rotation
- Session management (server-side vs stateless)
- Frontend auth patterns: protected routes, token refresh interceptor
- Cross-ref: Factor 6 (Auth), Factor 10 (BFF — auth proxy), Factor 11 (API — auth middleware)

- [ ] **Step 3: Commit**

```bash
git add layers/04-Layer-4-Auth-and-Permissions.md
git commit -m "feat: add Layer 4 - Auth & Permissions article"
```

---

### Task 8: Write Layer 5 — Hosting & Deployment

**Files:**
- Create: `layers/05-Layer-5-Hosting-and-Deployment.md`

- [ ] **Step 1: Write Layer 5 — Hosting & Deployment article**

Write `layers/05-Layer-5-Hosting-and-Deployment.md`.

Key content:
- Deployment platforms: Vercel, Netlify, Railway, Fly.io, self-hosted
- Environment management: dev, staging, production, preview deployments
- Rollout strategies: blue-green, canary, feature flags
- Infrastructure as Code: Terraform, Pulumi, CloudFormation
- Cross-ref: Factor 2 (Repo Strategy — monorepo deployment), Factor 7 (Rendering — SSR hosting)

- [ ] **Step 2: Commit**

```bash
git add layers/05-Layer-5-Hosting-and-Deployment.md
git commit -m "feat: add Layer 5 - Hosting & Deployment article"
```

---

### Task 9: Write Layer 6 — Cloud & Compute

**Files:**
- Create: `layers/06-Layer-6-Cloud-and-Compute.md`

- [ ] **Step 1: Write Layer 6 — Cloud & Compute article**

Write `layers/06-Layer-6-Cloud-and-Compute.md`.

Key content:
- Cloud providers: AWS, GCP, Azure — service model comparison
- Compute models: VMs, containers (Docker, K8s), serverless (Lambda, Cloud Functions), edge (Cloudflare Workers, Deno Deploy)
- Cost management: right-sizing, reserved instances, spot instances
- Multi-cloud and vendor lock-in considerations
- Cross-ref: Factor 7 (Rendering — serverless/edge), Factor 10 (BFF — edge compute)

- [ ] **Step 2: Commit**

```bash
git add layers/06-Layer-6-Cloud-and-Compute.md
git commit -m "feat: add Layer 6 - Cloud & Compute article"
```

---

### Task 10: Write Layer 7 — CI/CD & Version Control

**Files:**
- Create: `layers/07-Layer-7-CICD-and-Version-Control.md`

- [ ] **Step 1: Read Factor 2 for cross-reference alignment**

Read: `articles/02-Factor-2.md` (Repository Strategy)

- [ ] **Step 2: Write Layer 7 — CI/CD & Version Control article**

Write `layers/07-Layer-7-CICD-and-Version-Control.md`.

Key content:
- Version control strategies: Git flow, trunk-based, GitHub Flow
- CI/CD pipeline stages: lint, test, build, deploy, verify
- Pipeline tools: GitHub Actions, GitLab CI, CircleCI, Jenkins
- Artifact management, semantic versioning, changelogs
- Cross-ref: Factor 2 (Repo Strategy — monorepo tooling)

- [ ] **Step 2: Commit**

```bash
git add layers/07-Layer-7-CICD-and-Version-Control.md
git commit -m "feat: add Layer 7 - CI/CD & Version Control article"
```

---

### Task 11: Write Layer 8 — Security & RLS

**Files:**
- Create: `layers/08-Layer-8-Security-and-RLS.md`

- [ ] **Step 1: Read existing articles for cross-reference alignment**

Read: `articles/06-Factor-6.md` (Auth), `articles/08-Factor-8.md` (Forms — input validation)

- [ ] **Step 2: Write Layer 8 — Security & RLS article**

Write `layers/08-Layer-8-Security-and-RLS.md`.

Key content:
- Row-level security (RLS) policies in Supabase, Postgres, Firebase
- Input validation: client-side vs server-side, sanitization
- Content Security Policy (CSP), CORS, CSRF protection
- Secret management: environment variables, vaults, KMS
- Dependency scanning, SAST, DAST
- Cross-ref: Factor 6 (Auth), Factor 8 (Forms — CSRF), Factor 12 (Security performance)

- [ ] **Step 3: Commit**

```bash
git add layers/08-Layer-8-Security-and-RLS.md
git commit -m "feat: add Layer 8 - Security & RLS article"
```

---

### Task 12: Write Layer 9 — Rate Limiting

**Files:**
- Create: `layers/09-Layer-9-Rate-Limiting.md`

- [ ] **Step 1: Read Factor 11 for cross-reference alignment**

Read: `articles/11-Factor-11.md` (API Patterns)

- [ ] **Step 2: Write Layer 9 — Rate Limiting article**

Write `layers/09-Layer-9-Rate-Limiting.md`.

Key content:
- Rate limiting strategies: token bucket, leaky bucket, fixed window, sliding window
- Implementation layers: API gateway, application middleware, CDN edge
- Quota management: per-user, per-IP, per-route
- DDoS protection: Cloudflare, AWS Shield, Google Cloud Armor
- Return codes: 429 Too Many Requests, Retry-After header
- Cross-ref: Factor 11 (API — throttling patterns)

- [ ] **Step 3: Commit**

```bash
git add layers/09-Layer-9-Rate-Limiting.md
git commit -m "feat: add Layer 9 - Rate Limiting article"
```

---

### Task 13: Write Layer 10 — Caching & CDN

**Files:**
- Create: `layers/10-Layer-10-Caching-and-CDN.md`

- [ ] **Step 1: Write Layer 10 — Caching & CDN article**

Write `layers/10-Layer-10-Caching-and-CDN.md`.

Key content:
- HTTP caching: Cache-Control, ETag, Last-Modified, stale-while-revalidate
- In-memory caching: Redis, Memcached — strategies (LRU, TTL)
- CDN: Cloudflare, Akamai, Fastly — edge caching, purge, warm-up
- Application caching: SWR, React Query cache, ISR
- Cache invalidation: the hardest problem, patterns and approaches
- Cross-ref: Factor 4 (Routing — prefetching), Factor 7 (Rendering — ISR), Factor 12 (Performance — Core Web Vitals)

- [ ] **Step 2: Commit**

```bash
git add layers/10-Layer-10-Caching-and-CDN.md
git commit -m "feat: add Layer 10 - Caching & CDN article"
```

---

### Task 14: Write Layer 11 — Load Balancing & Scaling

**Files:**
- Create: `layers/11-Layer-11-Load-Balancing-and-Scaling.md`

- [ ] **Step 1: Write Layer 11 — Load Balancing & Scaling article**

Write `layers/11-Layer-11-Load-Balancing-and-Scaling.md`.

Key content:
- Horizontal vs vertical scaling: when each makes sense
- Load balancers: ALB/ELB, Nginx, HAProxy, Cloudflare
- Auto-scaling policies: CPU-based, request-based, schedule-based
- Stateful vs stateless scaling considerations
- Database scaling: read replicas, sharding, connection pooling
- Cross-ref: Factor 7 (Rendering — SSR scaling)

- [ ] **Step 2: Commit**

```bash
git add layers/11-Layer-11-Load-Balancing-and-Scaling.md
git commit -m "feat: add Layer 11 - Load Balancing & Scaling article"
```

---

### Task 15: Write Layer 12 — Error Tracking & Logs

**Files:**
- Create: `layers/12-Layer-12-Error-Tracking-and-Logs.md`

- [ ] **Step 1: Read Supplemental Factor 2 for cross-reference alignment**

Read: `articles/14-Supplemental-factor-2.md` (Observability & Error Management)

- [ ] **Step 2: Write Layer 12 — Error Tracking & Logs article**

Write `layers/12-Layer-12-Error-Tracking-and-Logs.md`.

Key content:
- Structured logging: JSON logs, log levels, context enrichment
- Error tracking: Sentry, Datadog, Rollbar — frontend + backend
- Distributed tracing: OpenTelemetry, Jaeger, Zipkin
- Metrics and dashboards: Prometheus + Grafana, Datadog
- Alerting: on-call rotation, escalation, PagerDuty/Opsgenie
- Cross-ref: Supplemental Factor 2 (Observability)

- [ ] **Step 3: Commit**

```bash
git add layers/12-Layer-12-Error-Tracking-and-Logs.md
git commit -m "feat: add Layer 12 - Error Tracking & Logs article"
```

---

### Task 16: Write Layer 13 — Availability & Recovery

**Files:**
- Create: `layers/13-Layer-13-Availability-and-Recovery.md`

- [ ] **Step 1: Write Layer 13 — Availability & Recovery article**

Write `layers/13-Layer-13-Availability-and-Recovery.md`.

Key content:
- High availability: redundancy, multi-AZ, multi-region
- Disaster recovery: RPO, RTO, backup strategies, restore testing
- Patterns: circuit breakers, bulkheads, retries with backoff, timeouts
- Chaos engineering: principles, tools (Chaos Monkey, Gremlin)
- SLA/SLO/SLI: defining and measuring reliability
- Cross-ref: Factor 7 (Rendering — fallback strategies), Factor 10 (BFF — resilience patterns)

- [ ] **Step 2: Commit**

```bash
git add layers/13-Layer-13-Availability-and-Recovery.md
git commit -m "feat: add Layer 13 - Availability & Recovery article"
```

---

### Task 17: Create cover images

**Files:**
- Create: `images/layers-intro.png`
- Create: `images/layer1.png` through `images/layer13.png`

- [ ] **Step 1: Check existing image style**

Check the existing images in `images/` for style reference. Check if the PSD files in `assets/` (`tikal.psd`, `3974875.psd`) contain templates or source files for the factor covers.

- [ ] **Step 2: Create cover images**

Generate 14 cover images consistent with the existing `factorN.png` style. One of these approaches:
- Use the PSD template in `assets/` if it exists and create a batch
- Create new images matching the existing style (dimensions, typography, color scheme)
- Each image should show the layer number and layer name

- [ ] **Step 3: Commit**

```bash
git add images/layer*.png images/layers-intro.png
git commit -m "feat: add cover images for layers perspective"
```

---

### Task 18: Final formatting pass

**Files:**
- Verify: all files in `layers/`

- [ ] **Step 1: Verify all links work**

Run a grep for broken markdown links in the layers directory:
`rg '\]\(\.\./articles/' layers/ --type md`

Check each referenced article exists.

- [ ] **Step 2: Verify all image references point to existing files**

`rg '\]\(\.\./images/' layers/ --type md`

Check each referenced image exists.

- [ ] **Step 3: Verify consistent formatting**

Manually spot-check 2-3 layer articles for:
- Heading hierarchy (no jumps from ## to ####)
- Code blocks have language annotations
- Consistent footer style
- No trailing whitespace

- [ ] **Step 4: Print final structure**

```bash
echo "=== layers/ ===" && ls -la layers/*.md | wc -l && echo "files" && echo "=== images/ ===" && ls -la images/layer*.png images/layers-intro.png 2>/dev/null | wc -l && echo "layer images"
```

- [ ] **Step 5: Commit any final fixes**

```bash
git add -A
git commit -m "chore: final formatting pass on layers perspective"
```
