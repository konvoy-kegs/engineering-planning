# Konvoy Kegs — Engineering Sprint Planning

You are helping **Robert Wilde (Rob)**, Head of Engineering at **Konvoy Kegs**, manage sprint planning, retrospectives, and engineering dashboards for the **Katch Cloud** platform.

## Company & Product

Konvoy Kegs is an Australian keg logistics company. **Katch Cloud** is the internal SaaS platform that manages orders, assets (kegs), collections, invoicing, and integrations with external systems (NetSuite, Carton Cloud). The platform serves both Konvoy staff and external customers (breweries/producers).

## Tech Stack

- **Backend:** PHP 8.4, Laravel 12, Symfony components
- **Testing:** PEST PHP 4
- **Frontend:** React (Next.js on Vercel)
- **Infrastructure:** AWS (EKS/Kubernetes), Dokploy, RDS MySQL 8.4, KEDA autoscaling
- **Monitoring:** Grafana Cloud, Sentry, OpenTelemetry
- **Integrations:** NetSuite (accounting/invoicing), Carton Cloud (logistics)
- **Feature flags:** LaunchDarkly
- **CI/CD:** GitHub Actions, Vercel (frontend)

## Team Structure (as of April 2026)

| Person | Role | Focus |
|--------|------|-------|
| **Rob Wilde** | Head of Engineering | Infrastructure, PR reviews, backend, DevOps, AWS/K8s. Also the primary (often only) PR reviewer. |
| **Millicent Convento** | Backend Developer | PHP/Symfony, Orders API, NetSuite integration, database work |
| **Bea Bain** | Frontend Developer (Contractor) | React, UI/UX. New — joined to replace Doug. Ramping up. |

**Recently departed:** Doug Bamber (Frontend Developer) — left early April 2026. Built the core Orders frontend (table, forms, charts, side panels). Handover recordings in SharePoint → Development → Recordings. All his open tickets transferred to Bea.

The team is small (3 devs). Rob has been clear that **measuring individual output is not productive at this team size** — retros and reports should focus on team-level output and themes, not individual metrics.

## Project Board

- **GitHub Projects URL:** https://github.com/orgs/konvoy-kegs/projects/4
- **Board name:** Katch Cloud
- **Views:** Kanban (default), Timeline, By Priority, Orders, Netsuite, My View
- **Workflow columns:** No Status → Backlog → Discovery → Ready → In-Progress → Review → QA → Done

### GitHub Insights Charts

These custom charts exist on the project Insights page:

| Chart | Type | Purpose |
|-------|------|---------|
| Burn up | Default (time-based) | Overall progress trajectory |
| Items by Status | Stacked column | Pipeline snapshot |
| Priority | Line (X: Priority, Group: Size) | Priority/effort distribution |
| Work by Label & Status | Stacked column | Where effort sits by work type |
| Items by Size | Stacked column | Effort distribution by story points |
| Completed by Label | Column, filtered to Done | What was shipped — the retro highlight chart |

### Sizing Convention

Story points use T-shirt sizes on the board: Small (1), Medium (3), Large (5), X-Large (8). Sustainable sprint velocity for Rob is approximately 20–25 SP per 2-week sprint.

## Sprint Cadence

- **2-week sprints**
- Sprint goals are typically 3 themes agreed with CEO/COO
- Rob wants a hard **scope freeze after Day 8** — no new work pulled in after that
- **Review column WIP limit of 5** is the target (this was a problem in Sprint 2 — peaked at 14)
- Friday review blitz blocks are recommended to prevent Review bottleneck

## Engineering Planning Repository

**Repository:** https://github.com/konvoy-kegs/engineering-planning
**Published site:** https://konvoy-kegs.github.io/engineering-planning/

This repo hosts sprint review dashboards as static HTML pages deployed via GitHub Pages.

### Repository Structure

```
engineering-planning/
├── .nojekyll                          # Bypass Jekyll processing
├── README.md
├── index.html                         # Landing page with card links to each sprint review
├── sprint-review-2026-04-03.html      # Sprint 2 end-of-sprint snapshot
└── sprint-review-2026-04-08.html      # Sprint 2 retro + Sprint 3 planning
```

### How to Add a New Sprint Review

1. Create a new HTML file: `sprint-review-YYYY-MM-DD.html`
2. Add a card entry at the top of the grid in `index.html` (move the "Latest" badge to the new card, remove it from the previous one)
3. Push to `main` — GitHub Pages deploys automatically

### Dashboard Template Conventions

- **Dark theme** using CSS custom properties: `--bg: #0f172a`, `--surface: #1e293b`, `--surface2: #334155`, `--text: #f1f5f9`, `--muted: #94a3b8`, `--accent: #38bdf8`
- **Charts:** Chart.js 4.4.1 via CDN (`https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.min.js`)
- Chart types used: doughnut (status breakdown), horizontal bar (completed by person), stacked bar (open items), polar area (labels)
- **Badge classes:** `.badge-done` (green), `.badge-review` (yellow), `.badge-progress` (blue), `.badge-ready` (purple), `.badge-backlog` (grey), `.badge-discovery` (pink), `.badge-qa` (cyan), `.badge-urgent` (red)
- **Section structure:** KPI stat cards → Charts row → Per-person breakdown tables → Dependency/risk sections → Action items
- Person cards include an avatar circle, stats row, and ticket tables grouped by status
- Issues link to `https://github.com/konvoy-kegs/konvoy/issues/{number}` (main monorepo) or `https://github.com/konvoy-kegs/kubernetes/issues/{number}` (infra repo)

### Existing Dashboards

**sprint-review-2026-04-03.html** — End-of-sprint snapshot for Sprint 2 (March 23 – April 3). Contains: Doug's departure alert and handover items, KPI stats (47 done, 7 review, 30 open), per-person breakdown (Doug, Millicent, Rob, Bea), Doug dependency mapping, and Chart.js visualizations.

**sprint-review-2026-04-08.html** — Sprint 2 retrospective + Sprint 3 planning. Contains: Sprint 2 outcome summary, alerts (Doug departed, Rob overloaded), retrospective columns (went well / review / process questions), entering-Sprint-3 team breakdown with capacity bars, Fuel Levy epic dependency map, Sprint 3 goals, items to watch, and prioritized action items.

## Sprint History

### Sprint 1 (March 9–20, 2026)

- First sprint under Rob's leadership
- Establishing processes and baseline velocity

### Sprint 2 (March 23 – April 3, 2026)

- **47 items completed** (Rob: 20, Millicent: 14, Doug: 5 board + ~15 PRs, Unassigned: 8)
- Doug Bamber departed mid-sprint; all tickets handed to Bea Bain
- Key deliverables: Orders table redesign, year-over-year charts, NS billing email tooling, Grafana alerting
- Issues: Review bottleneck peaked at 14 items (3x normal), 80+ SP of unplanned work pulled in mid-sprint vs 24 SP planned, milestone tracking was poor (8% at mid-sprint despite active work)

### Sprint 3 (April 8–22, 2026)

- **Goal 1:** Fuel Levy backend — complete FL-1 through FL-6 (backend foundation + API + NS integration). #1 business priority from CEO/COO.
- **Goal 2:** Clear review backlog — merge or close all carried-forward Review items. Target Review column under 5 by Day 5.
- **Goal 3:** Bea onboarding — get her to first PR merged. Start with smaller Doug-adjacent tickets.
- Rob entered overloaded at 35+ SP (sustainable is ~22 SP)
- FL backend tickets #4501-4503 are unassigned and blocking — recommended for Millicent

## Key Active Epics

### Fuel Levy (#4493) — P0

Full-stack feature: surcharge as % of freight, configurable by region/state/location/customer, flows to NetSuite as separate line item. 14 total tickets. Backend must complete first to unblock frontend.

- Backend blockers (unassigned): #4500 (discovery), #4501 (entity/migration), #4502 (rate service), #4503 (order integration)
- Assigned to Rob: #4504 (CRUD API), #4505 (NS invoice integration), #4506-4509 (UI/reporting)

### NetSuite Integration Epics

Multiple epics in Discovery or Backlog, primarily owned by Millicent:

- Epic 0: Foundation (#4296) — X-Large, critical path for all NS work
- Epic 2: Credit Memos (#4315) — 22 SP, Low priority
- Epic 3: Posting Period (#4302) — 1 SP, High priority
- Epic 5: Hybrid Customers (#4337) — 6 SP
- Epic 7: Bulk Forecast Upload (#4327) — 8 SP
- Epic 8: Reporting/CSV (#4304) — 6 SP, High priority
- Epic 9: Contract PDFs (#4340) — 8 SP, assigned to Bea

### NS Security Audit (#4532)

13 sub-tasks, compliance-driven (not tech debt). Unpointed. Recommendation is to timebox investigation tickets to prevent them consuming an entire sprint.

### Orders Experience (#4377)

Epic transferred from Doug to Bea. Includes: email status indicator, location side panel, fixed columns, collection request detail page, and several frontend enhancements.

## Working Preferences

- Rob codes in **PHP 8.4 with Laravel 12** and tests with **PEST PHP 4**
- Sprint retro reports should be **Obsidian-compatible markdown** with YAML frontmatter when saved as `.md` files
- Dashboard HTML files follow the dark-theme template described above
- When gathering board data, use Claude in Chrome to browse the GitHub project board and Insights charts
- Reports should tell a **narrative** ("We made significant progress on NetSuite integration while clearing a backlog of frontend bugs") rather than just listing numbers
- **Never break down retro work by individual developer** — focus on team-level themes
- Every report section should be **actionable** — frame facts as discussion points or decisions

## Useful Links

| Resource | URL |
|----------|-----|
| Katch Cloud Project Board | https://github.com/orgs/konvoy-kegs/projects/4 |
| Engineering Planning (GitHub Pages) | https://konvoy-kegs.github.io/engineering-planning/ |
| Engineering Planning Repo | https://github.com/konvoy-kegs/engineering-planning |
| Main Monorepo | https://github.com/konvoy-kegs/konvoy |
| Kubernetes/Infra Repo | https://github.com/konvoy-kegs/kubernetes |
| Sentry | https://konvoy-katch.sentry.io |

## Files in This Folder

This folder (`engineering-planning`) contains the latest copies of the repo files:

- `index.html` — Landing page (updated with Sprint 2 retro card)
- `sprint-review-2026-04-03.html` — Sprint 2 end-of-sprint snapshot
- `sprint-review-2026-04-08.html` — Sprint 2 retro + Sprint 3 planning dashboard

These files should be pushed to `https://github.com/konvoy-kegs/engineering-planning` to deploy.
