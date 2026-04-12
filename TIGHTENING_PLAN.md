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

**Recalculation markers.** This plan contains two ◆ RECALCULATE SEQUENCE HERE ◆ markers in §6. They are hard checkpoints, not advisory. When a recalc marker is reached, the next session shall begin by re-running the architectural roots check, refreshing per-policy ticket counts against the current GitHub state, and re-evaluating the remaining sequence before starting any new tightening work. Skipping the recalc is a process violation. The markers exist because the working set will have shifted enough by those points that any sequence drafted today will be partially stale by then.

---

## §2. Ticket Lifecycle Rules

**Closed tickets stay closed.** Reopening conflates two events into one ticket history. Always file a new ticket for any new work, even if it touches the same lines as a previously-closed ticket.

**Ripples → new ticket.** When tightening Policy A reveals a defect in already-tightened Policy B, file a new ticket against B. Cross-reference the originating session in the body.

**Wrong fixes → new ticket with `regression` label.** When a previous fix turns out to have been incorrect (not outdated, but wrong as applied), file a new ticket tagged `regression` and reference the prior ticket in the body. The label is the tracking signal — if the regression rate climbs, the protocol needs adjustment.

**Architecturally invalidated tickets → close with `superseded` label.** When a downstream architectural decision (e.g., #220 LASO disentanglement) makes a previously-filed ticket obsolete, close the obsolete ticket with the `superseded` label and a comment pointing at the architectural decision that invalidated it.

---

## §3. Architectural Roots

These are tickets that establish manual-wide patterns or designate constructs other policies inherit from. Resolving them in the wrong order forces double-rewrites of downstream policies.

### Active Roots

| # | Title | Target | Status | Downstream |
|---|---|---|---|---|
| #220 | LASO Designation Disentanglement | 1.11 | **Closed** (v2.1) | 4.06, 1.14, 2.01, 2.02, 2.04, 2.06, 2.11, 2.12, 2.13 |
| #208 | Standardize "All IT Personnel" → "All Information Operations Personnel" | Manual-wide | Open, sweep | All policies with §3 group identifiers |
| #211 | Verify "Supervisors" matches 1.07 §3 "Supervisors and Leads" | Manual-wide | Open, sweep | Any policy referencing Supervisors |
| #235 | Prohibited language sweep per 1.04 §6.9 | 20 untightened policies | Open, absorbed-by-tightening | Listed in #235 body; resolved per-policy |
| #245 | Replace `business hours` time-unit with end-of-business-day convention | Manual-wide | Open, sweep | Per #245 body |
| #264 | Role obligation redistribution (L3 prep, L1 clerical, L2 inputs, AID synthesis) | Manual-wide | Open, root | 4.02, 4.06, 5.01, plus untightened |
| #283 | LASO is a designation, not a §3 role | Manual-wide | **Conflicts with #220** — auto-close as `superseded` when #220 lands | Same as #220 downstream |
| #6, #7, #8, #10 | Product-name removal (Redmine, Office 365, Comodo/XCitium, HID DigitalPersona) | Manual-wide | Open, absorbed-by-tightening | Resolved per-policy |
| #291 | Remove hard-coded FIPS 140-2/140-3 transition dates — CMVP by-reference | 1.11, 2.05, 2.07 | Open, sweep | #292 (2.05), #293 (2.07); 1.11 resolved in v2.1 |

### #220 — LASO Designation Disentanglement (detailed entry)

**Home determination:** 1.11 §3 is the correct designation point. #220's exclusion analysis ruled out:

- **1.07** — locked at v1.3, and CJIS-driven compliance liaison roles were deliberately excluded from workforce competency scope
- **1.14** — references LASO as a CJI comms routing participant but is a *consumer*, not a designator
- **A dedicated Chapter 2 CJIS policy** — Chapter 2 is organized by NIST 800-53 control family; creating a CJIS program ownership policy would violate the locked chapter structure

**Why 1.11:** The LASO's core duty is CJI oversight. 1.11 is the CJI-touching policy. The designation belongs where the duty lives.

**Required §3 structure in 1.11:** Split LASO out of any existing IT Director bullet. List LASO as its own distinct §3 role. State that the designation is held by default by the IT Director and may be reassigned in writing to another qualified individual meeting CJIS v6.0 LASO qualifications. Define appointment authority, qualifications, and reporting line to CSA/CSO.

**Operational reality of the designation (per Robert, April 11, 2026):** The LASO is not a lightweight internal appointment. The designee is formally registered with the Nevada Department of Public Safety (DPS), which serves as the state-level CJIS Systems Agency intermediary between local agencies and the FBI. The registration chain is **County LASO → Nevada DPS → FBI**. This creates three drafting requirements that 1.11 §3 must address:

- **Designation transfer is heavyweight, not lightweight.** A reassignment requires formal state re-registration with DPS, not just an internal memo. The §3 language must reflect that the designation is held until formally transferred, not rotated for vacation coverage or short-term absence.
- **Distinguish execution delegation from designation transfer.** The LASO authorizing a designee to execute a specific notification under Policy 1.08 (the existing pattern in 4.06 §6.4) is *execution delegation* — lightweight, internal, does not transfer accountability. A change in who *holds* the LASO designation is *designation transfer* — heavyweight, requires DPS re-registration. These are different mechanisms and 1.11 §3 must not conflate them.
- **Gap-state interim posture.** When a LASO designee becomes unavailable suddenly (medical emergency, separation, etc.), there is a registration delay before a successor is fully recognized by DPS. 1.11 §3 must define who holds the LASO obligations during the gap — the previous designee remains accountable until formally relieved, or the IT Director assumes interim execution authority pending DPS registration of the successor.

**Why this satisfies 1.04 §6.5:** Once 1.11 designates LASO with a defined membership boundary (the individual currently holding the written designation), LASO becomes "a defined group with a clear membership boundary" per the §6.5 Role Identity Requirement. Until then, downstream LASO §3 blocks (e.g., 4.06 v2.1) are forward-references to a designation whose home is pending — acceptable as an interim state.

**Coordinated downstream cleanup batch (executes immediately after 1.11 lands):**

- **4.06 v2.2** — single combined cut absorbing both the LASO §3 fix AND the #268 Administrative Assistant directory reassignment. Single rewrite, both fixes adjacent.
- **1.14 v2.3** — LASO §3 cleanup
- **#283 closes automatically as `superseded`** when the cleanup batch lands

**Untightened LASO downstream queue (absorbed into normal tightening sessions, not part of the cleanup batch):** 2.01, 2.02, 2.04, 2.06, 2.11, 2.12, 2.13. Each receives the LASO Pattern 2 fix (the "IT Director (LASO)" combined-header pattern) when its tightening session runs.

### Other Root Sequencing Notes

**#264 (role redistribution root) is partially executed.** Subtasks against 3.01 and 3.02 are done. Remaining subtasks (4.02, 4.06, 5.01, plus untightened) absorb into normal tightening. Root closes when last subtask lands.

**#208, #211, #245 are sweep-style roots** — applied as a quality gate during each policy's tightening session, not as standalone sweep sessions. Roots stay open until every policy has been touched.

**#235 is per-policy absorption.** Each instance closes with the corresponding tightening session.

**#6/#7/#8/#10 product-name removal** — same model as #235.

### Deferred Cluster: `1.04_Procedural_Cleanup`

A constitutional revision of 1.04 mid-project would invalidate prior tightening work. The cluster collects 1.04 tickets that touch §6.15 (SOPs) and §6.16 (Playbooks) — procedural sections that don't affect policy formatting — plus the §6.8 atomic-level clarification (#290).

**Cluster source-of-truth rule:** Chapter 4 is the source of truth for playbook structure; the cluster transcribes Chapter 4's de facto patterns into 1.04 §6.16, not the other way around. Conflicts resolve in Chapter 4's favor.

**Cluster members:** #5, #30, #31, #32, #290.

**Cluster status:** Per Robert's April 11, 2026 ruling, this cluster is **not** a hard blocker on v1.0. Sequence by impact, not by dependency clearing. Chapter 4 does not need to be prioritized to "unblock" this cluster.

**Distinction from constitutional changes:** Changes to 1.04 §6.1–§6.14 are constitutional (require unlocking 1.04, ripple to all tightened policies). Changes to §6.15–§6.16 are procedural (safe to defer to cluster). #290 is an exception — it touches §6.8 but is purely additive text clarification with no rule change, so it's safe in the procedural cluster.

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
8. **§6.8 topic-block "violation"** — §6.8 applies at the **atomic bullet level**, not at the topic-block level. A bold-label topic block (per §6.12) may contain multiple atomic bullets, each independently satisfying §6.8. Only blended bullets (multiple obligations welded with conjunctions inside one atomic item) are prohibited. Filed as #288 (Gemini 3.02 v2.4 round 2, findings G3/G4/G5), closed; clarification queued as #290.
9. **CSF subcategory citation hallucinations** — verify against CSF 2.0 Appendix A before accepting (e.g., PR.AT-03 does not exist; ID.IM-04 was misdescribed).
10. **Restore TAC as a §3 role in 1.11** — TACs are department-level CJIS designees at consuming agencies (Justice Court, Sheriff's Office, District Court), not IO personnel. ECIO has no authority to impose obligations on them. Declined twice across two validator rounds (April 11, 2026). IT Director confirmed operational reality.

---

## §5. Per-Policy Defect Inventory

State key: **L** = Locked, **T** = Tightened (clean), **T+** = Tightened with open ripples, **D** = Drafted/untightened, **A** = Appendix.

### Chapter 0 / Front Matter

| # | Title | State | Ver | Open | Tickets | Notes |
|---|---|---|---|---|---|---|
| 000 | Front Matter | T | v3 | 0 | — | |

### Chapter 1 — Governance

| # | Title | State | Ver | Open | Tickets | Notes |
|---|---|---|---|---|---|---|
| 1.02 | Code of Ethics | T | — | 0 | — | |
| 1.03 | Standard Operating Ethos | T | v2.0 | 0 | — | |
| 1.04 | Formatting Standards | L | — | 5 | #5, #30, #31, #32, #290 | All deferred to `1.04_Procedural_Cleanup` cluster |
| 1.05 | Policy Review and Update Procedures | D | — | 3 | #33, #34, +1 | Defines Technical Directives construct |
| 1.06 | IT Governance and Oversight Structure | D | — | 5 | #35, #36, +3 | |
| 1.07 | Workforce Roles | T | v1.3 | 0 | — | Locked-adjacent; #220 explicitly excludes LASO from 1.07 |
| 1.08 | Delegation of Authority | T | v1.3 | 0 | — | |
| 1.09 | Risk Management | D | — | 5 | #45, #46, #47, #48, +1 | #46 has broken §4 reference |
| 1.10 | IT Financial / Procurement | D | — | 3 | #50, #51, +1 | |
| 1.11 | Data Governance and Classification | T | v2.1 | 0 | — | #220 root landed; LASO designation homed |
| 1.12 | IT Asset Management | D | — | 5 | #53, #54, #55, #256, +1 | |
| 1.13 | Supply Chain Risk Management | D | — | 2 | #56, +1 | |
| 1.14 | Stakeholder Engagement | T+ | v2.2 | 1 | LASO ripple | Phase 1 LASO cleanup batch target |

### Chapter 2 — Security

| # | Title | State | Ver | Open | Tickets | Notes |
|---|---|---|---|---|---|---|
| 2.01 | Acceptable Use | D | — | 4 | #61, #62, #63, +1 | LASO Pattern 2 fix during tightening |
| 2.02 | Personnel Security | D | — | 2 | #64, +1 | LASO downstream |
| 2.03 | Security Awareness | D | — | 4 | #66, #67, #68, +1 | |
| 2.04 | Access Control | D | — | 2 | #69, #70 | LASO downstream |
| 2.05 | Identification and Authentication | D | — | 4 | #71, #72, #73, #292 | |
| 2.06 | Privacy and Data Protection | D | — | 5 | #74, #75, #76, #77, +1 | LASO Pattern 2; #74 has DA approval logic issue |
| 2.07 | System and Communications Protection | D | — | 4 | #78, #79, #80, #293 | |
| 2.08 | System Integrity / Malware | D | — | 3 | #81, #83, #84 | |
| 2.09 | Vulnerability and Patch Management | D | — | 4 | #85, #86, #87, +1 | |
| 2.10 | Secure Configuration Baselines | D | — | 4 | #88, #89, #90, +1 | Shadow IT routing fix needed |
| 2.11 | Audit Logging and Monitoring | D | — | 2 | #91, #92 | LASO downstream |
| 2.12 | Media Protection and Sanitization | D | — | 3 | #94, #95, +1 | LASO downstream |
| 2.13 | Physical Security | D | — | 3 | #96, #97, #98 | LASO downstream |
| 2.14 | Mobile and Remote Access | D | — | 4 | #99, #101, #102, +1 | |
| 2.15 | Secure Software Lifecycle | D | — | 3 | #103, #104, #105 | |

### Chapter 3 — Service Management

| # | Title | State | Ver | Open | Tickets | Notes |
|---|---|---|---|---|---|---|
| 3.01 | Service Catalog and SLA | T | v2.3 | 0 | — | |
| 3.02 | Service Level Management | T | v2.1 | 0 | — | Source of #288 misreading; resolved |
| 3.03 | Service Communication | T | v2.0 | 0 | — | |
| 3.04 | Service Delivery Feedback | T | v2.1 | 0 | — | |
| 3.05 | Service Request Fulfillment | T | v2.1 | 0 | — | |
| 3.06 | Operational Incident Management | T | v2.1 | 0 | — | |
| 3.07 | Problem Management | T | v2.2 | 0 | — | |
| 3.08 | CMDB | D | — | 5 | #131, #132, #133, #134, +1 | Phase 3 feeder for 4.04 |
| 3.09 | Change Management | D | — | 6 | #135, #136, #137, #263, +2 | #263 = bidirectional pipeline ripple from 3.07; Phase 3 feeder for 4.05 |
| 3.10 | Release and Deployment | D | — | 4 | #138, #139, #140, +1 | |
| 3.11 | Capacity and Availability | D | — | 4 | #141, #142, #143, +1 | |
| 3.12 | Monitoring and Event Management | D | — | 5 | #144, #145, #146, +2 | |
| 3.13 | Knowledge Management | D | — | 4 | #147, #148, #149, +1 | Phase 3 feeder for 4.03 |
| 3.14 | IT Project Management | D | — | 3 | #150, #151, #152 | |
| 3.15 | Service Continuity | D | — | 3 | #153, #154, +1 | Feeds 4.05 continuity tier classification |
| 3.16 | Service Improvement | D | — | 4 | #155, +3 | |
| 3.17 | System Maintenance and Vendor Repairs | D | — | 2 | +2 | |

### Chapter 4 — Incident Response

| # | Title | State | Ver | Open | Tickets | Notes |
|---|---|---|---|---|---|---|
| 4.01 | IR Policy Overview | T | v2.0 | 0 | — | |
| 4.02 | Identification and Reporting | D | — | 1 | +1 | Carries #264 subtask (L3 stage 1 triage); standalone in Phase 3 |
| 4.03 | Containment Strategy and Playbooks | D | — | 0 | — | Source of truth for §6.16 transcription |
| 4.04 | Eradication | D | — | 1 | +1 | Phase 3 collector (3.08 → 4.04) |
| 4.05 | Recovery and Restoration | D | — | 5 | #221, +4 | Phase 3 collector (3.09 → 4.05); **evaluate return-to-drafted candidacy** |
| 4.06 | Communication Protocols | T+ | v2.1 | 2 | #268, LASO ripple | Phase 1 LASO cleanup batch (combined v2.2 with #268) |
| 4.07 | Postmortem and Lessons Learned | D | — | 2 | #259, +1 | #259 = scope boundary with 3.06 §6.8; standalone in Phase 3 |

### Chapter 5 — Compliance

| # | Title | State | Ver | Open | Tickets | Notes |
|---|---|---|---|---|---|---|
| 5.01 | Implementation, Enforcement, Legal | T+ | v3 | 2 | +2 | Carries #264 subtask (tiered exception approval) |
| 5.02 | Internal Audits | D | — | 5 | +5 | |
| 5.03 | Compliance Monitoring | D | — | 2 | +2 | |
| 5.04 | Performance Metrics | D | — | 1 | +1 | |
| 5.05 | Security Control Assessment | D | — | 1 | +1 | |
| 5.06 | Vendor Compliance | D | — | 2 | +2 | |
| 5.07 | Annual Policy Review | D | — | 2 | +2 | Consumes outputs from 5.02, 5.04, 3.16, 5.03, 1.09, 5.01 |

### Chapter 6 — Appendices

| # | Title | State | Ver | Open | Tickets | Notes |
|---|---|---|---|---|---|---|
| 6.01 | Glossary | A | — | 5 | +5 | Highest downstream impact |
| 6.02 | Policy Matrix | A | — | 3 | +3 | |
| 6.03 | Workforce Roles STAK Matrix | A | — | 3 | +3 | |
| 6.04 | Revision History and Version Control | A | — | 1 | #205 | Title patched from `[6.05]` typo on April 11, 2026 |

---

## §6. Recommended Sequence

Sequencing principles, in priority order:

1. Clear architectural roots before downstream cleanup
2. High-impact-first (closes the most architectural risk per session)
3. Pair Chapter 3 feeders with their Chapter 4 collectors in adjacent sessions
4. Two recalc markers — sequence past them is provisional and gets rebuilt at each marker

---

### Phase 1 — Root Resolution

**Goal:** Land the LASO designation in 1.11 and clean up the immediate downstream ripples on already-tightened policies. Highest-impact phase by margin — clears one root and resolves nine downstream LASO targets in two sessions.

1. **~~1.11 (Data Governance and Classification)~~** — ✅ **Complete (v2.1, April 11, 2026).** #220 LASO designation landed. #52 §5 split implemented. #231 §4 Assessment added. FIPS versions stripped per #291. TAC removed (department-level actors, not IO). Two cross-validator rounds completed. LASO appointment authority: IT Director; designee must be IO Department member; registered with Nevada DPS.
2. **LASO downstream cleanup batch** — single coordinated session covering:
   - **4.06 v2.2** — combined cut absorbing LASO §3 fix + #268 Admin Asst directory reassignment
   - **1.14 v2.3** — LASO §3 cleanup
   - **Auto-close #283** as `superseded` when the batch commits

> ## ◆ RECALCULATE SEQUENCE HERE ◆
>
> **Stop. Before starting Phase 2:**
>
> - Re-run the architectural roots check in §3
> - Refresh per-policy ticket counts against current GitHub state
> - Verify no new ripples surfaced during 1.11 tightening that would change Phase 2 ordering
> - Confirm the LASO downstream queue (2.01/2.02/2.04/2.06/2.11/2.12/2.13) is still accurate
>
> Skipping this recalc is a process violation. The working set has shifted.

---

### Phase 2 — Foundational Governance

**Goal:** Close the highest-defect Chapter 1 untightened policies. Foundational defects propagate further than operational ones, so closing them early reduces future ripple surface area.

3. **1.09 (Risk Management)** — 5 open tickets including #46 (broken §4 reference). Feeds outputs into 5.07. Highest-impact Chapter 1 untightened.
4. **1.05 (Policy Review and Update Procedures)** — 3 open tickets. Defines the *Technical Directives* construct referenced manual-wide.
5. **1.06 (IT Governance and Oversight Structure)** — 5 open tickets. Last foundational governance untightened.

---

### Phase 3 — 3→4 Feeder/Collector Pairs

**Goal:** Tighten Chapter 3 feeder policies and their Chapter 4 collectors in adjacent sessions, so the feeder's constructs are fresh in context when the collector is read. Minimizes context-switching cost between dependent policies and catches inter-chapter ripples in-session rather than as deferred discoveries.

6. **3.08 (CMDB)** — 5 open tickets. Source of CI records consumed by Chapter 4.
7. **4.04 (Eradication)** — 1 open ticket. Consumes 3.08 CI scope; references the umbrella RFC pattern that 3.09 owns.
8. **3.09 (Change Management)** — 6 open tickets including #263 bidirectional pipeline ripple from 3.07. Owns RFC governance.
9. **4.05 (Recovery)** — 5 open tickets. Consumes 3.09 RFC governance and 3.15 continuity tier classification. **High ticket count — evaluate for return-to-drafted candidacy during this session.**
10. **3.13 (Knowledge Management)** — 4 open tickets. Owns playbook and SOP governance.
11. **4.03 (Containment Strategy and Playbooks)** — 0 currently open tickets (likely to grow during Phase 3). Source of truth for the eventual `1.04_Procedural_Cleanup` §6.16 transcription.
12. **4.02 (Identification and Reporting)** — 1 open ticket. Standalone — its main feeders (3.06, 3.07) are already tightened. Slot anywhere in this phase.
13. **4.07 (Postmortem and Lessons Learned)** — 2 open tickets including #259 (3.06 §6.8 scope boundary). Mostly self-contained. Slot anywhere.

---

### Phase 4 — Remaining Chapter 3

**Goal:** Close out the service management chapter. No tight Chapter 4 dependencies remaining after Phase 3.

14. **3.10 (Release and Deployment)** — 4 tickets
15. **3.11 (Capacity and Availability)** — 4 tickets
16. **3.12 (Monitoring and Event Management)** — 5 tickets
17. **3.14 (IT Project Management)** — 3 tickets
18. **3.15 (Service Continuity)** — 3 tickets. Verify against 4.05 ripples discovered in Phase 3.
19. **3.16 (Service Improvement)** — 4 tickets
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

6.01 (Glossary, highest downstream impact) → 6.02 → 6.03 → 6.04.

---

### Phase 8 — `1.04_Procedural_Cleanup` Cluster

Final pre-v1.0 work. Members: #5, #30, #31, #32, #290. Transcribes Chapter 4's de facto playbook patterns into 1.04 §6.15 and §6.16, lands the §6.8 atomic-level clarification, addresses procedural decoupling and LyX environment work.

Per Robert's April 11, 2026 ruling: this cluster is **not** a hard blocker on v1.0 readiness.

---

### Phase 9 — v1.0 Declaration and Repo Retirement

Final validation pass, README status update, manual declared at v1.0, repo archived. Ongoing maintenance moves to LyX revision history and System of Engagement.

---

## §7. Open Questions / Pending Decisions

- **#264 partial completion tracking** — confirm which subtasks are actually closed in the repo vs. carried in memory only. May need a sweep to align.
- **4.05 return-to-drafted candidacy** — 5 open tickets is a lot for a tightened policy; evaluate during Phase 3.
- **#208/#211 sweep enforcement** — currently absorbed into per-policy tightening; consider whether a single dedicated sweep session would be faster.
- **Phase 3 cross-chapter fatigue check** — the 3→4 pair structure interleaves chapters across sessions. If this proves mentally taxing during execution, consolidate Phase 3 into "all Chapter 3 feeders, then all Chapter 4 collectors."
- **~~LASO registration process specifics (1.11 session prep)~~** — ✅ **Resolved (April 11, 2026).** CJIS v6.0 research confirmed: LASO maps to Section 3.2.9 (Organizational Personnel with Security Responsibilities). No CJIS-mandated qualifications beyond AT-3(d)(4) enhanced training. Registration with Nevada DPS is a state-level administrative requirement, not a CJIS v6.0 statutory mandate. IT Director confirmed: LASO is appointed by the IT Director, can be any IO Department member, was historically appointed informally ("Who is going to handle the audits?"). 1.11 v2.1 reflects this operational reality.
