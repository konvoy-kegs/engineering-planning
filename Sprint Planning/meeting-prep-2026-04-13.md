---
title: Monday Meeting Prep — CEO/COO/Doug Farewell
date: 2026-04-13
sprint: "Sprint 3 (April 8–22)"
type: meeting-prep
participants: [Rob Wilde, CEO, COO, Doug Bamber]
---

# Monday Meeting Prep — April 13, 2026

Doug's final meeting with leadership. The purpose is to confirm handover completeness, review current sprint state, and align on quarterly priorities after the NS breach disruption.

---

## 1. Doug Bamber — Completed Work Summary

Doug closed **47 issues** across his tenure, almost entirely within the Orders Experience domain. This is the foundation the team will build on going forward.

### Major Deliverables

**Orders Table & Core Workflow (Oct 2025 – Jan 2026)**
Built the entire Orders frontend from the ground up: orders table (#4059), page routing (#4074), create/view order (#4100), complete order (#4148), schedule order (#4146), cancel order (#4139), unschedule order (#4147), order logs (#4145), order filtering (#4143), order pricing (#4144), order invoicing (#4149), order charts (#4150), and the feature flag gating (#4151).

**Orders Enhancements & Polish (Feb – Mar 2026)**
Internal notes (#4287), filter by source (#4348), export/download restrictions (#4351), field naming consistency (#4352), reset filters (#4279), legacy redirect routing (#4402), admin pricing edit (#4409), collections UI updates (#4435), prefill formatting (#4446), organisation details side panel (#4429), organisation orders list (#4430), admin SKU visibility (#4411), mobile fullscreen modal (#4519), pallet-size enforcement (#4497), pallet constraint for transfers (#4512), year-over-year charts (#4451), internal notes display (#4521), hide actioned collection requests (#4523), targeted date ranges for ops (#4345), activity log visibility (#4495), and a crash fix on Rentals (#4546).

**Other Frontend Work**
Activity logs on Organisation page (#4245), schedule collections at creation (#4269), transport consignment number (#4273), form improvements (#4251), and CSS specificity fix (#4551).

### Doug's Still-Open Tickets (10 items — need reassignment)

These are all still assigned to `doug-bamber-konvoy` and need to be reassigned to Bea or triaged:

| # | Title | Notes |
|---|-------|-------|
| 4526 | Decouple leases from orders feature | Large — architecture change. Needs careful scoping for Bea. |
| 4290 | Customisable column visibility/sort | Doug had context on this — may need discovery. |
| 4153 | Add assets to order | Sprint 1 leftover. Core feature gap. |
| 4152 | Lease Orders | Sprint 1 leftover. Depends on lease decoupling (#4526). |
| 4636 | Remove fully-rolled-out feature flags | Housekeeping — good starter for Bea. |
| 4498 | Fix button anchor text (mobile Safari) | Quick CSS fix. |
| 4475 | Transfers: Update Rainforest QA E2E Tests | QA automation. |
| 4474 | Rentals: Update Rainforest QA E2E Tests | QA automation. |
| 4473 | Collections: Update Rainforest QA E2E Tests | QA automation. |
| 4371 | Filter Orders by Account Manager | No milestone, standalone. |

**Action:** Reassign all 10 to Bea or unassign and triage. The three Rainforest QA tickets (#4473-4475) could be grouped into one effort.

---

## 2. Current Sprint State — What's Underway?

### Sprint 3 Velocity (Apr 8–11, Day 3 of 10)

**14 items closed since Apr 3.** However, the majority were NS breach recovery work, not planned Sprint 3 tickets:

| Closed | Title | Who |
|--------|-------|-----|
| Apr 10 | #4631 Fix NS location-subsidiary mismatch (WA invoices) | Rob |
| Apr 8 | #4562 Contract brewer order date fix | Millicent |
| Apr 7 | #4620 NS auth failures — 401s | Rob |
| Apr 7 | #4621 NS subsidiary mismatch on invoice creation | Rob |
| Apr 7 | #4617 NS subsidiary change blocked during backfill | Rob |
| Apr 7 | #4618 NS invoice backfill 404s | Rob |
| Apr 7 | #4619 fputcsv PHP 8.4 deprecation | Rob |
| Apr 7 | #4615 Batch command to push outage invoices | Rob |
| Apr 7 | #4582 Customer payload in backfill failure CSV | Rob |
| Apr 6 | #4561 Contract brewer transfer fix | Millicent |
| Apr 6 | #4579 Clean up invalid phone numbers | Rob |
| Apr 6 | #4578 Sanitize phone numbers + failure reporting | Rob |
| Apr 5 | #4575 Reconnection audit CSV export for Finance | Rob |
| Apr 4 | #4573 Fix NS observability (Sentry + Loki) | Rob |

**Key observation:** Rob closed 12 of 14 items, and all were reactive NS breach/recovery work. Millicent closed 2 bug fixes. Bea has not yet closed any items (still ramping). No planned Sprint 3 goal tickets (Fuel Levy, review backlog) have been completed yet.

### Current Sprint Milestone — Still Open (26 items)

**Rob (2 items):** FL-5 CRUD API (#4504), FL-6 NS invoice integration (#4505) — both Fuel Levy backend, not yet started.

**Millicent (5 items):** Allow update for scheduled orders (#4586), Twig runtime error (#4567), order item sorting (#4491), Symfony 8.0 upgrade (#4394), mark legacy endpoints deprecated (#4383).

**Bea (12 items):** 4 Fuel Levy frontend tickets (#4506-4509), plus 8 Orders Experience tickets (#4565, #4447, #4441, #4428, #4427, #4415, #4400, #4369).

**Doug (7 items):** Still assigned — see Section 1. All need reassignment.

### Velocity Assessment

Sprint 2 closed 47 items across 2 weeks. Sprint 3 has closed 14 in 3 days, but nearly all were unplanned NS incident work. **Effective progress on Sprint 3 goals is near zero.** The NS breach consumed most of the first week. With 7 working days remaining and a Day 8 scope freeze approaching, the team needs to aggressively prioritise.

---

## 3. Assigned But Not Underway — Sprint Fit Check

### Sprint 1 Leftovers (10 items still open)

These have been sitting since mid-March. Recommendation for each:

| # | Title | Assignee | Recommendation |
|---|-------|----------|---------------|
| 4484 | Remove subsidiary from NS customer payload | Unassigned | Close or merge into NS Audit |
| 4478 | Audit command — KC vs NS billing emails | Rob | Defer — not critical this sprint |
| 4477 | Fix null billing emails overwriting NS | Rob | **Do this sprint** — data integrity |
| 4466 | Fix slow GET /api/assets (Epic) | Rob | Defer — performance, not blocking |
| 4438 | Integrate EmailLogService | Rob | Defer to Sprint 4 |
| 4436 | Upgrade mailchimp/transactional | Rob | **Do this sprint** — PHP 8.4 compat |
| 4309 | Discovery: Define refill order workflow | Rob | **Do this sprint** — quarterly priority |
| 4300 | NS API retry logic | Rob | Defer — nice to have |
| 4153 | Add assets to order | Doug→Bea | Defer — needs lease decoupling first |
| 4152 | Lease Orders | Doug→Bea | Defer — depends on #4526 |

**Action:** Move milestones. Only #4477, #4436, and #4309 should stay in active sprint scope. The rest should be untagged or moved to Sprint 4.

### Millicent's Sprint Items — All Relevant?

Her 5 current sprint items are all valid. Priority order:
1. #4586 Allow update for scheduled orders — **feature work, ship this**
2. #4567 Twig runtime error — **bug fix, ship this**
3. #4491 Order item sorting — **enhancement, ship if time**
4. #4394 Symfony 8.0 upgrade — **chore, defer to Sprint 4** (big risk, no business value this sprint)
5. #4383 Mark legacy endpoints deprecated — **chore, defer**

### Bea's Sprint Items — Realistic?

12 items is too many for someone still onboarding. Recommended focus:
1. **Fuel Levy frontend** (#4506-4509) — blocked on backend FL-2 through FL-4 being done first. Bea can't start these yet.
2. **Quick wins for first PRs:** #4565 (consignment number visibility), #4369 (email status indicator), #4498 (mobile Safari CSS fix — reassigned from Doug)
3. **Defer:** #4441, #4428, #4427, #4415, #4400, #4447 — these are all good work but not sprint-critical

---

## 4. Quarterly Priority Status

### Priority 1: Fuel Surcharge (Epic #4493) — 🔴 Behind

14 total tickets. Current state:

| Ticket | Title | Status | Assignee |
|--------|-------|--------|----------|
| FL-1 #4500 | Discovery: Postcode→State classification | **Unassigned** | — |
| FL-2 #4501 | Migration + FuelSurchargeRate entity | **Unassigned** | — |
| FL-3 #4502 | Rate resolution service | **Unassigned** | — |
| FL-4 #4503 | Order integration — snapshot + line item | **Unassigned** | — |
| FL-5 #4504 | CRUD API endpoints | Open | Rob |
| FL-6 #4505 | NS invoice integration | Open | Rob |
| FL-7 #4506 | Frontend: Order detail display | Open | Bea |
| FL-8 #4507 | Frontend: Admin rate management UI | Open | Bea |
| FL-9 #4508 | Frontend: Customer portal notice | Open | Bea |
| FL-10 #4509 | Frontend: Admin order form display | Open | Bea |
| FL-11 #4510 | Discovery: Invoice data sync NS→KC | **Unassigned** | — |

**Critical blocker:** FL-1 through FL-4 are unassigned and block everything else. FL-5 and FL-6 (Rob's) depend on FL-2 and FL-3 being done. Bea's frontend work (FL-7 through FL-10) depends on the backend being done.

**Recommendation:** Assign FL-1 through FL-3 to Millicent immediately. FL-4 can go to Rob or Millicent. This was flagged in the Sprint 3 planning dashboard but hasn't happened yet — the NS breach consumed the week.

### Priority 2: Orders Experience (Epic #4377) — 🟡 Progressing, Needs Focus

This is now Bea's primary domain. The epic is open and assigned to her. Related sub-epics:
- #4557 Orders Enhancements & Polish — unassigned, backlog
- #4598 Rental Order Form Improvements — unassigned, backlog (new, 11 sub-tickets with `design-feedback` tag)
- #4587 Rentals List Page Improvements — unassigned, backlog (new, 8 sub-tickets)
- #4606 Order Detail & Workflow Improvements — unassigned, backlog (new, 9 sub-tickets)

Doug completed the core Orders table, forms, and workflows. The remaining work is polish, UX improvements, and extending to all order types. **28 tickets tagged `design-feedback`** were created recently — these appear to be from a design review session and are all unassigned with no milestone.

**Recommendation:** These 28 design-feedback tickets should be triaged with the COO/CEO. They're good ideas but adding them all to the sprint would be scope creep. Pick 3–5 high-impact ones for Sprint 4 and leave the rest in backlog.

### Priority 3: Refill Orders in Cloud (Epic #4308) — 🔴 Not Started

6 sub-tickets under NS Epic 1:

| Ticket | Title | Assignee |
|--------|-------|----------|
| NS-1.1 #4309 | Discovery: Define refill workflow | Rob |
| NS-1.2 #4310 | Un-deprecate REFILL line item | Millicent |
| NS-1.3 #4311 | Backend: Refill order creation | Rob |
| NS-1.4 #4312 | Backend: Refill invoicing via NS | Millicent |
| NS-1.5 #4313 | Frontend: Refill order creation UI | Bea |
| NS-1.6 #4314 | Ensure refill volume in contract tracking | Rob |

**Depends on:** NS Epic 0 Foundation (#4296), which is still open and assigned to Rob. This is the critical path for all NetSuite work.

**Recommendation:** NS-1.1 Discovery (#4309) is sitting in Sprint 1 milestone. Rob should complete this discovery before the end of Sprint 3 to unblock Millicent on NS-1.2 and NS-1.3. Full implementation likely Sprint 4–5.

---

## 5. Additional Points for Monday's Meeting

### The NS Breach Impact

Between Apr 4–10, Rob closed 12 tickets — all reactive incident work. This effectively wiped out Week 1 of Sprint 3. The NS Security Audit epic (#4532) has **13 sub-tasks still open**, 7 assigned to Rob and 4 unassigned. This work is compliance-driven and ongoing.

**Discussion point:** Should NS Audit remediation be timeboxed (e.g., 2 days/sprint) or does leadership want it completed as a block? The current trajectory has it competing with Fuel Levy and Refill work for Rob's time.

### Team Load Distribution

| Person | Open Issues | Sprint Items | Observation |
|--------|------------|-------------|-------------|
| Rob | 53 | 9 (2 sprint + 7 from Sprint 1) | Massively overloaded. 44 items with no milestone. |
| Bea | 33 | 12 | High for someone onboarding. Many are blocked on backend. |
| Millicent | 30 | 5 | Reasonable load, but FL tickets need assigning to her. |
| Doug | 10 | 7 in sprint | All need reassignment before he leaves. |
| Unassigned | 49 | — | Includes FL-1 to FL-4 (blockers) and 28 design-feedback items. |

### Backlog Grouping Opportunities

The 48 unassigned/no-milestone items cluster into clear groups:

1. **Design Feedback (28 items)** — Three natural epics already exist: Rentals List (#4587), Rental Form (#4598), Order Detail (#4606). These are triageable as a batch.
2. **NS Audit (4 unassigned items)** — #4536-4539. These are the "do the rotation" tasks. Could be a focused half-day for Rob + Millicent.
3. **Fuel Levy Backend (4 unassigned)** — FL-1 to FL-4. Assign to Millicent.
4. **Legacy Cleanup** — #3928 (consolidate default tenant), #4254 (remove SSID Bank), #4253 (remove Sigfox refs). Group as a "tech debt sprint day."
5. **Performance** — #4250 (global search 11s), #4457 (assets query). Could be a paired effort.

### Items to Move to Ready

These are well-defined, unblocked, and should be promoted from backlog to Ready:

- **#4477** Fix null billing emails — data integrity fix, ready to go
- **#4436** Upgrade mailchimp/transactional — PHP 8.4 compat, clear scope
- **#4636** Remove rolled-out feature flags — reassign to Bea, good starter
- **#4498** Fix mobile Safari button text — reassign to Bea, quick CSS
- **#4303** Fix posting period to use completed date — assigned to Millicent, 1 SP, high priority per CLAUDE.md

### Doug Handover Checklist for Monday

- [ ] Confirm all 10 open tickets are documented well enough for Bea to pick up
- [ ] Specifically discuss #4526 (lease decoupling) — this is architecturally complex
- [ ] Confirm Rainforest QA test access/credentials are documented
- [ ] Confirm handover recordings are in SharePoint → Development → Recordings
- [ ] Any undocumented tribal knowledge about the Orders frontend state management?

---

## 6. Recommended Actions Coming Out of Monday

1. **Reassign Doug's 10 tickets** — 7 to Bea, 3 QA tickets grouped together
2. **Assign FL-1 through FL-4 to Millicent** — unblock the entire Fuel Levy chain
3. **Timebox NS Audit** — agree with leadership on a budget (e.g., 3 SP/sprint)
4. **Clean Sprint 1 milestone** — move or close the 10 stale items
5. **Triage design-feedback batch** — pick 3–5 for Sprint 4, backlog the rest
6. **Rob scope reduction** — 53 open items is not sustainable. Identify 10+ to defer or delegate
7. **Sprint 3 revised goals** — given Week 1 was lost, realistic goals for remaining 7 days:
   - Rob: Complete FL-5, FL-6, #4477, #4436, NS-1.1 discovery
   - Millicent: Start FL-1/FL-2, ship #4586, fix #4567
   - Bea: First PR merged (#4636 or #4498), start #4565 and #4369
