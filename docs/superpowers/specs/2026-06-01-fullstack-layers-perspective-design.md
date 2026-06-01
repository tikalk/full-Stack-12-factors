# Full-Stack Layers Perspective: A Complementary View

**Date:** 2026-06-01
**Status:** Draft

## Purpose

The existing 12-factor model focuses on **frontend-heavy fullstack concerns** — UI components, routing, state management, forms, design systems, rendering strategies, i18n, etc. This design adds a complementary **13-layer perspective** that covers the **backend/infrastructure/operations side** of fullstack development.

The goal is NOT to replace the 12 factors. The goal is to give fullstack developers a second lens to look through — one that covers the layers they touch daily but that the original factors don't explicitly name.

## Directory Structure

All new content lives in a `layers/` directory at the repo root, parallel to `articles/`:

```
layers/
├── 00-Intro.md
├── 01-Layer-1-Frontend.md
├── 02-Layer-2-APIs-and-Backend-Logic.md
├── 03-Layer-3-Database-and-Storage.md
├── 04-Layer-4-Auth-and-Permissions.md
├── 05-Layer-5-Hosting-and-Deployment.md
├── 06-Layer-6-Cloud-and-Compute.md
├── 07-Layer-7-CICD-and-Version-Control.md
├── 08-Layer-8-Security-and-RLS.md
├── 09-Layer-9-Rate-Limiting.md
├── 10-Layer-10-Caching-and-CDN.md
├── 11-Layer-11-Load-Balancing-and-Scaling.md
├── 12-Layer-12-Error-Tracking-and-Logs.md
├── 13-Layer-13-Availability-and-Recovery.md
└── LAYERS-MATRIX.md
```

Image files go in `images/` following the existing pattern: `images/layer1.png` through `images/layer13.png`, plus `images/layers-intro.png`.

## Naming Convention

- `NN-Layer-N-<Short-Name>.md` — matches the pattern `NN-Factor-N.md` used in articles/
- Dashes between words in the short name
- Layers with "&" use "and" in the filename for filesystem compatibility

## Article Format

Each layer article follows the established format from the existing factors:

```markdown
# Layer N: Layer Name
![cover](../images/layerN.png)

## Subtitle / TL;DR
One-paragraph summary of what this layer covers and why it matters.

## Why This Layer Matters
Strategic importance from a fullstack developer's perspective.

## Key Considerations for Fullstack Developers
What a fullstack dev needs to know about this layer — not a deep-dive, but the essential concepts, trade-offs, and decision points.

## Implementation Patterns & Technologies
Common patterns, tools, frameworks, and services. Code examples where relevant.

## Common Pitfalls
Anti-patterns, gotchas, and lessons learned (drawing on Tikal's consulting experience).

## How This Layer Connects to the 12 Factors
Explicit cross-references to relevant existing factors. For example:
- Layer 4 (Auth & Permissions) → Factor 6 (Auth), Factor 11 (API Patterns), Factor 12 (Accessibility/SEO/Performance)
- Layer 2 (APIs & Backend Logic) → Factor 10 (BFF), Factor 11 (API Patterns)

## Case Study
Real-world example from Tikal's experience, matching the narrative style of existing case studies.

## Conclusion
Key takeaways and call to action.

_This article is part of Tikal's Modern Full-Stack Developer's Guide: A 12-Factor Approach series..._
```

## Cross-Reference Matrix (LAYERS-MATRIX.md)

A standalone reference document showing bidirectional mappings:

### Layer → Factors
Table mapping each of the 13 layers to the existing factors they relate to.

### Factor → Layers
Table mapping each of the 12 existing factors to the layers they touch.

This document serves as a quick-reference navigation tool for readers who want to understand how the two perspectives connect.

## Housekeeping Items

1. **Rename `assests/` → `assets/`** (fix misspelling), update any internal references
2. **Create `VISION.md`** with the project's vision (referenced in README but missing)
3. **Create `CONTRIBUTING.md`** with contribution guidelines (referenced in README but missing)
4. **Update README.md** to add a Layers table of contents below the existing articles table
5. **Update CODEOWNERS** to include `layers/*`

## Image Strategy

Each layer gets a cover image (PNG) in `images/`, consistent with existing factor covers. Either:
- Created from the same source PSD template in `assets/`
- Or generated as new artwork with a consistent style

## Order of Implementation

Suggested writing order (by dependency/logical grouping):

1. **Intro + Matrix** (foundation — sets up the entire perspective)
2. **Layer 1: Frontend** (natural bridge from existing factors)
3. **Layer 2: APIs & Backend Logic** (core backend concern)
4. **Layer 3: Database & Storage** (data layer)
5. **Layer 4: Auth & Permissions** (security baseline)
6. **Layer 8: Security & RLS** (deepens security)
7. **Layer 9: Rate Limiting** (API protection)
8. **Layer 5: Hosting & Deployment** (delivery)
9. **Layer 6: Cloud & Compute** (infrastructure)
10. **Layer 7: CI/CD & Version Control** (automation)
11. **Layer 10: Caching & CDN** (performance)
12. **Layer 11: Load Balancing & Scaling** (reliability)
13. **Layer 12: Error Tracking & Logs** (observability)
14. **Layer 13: Availability & Recovery** (resilience)
