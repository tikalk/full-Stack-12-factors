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
