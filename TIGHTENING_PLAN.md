# ECIO Policy Manual — Tightening Execution Plan

**Created:** April 11, 2026
**Owner:** Robert Pratt (IT Director)
**Status:** Living document until manual reaches v1.0; retires with the repo
**Scope:** Sequencing and defect tracking for the ECIO Policy Manual tightening pass

This plan is operational scaffolding for the tightening project. It is not a permanent artifact. Once the manual reaches v1.0, this file and the GitHub repo it lives in are retired; ongoing maintenance moves to the LyX revision history and the System of Engagement under the policy maturation cycle.

---

## §1. How to Use This Plan

At the start of every tightening session, fetch this file and check three things in order:

1. **Architectural Roots** (§3) — has anything changed that affects what's safe to execute?
2. **Standing Decline Patterns** (§4) — what cross-validator feedback should be reflexively declined?
3. **Per-Policy Defect Inventory** (§5) — what's the current ticket list against the target policy?

The Recommended Sequence (§6) is advisory. Robert makes final sequencing calls per session.

**Recalculation markers.** This plan contains ◆ RECALCULATE SEQUENCE HERE ◆ markers in §6. They are hard checkpoints, not advisory. When a recalc marker is reached, the next session shall begin by re-running the architectural roots check, refreshing per-policy ticket counts against the current GitHub state, and re-evaluating the remaining sequence before starting any new tightening work. Skipping the recalc is a process violation.

**Session-close checklist.** Claude shall run through these items in order. Claude does not declare the session complete — Robert does. After completing the checklist, Claude asks: "Anything else, or are we done?"

1. **File all ripple issues immediately** — never defer a ripple as a session note.
2. **Close resolved issues** — comment with resolution details, then close. Update parent sweep tickets (#208, #8, etc.) with per-policy resolution notes.
3. **Update and push this plan** — update §5 (target policy state, version, open ticket count) and §6 (mark the completed entry). If new ripples were filed against other policies, update their §5 rows. Push to repo.
4. **Ask Robert if we're done** — do not declare session complete unilaterally. IF confirmed done, then we continue on the checklist.
5. **Commit tightened LyX via API** — push the final LyX file to the repo and update the README.md to match. Confirm the version number in the metadata line matches what §5 will record. Robert syncs local repo afterward.
6. **Verify synchronization** — the plan, the issue tracker, the repo LyX files, and the README.md shall agree.
7. **Next session notice** — remind Robert of the next policy to tackle.

---

## §2. Ticket Lifecycle Rules

**Closed tickets stay closed.** Reopening conflates two events into one ticket history. Always file a new ticket for any new work, even if it touches the same lines as a previously-closed ticket.

**Ripples → new ticket.** When tightening Policy A reveals a defect in already-tightened Policy B, file a new ticket against B. Cross-reference the originating session in the body.

**Wrong fixes → new ticket with `regression` label.** When a previous fix turns out to have been incorrect (not outdated, but wrong as applied), file a new ticket tagged `regression` and reference the prior ticket in the body.

**Architecturally invalidated tickets → close with `superseded` label.** When a downstream architectural decision makes a previously-filed ticket obsolete, close it with the `superseded` label and a comment pointing at the decision that invalidated it.

---

## §3. Architectural Roots

These are tickets that establish manual-wide patterns or designate constructs other policies inherit from. Resolving them in the wrong order forces double-rewrites of downstream policies.

### Active Roots

| # | Title | Target | Status | Downstream |
|---|---|---|---|---|
| #208 | Standardize "All IT Personnel" → "All Information Operations Personnel" | Manual-wide | Open, sweep | All policies with §3 group identifiers |
| #211 | Verify "Supervisors" matches 1.07 §3 "Supervisors and Leads" | Manual-wide | Open, sweep | Any policy referencing Supervisors |
| #235 | Prohibited language sweep per 1.04 §6.9 | Untightened policies | Open, absorbed-by-tightening | Listed in #235 body; resolved per-policy |
| #245 | Replace `business hours` time-unit with end-of-business-day convention | Manual-wide | Open, sweep | Per #245 body |
| #264 | Role obligation redistribution (L3 prep, L1 clerical, L2 inputs, AID synthesis) | Manual-wide | Open, root | Remaining subtasks absorb into tightening |
| #291 | Remove hard-coded FIPS 140-2/140-3 transition dates — CMVP by-reference | 1.11, 2.05, 2.07 | Open, sweep | #292 (2.05), #293 (2.07); 1.11 resolved in v2.2 |
| #6, #7, #8, #10 | Product-name removal (Redmine, Office 365, Comodo/XCitium, HID DigitalPersona) | Manual-wide | Open, absorbed-by-tightening | Resolved per-policy |

### Closed Roots

| # | Title | Resolved | Notes |
|---|---|---|---|
| #220 | LASO Designation Disentanglement | v2.2, April 11 | Landed in 1.11 §6.11. IT Director holds LASO by policy mandate. Downstream cleanup batch (4.06 v2.2, 1.14 v2.3) complete. Untightened LASO queue (2.01/2.02/2.04/2.06/2.11/2.12/2.13) absorbs into normal tightening using "IT Director (as LASO)" pattern. |
| #283 | LASO is a designation, not a §3 role | April 11 | Superseded by #220 landing. |
| #304 | Chapter 4 external self-containment quality gate | April 12 | All Ch4 policies tightened (4.01–4.07). |

**Sweep-style roots (#208, #211, #235, #245, #6/#7/#8/#10)** are applied as a quality gate during each policy's tightening session, not as standalone sweep sessions. Roots stay open until every policy has been touched.

### Deferred Cluster: `1.04_Procedural_Cleanup`

A constitutional revision of 1.04 mid-project would invalidate prior tightening work. This cluster collects 1.04 tickets that touch §6.15 (SOPs) and §6.16 (Playbooks) — procedural sections that don't affect policy formatting rules.

**Cluster source-of-truth rule:** Chapter 4 is the source of truth for playbook structure; the cluster transcribes Chapter 4's de facto patterns into 1.04 §6.16, not the other way around.

**Cluster members:** #31 (LyX environment names for §6.15/§6.16). Previously closed: #5, #30, #32, #290.

**Status:** Per Robert's April 11, 2026 ruling, this cluster is **not** a hard blocker on v1.0.

---

## §4. Standing Decline Patterns

Cross-validator feedback matching these patterns is reflexively declined.

1. **Merge §5 into a flat list** — violates 1.04 §6.7 Cited/Framework split.
2. **Reorder NIST SP before CSF in citations** — violates 1.04 §6.11; citation order ≠ authority order.
3. **LyX CommandInset false positives** — validators sometimes flag valid LyX cross-references as broken.
4. **ChatGPT hallucinated policies** (4.09, 4.10) — do not exist.
5. **ChatGPT: restore dual-maintenance trigger thresholds in 3.07** — dual-maintenance risk.
6. **ChatGPT: reinstate 1.08 in exception path** — locked architecture; exception routing is 5.01 §6.6.
7. **Stale section references to pre-tightening versions** — validators lack access to tightened source.
8. **§6.8 topic-block "violation"** — §6.8 applies at the atomic bullet level, not the topic-block level. A bold-label topic block (per §6.12) may contain multiple atomic bullets, each independently satisfying §6.8.
9. **CSF subcategory citation hallucinations** — verify against CSF 2.0 Appendix A before accepting (e.g., PR.AT-03 does not exist; ID.IM-04 was misdescribed).
10. **Restore TAC as a §3 role in 1.11** — TACs are department-level CJIS designees at consuming agencies, not IO personnel. ECIO has no authority to impose obligations on them.
11. **ChatGPT: restore product names (e.g., Redmine) for cross-policy consistency** — 1.04 §6.10 prohibits product names; untightened policies will be cleaned during their sessions.
12. **Accept dash Out of Scope convention as Ch4 standing pattern** — 1.04 §6.4 prescribes colon format. The dash pattern was a regression corrected in 4.04 v2.2.
13. **ChatGPT: narrow 3.12 IC designation to pre-work-order scope or delete communications spokesperson** — IC is incorporated by reference from 3.06, not independent authority. Proposed narrowing is architecturally incoherent (IC commands response, not monitoring; "up to work order creation" would give IC zero authority since incidents require work orders). "Operational" qualifier + §6.3 Security Handoff + §2 Out of Scope already draw the jurisdictional boundary.

---

## §5. Per-Policy Defect Inventory

State key: **L** = Locked, **T** = Tightened (clean), **T+** = Tightened with open ripples, **D** = Drafted/untightened, **A** = Appendix.

### Chapter 0 / Front Matter

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 000 | Front Matter | T | v3 | 0 | — |

### Chapter 1 — Governance

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 1.02 | Code of Ethics | T | — | 0 | — |
| 1.03 | Standard Operating Ethos | T | v2.0 | 0 | — |
| 1.04 | Formatting Standards | L | — | 1 | #31 (deferred to cluster) |
| 1.05 | Policy Review and Update Procedures | T | v2.2 | 0 | — |
| 1.06 | IT Governance and Oversight Structure | T | v2.1 | 0 | — |
| 1.07 | Workforce Roles | T | v1.3 | 0 | — |
| 1.08 | Delegation of Authority | T | v1.4 | 0 | — |
| 1.09 | Risk Management | T | v2.1 | 0 | — |
| 1.10 | IT Financial / Procurement | D | — | 4 | #50, #51, #299, +1 |
| 1.11 | Data Governance and Classification | T | v2.2 | 0 | — |
| 1.12 | IT Asset Management | D | — | 6 | #53, #54, #55, #256, #301, +1 |
| 1.13 | Supply Chain Risk Management | D | — | 2 | #56, +1 |
| 1.14 | Stakeholder Engagement | T | v2.3 | 0 | — |

### Chapter 2 — Security

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 2.01 | Acceptable Use | D | — | 4 | #61, #62, #63, +1 |
| 2.02 | Personnel Security | D | — | 2 | #64, +1 |
| 2.03 | Security Awareness | D | — | 4 | #66, #67, #68, +1 |
| 2.04 | Access Control | D | — | 2 | #69, #70 |
| 2.05 | Identification and Authentication | D | — | 4 | #71, #72, #73, #292 |
| 2.06 | Privacy and Data Protection | D | — | 5 | #74, #75, #76, #77, +1 |
| 2.07 | System and Communications Protection | D | — | 4 | #78, #79, #80, #293 |
| 2.08 | System Integrity / Malware | D | — | 3 | #81, #83, #84 |
| 2.09 | Vulnerability and Patch Management | D | — | 4 | #85, #86, #87, +1 |
| 2.10 | Secure Configuration Baselines | D | — | 4 | #88, #89, #90, +1 |
| 2.11 | Audit Logging and Monitoring | D | — | 2 | #91, #92 |
| 2.12 | Media Protection and Sanitization | D | — | 3 | #94, #95, +1 |
| 2.13 | Physical Security | D | — | 3 | #96, #97, #98 |
| 2.14 | Mobile and Remote Access | D | — | 4 | #99, #101, #102, +1 |
| 2.15 | Secure Software Lifecycle | D | — | 3 | #103, #104, #105 |

### Chapter 3 — Service Management

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 3.01 | Service Catalog and SLA | T | v2.3 | 0 | — |
| 3.02 | Service Level Management | T+ | v2.5 | 1 | #309 |
| 3.03 | Service Communication | T | v2.0 | 0 | — |
| 3.04 | Service Delivery Feedback | T | v2.1 | 0 | — |
| 3.05 | Service Request Fulfillment | T | v2.1 | 1 | #308 |
| 3.06 | Operational Incident Management | T+ | v2.1 | 1 | #313 |
| 3.07 | Problem Management | T+ | v2.2 | 1 | #316 |
| 3.08 | CMDB | T | v2.1 | 0 | — |
| 3.09 | Change Management | T | v2.0 | 0 | — |
| 3.10 | Release and Deployment | T | v2.0 | 0 | — |
| 3.11 | Capacity and Availability | T+ | v2.0 | 1 | #317 |
| 3.12 | Monitoring and Event Management | T+ | v2.0 | 1 | #318 |
| 3.13 | Knowledge Management | T | v2.1 | 0 | — |
| 3.14 | IT Project Management | T | v2.1 | 0 | — |
| 3.15 | Service Continuity | T+ | v2.1 | 2 | #314, #319 |
| 3.16 | Service Improvement | T | v2.0 | 0 | — |
| 3.17 | System Maintenance and Vendor Repairs | D | — | 2 | +2 |

### Chapter 4 — Incident Response

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 4.01 | IR Policy Overview | T | v2.0 | 0 | — |
| 4.02 | Identification and Reporting | T | v2.1 | 0 | — |
| 4.03 | Containment Strategy and Playbooks | T | v2.0 | 0 | — |
| 4.04 | Eradication | T | v2.2 | 0 | — |
| 4.05 | Recovery and Restoration | T | v2.1 | 0 | — |
| 4.06 | Communication Protocols | T | v2.2 | 0 | — |
| 4.07 | Postmortem and Lessons Learned | T | v1.0 | 0 | — |

### Chapter 5 — Compliance

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 5.01 | Implementation, Enforcement, Legal | T | v1.0 | 0 | — |
| 5.02 | Internal Audits | D | — | 5 | +5 |
| 5.03 | Compliance Monitoring | D | — | 2 | +2 |
| 5.04 | Performance Metrics | D | — | 1 | +1 |
| 5.05 | Security Control Assessment | D | — | 1 | +1 |
| 5.06 | Vendor Compliance | D | — | 1 | +1 |
| 5.07 | Annual Policy Review | D | — | 3 | #300, +2 |

### Chapter 6 — Appendices

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 6.01 | Glossary | A | draft | 3 | #192, #193, #195 |
| 6.02 | Policy Matrix | A | — | 3 | +3 |
| 6.03 | Workforce Roles STAK Matrix | A | — | 3 | +3 |
| 6.04 | Revision History and Version Control | A | — | 1 | #205 |

---

## §6. Recommended Sequence

Sequencing principles, in priority order:

1. Clear architectural roots before downstream cleanup
2. High-impact-first (closes the most architectural risk per session)
3. Pair Chapter 3 feeders with their Chapter 4 collectors in adjacent sessions
4. Recalc markers — sequence past them is provisional and gets rebuilt at each marker

---

### Phase 1 — Root Resolution ✅

**Goal:** Land the LASO designation in 1.11 and clean up immediate downstream ripples.

1. ~~1.11 (Data Governance and Classification)~~ — ✅ v2.2, April 11, 2026.
2. ~~LASO downstream cleanup batch (4.06 v2.2, 1.14 v2.3, #283 closed)~~ — ✅ April 11, 2026.

---

### Phase 2 — Foundational Governance ✅

**Goal:** Close the highest-defect Chapter 1 untightened policies.

3. ~~1.09 (Risk Management)~~ — ✅ v2.1, April 11, 2026.
4. ~~1.05 (Policy Review and Update Procedures)~~ — ✅ v2.2, April 12, 2026.
5. ~~1.06 (IT Governance and Oversight Structure)~~ — ✅ v2.1, April 12, 2026.

---

### Phase 3 — 3→4 Feeder/Collector Pairs ✅

**Goal:** Tighten Chapter 3 feeders and their Chapter 4 collectors in adjacent sessions.

6. ~~3.08 (CMDB)~~ — ✅ v2.1, April 12, 2026.
7. ~~4.04 (Eradication)~~ — ✅ v2.2, April 12, 2026.
8. ~~3.09 (Change Management)~~ — ✅ v2.0, April 12, 2026.
9. ~~4.05 (Recovery)~~ — ✅ v2.1, April 12, 2026.
10. ~~3.13 (Knowledge Management)~~ — ✅ v2.1, April 12, 2026.
11. ~~4.03 (Containment)~~ — ✅ v2.0, April 12, 2026.
12. ~~4.02 (Identification and Reporting)~~ — ✅ v2.1, April 12, 2026.
13. ~~4.07 (Postmortem)~~ — ✅ v1.0, April 13, 2026.

---

### Phase 4 — Remaining Chapter 3

**Goal:** Close out the service management chapter. No tight Chapter 4 dependencies remaining after Phase 3.

14. ~~3.10 (Release and Deployment)~~ — ✅ v2.0, April 13, 2026.
15. ~~3.11 (Capacity and Availability)~~ — ✅ v2.0, April 13, 2026. Ripples: #309 (3.02 data intake), #310 (3.12 threshold receipt).
16. ~~3.12 (Monitoring and Event Management)~~ — ✅ v2.0, April 13, 2026. Ripple: #311 (1.11 LRDA title correction).
17. ~~3.14 (IT Project Management)~~ — ✅ v2.1, April 13, 2026. Ripple: #312 (4.07 reciprocal Out of Scope pointer).
18. ~~3.15 (Service Continuity)~~ — ✅ v2.1, April 14, 2026. Ripples: #313 (3.06 bidirectional reference), #314 (LRDA series mapping).
19. ~~3.16 (Service Improvement)~~ — ✅ v2.0, April 14, 2026. Ripples: #316 (3.07 bidirectional SIR routing), #317 (3.11 remediation plan SIR routing), #318 (3.12 threshold breach SIR routing), #319 (3.15 tabletop findings SIR routing).
20. **3.17 (System Maintenance and Vendor Repairs)** — 2 tickets

> ## ◆ RECALCULATE SEQUENCE HERE ◆
>
> **Stop. Before starting Phase 5:**
>
> - Re-run the architectural roots check
> - Refresh per-policy ticket counts — Phase 5+ orderings below are provisional and likely partially stale
> - Re-evaluate Chapter 2 LASO downstream queue ordering against any ripples from Phases 2–4
> - Check whether 5.07 should pull forward based on 1.09 ripples
> - Decide whether `1.04_Procedural_Cleanup` should sequence before or after Chapter 6 appendices
>
> The remaining phases are **provisional**. Treat them as a starting point for re-planning, not a fixed schedule.

---

### Phase 5 — Chapter 2 Security (provisional)

**LASO downstream cleanup priority** (consume LASO ripples first while pattern is fresh):

- 2.01 → 2.06 → 2.02 → 2.04 → 2.11 → 2.12 → 2.13

**Remaining Chapter 2:**

- 2.03 → 2.05 → 2.07 → 2.08 → 2.09 → 2.10 → 2.14 → 2.15

Note: 2.10 has the Shadow IT routing fix (split between IoC routing through 4.02 and config-mgmt remediation through 3.09/2.10). Apply during 2.10's session.

---

### Phase 6 — Chapter 5 Compliance (provisional)

5.02 → 5.03 → 5.04 → 5.05 → 5.06 → 5.07. 5.07 last because it consumes outputs from the other Chapter 5 policies.

---

### Phase 7 — Chapter 6 Appendices (provisional)

6.01 (Glossary — draft delivered April 12, 2026; final tightening after all policies finalized) → 6.02 → 6.03 → 6.04.

---

### Phase 8 — `1.04_Procedural_Cleanup` Cluster

Final pre-v1.0 work. Remaining member: #31 (LyX environment names for §6.15/§6.16). Transcribes Chapter 4's de facto playbook patterns into 1.04 §6.16.

Per Robert's April 11, 2026 ruling: this cluster is **not** a hard blocker on v1.0 readiness.

---

### Phase 9 — v1.0 Declaration and Repo Retirement

Final validation pass, README status update, manual declared at v1.0, repo archived. Ongoing maintenance moves to LyX revision history and System of Engagement.

---

## §7. Open Questions / Pending Decisions

- **#264 partial completion tracking** — confirm which subtasks are actually closed in the repo vs. carried in memory only. May need a sweep to align.
- **#208/#211 sweep enforcement** — currently absorbed into per-policy tightening; consider whether a single dedicated sweep session would be faster.

---

## §8. v1.0 Declaration Criteria

The manual reaches v1.0 when it satisfies all three of the following criteria. These are gate conditions, not aspirational targets.

**Criterion 1 — Internal Consistency.** The manual is internally consistent in both formatting and content. Every policy conforms to 1.04 structural and stylistic standards. Cross-references resolve. Terminology is uniform. No policy contradicts another.

**Criterion 2 — Self-Feeding and Self-Growing.** The manual is a self-sustaining governance system with no isolated parts. Every policy's outputs feed at least one other policy's inputs. Every pipeline is bidirectional where the relationship warrants it. The appendices are both part of and separate from the manual — they support the system but are not dead-end artifacts.

**Criterion 3 — Succession Completeness.** The manual is complete enough that if the entire department were eliminated — no people, no tools, no procedures — a competent reader with no institutional knowledge could pick it up and rebuild the department. The manual cannot and should not contain step-by-step operational procedures (those belong in the System of Engagement under 1.04 §6.15/§6.16), but it must contain enough specificity that procedures can be *derived* from the policy directives.

**Phase 9 Validation Test:** For any directive in any policy, a reader with no institutional knowledge shall be able to determine:

1. What needs to happen.
2. Who is accountable.
3. What triggers it.
4. What it produces.
5. Where that output goes next.

If any of the five are missing for any directive, that is a v1.0 gap.

**Residual work tolerance:** The `1.04_Procedural_Cleanup` cluster (§6 Phase 8) is not a hard blocker per the IT Director's April 11, 2026 ruling. Other residual items of comparable scope may be deferred to post-v1.0 maintenance at the IT Director's discretion, provided they do not violate Criteria 1–3.
