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

**Session-close checklist.** At the end of every tightening session, before declaring the session complete:

1. **File all ripple issues immediately** — never defer a ripple as a session note. Ripples are filed to GitHub during the session for proper tracking.
2. **Close resolved issues** — comment with resolution details, then close. Update parent sweep tickets (#208, #8, etc.) with per-policy resolution notes.
3. **Update this plan** — update §5 (target policy state, version, open ticket count) and §6 (mark the completed entry with session summary). If new ripples were filed against other policies, update their §5 rows with the new ticket number and incremented count.
4. **ASK TO UPDATE GITHUB** — Directly ask if I want to sync the final version to GitHub in the session. Assume yes unless I say otherwise.
5. **Verify synchronization** — the plan and the issue tracker shall agree. If a ticket was closed, §5 reflects it. If a ticket was filed, §5 reflects it.
6. **Next Session Notice** — Remind Robert of the next policy that we need to tackle at this point so it doesn't get lost in the conversation.

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
| #220 | LASO Designation Disentanglement | 1.11 | **Closed** (v2.2) | 4.06, 1.14, 2.01, 2.02, 2.04, 2.06, 2.11, 2.12, 2.13 |
| #208 | Standardize "All IT Personnel" → "All Information Operations Personnel" | Manual-wide | Open, sweep | All policies with §3 group identifiers |
| #211 | Verify "Supervisors" matches 1.07 §3 "Supervisors and Leads" | Manual-wide | Open, sweep | Any policy referencing Supervisors |
| #235 | Prohibited language sweep per 1.04 §6.9 | 20 untightened policies | Open, absorbed-by-tightening | Listed in #235 body; resolved per-policy |
| #245 | Replace `business hours` time-unit with end-of-business-day convention | Manual-wide | Open, sweep | Per #245 body |
| #264 | Role obligation redistribution (L3 prep, L1 clerical, L2 inputs, AID synthesis) | Manual-wide | Open, root | 4.02, 4.06, 5.01, plus untightened |
| #283 | LASO is a designation, not a §3 role | Manual-wide | **Closed** (`superseded`, April 11, 2026) — #220 landed in 1.11 v2.1/v2.2; LASO pinned to IT Director by mandate | Same as #220 downstream |
| #6, #7, #8, #10 | Product-name removal (Redmine, Office 365, Comodo/XCitium, HID DigitalPersona) | Manual-wide | Open, absorbed-by-tightening | Resolved per-policy |
| #304 | Chapter 4 external self-containment quality gate — state filing requirement | Ch4 (4.02, 4.07) | **Closed** (April 12, 2026) | All Ch4 policies tightened: 4.01, 4.02, 4.03, 4.04, 4.05, 4.06, 4.07 |
| #291 | Remove hard-coded FIPS 140-2/140-3 transition dates — CMVP by-reference | 1.11, 2.05, 2.07 | Open, sweep | #292 (2.05), #293 (2.07); 1.11 resolved in v2.2 |

### #220 — LASO Designation Disentanglement (detailed entry)

**Home determination:** 1.11 §3 is the correct designation point. #220's exclusion analysis ruled out:

- **1.07** — locked at v1.3, and CJIS-driven compliance liaison roles were deliberately excluded from workforce competency scope
- **1.14** — references LASO as a CJI comms routing participant but is a *consumer*, not a designator
- **A dedicated Chapter 2 CJIS policy** — Chapter 2 is organized by NIST 800-53 control family; creating a CJIS program ownership policy would violate the locked chapter structure

**Why 1.11:** The LASO's core duty is CJI oversight. 1.11 is the CJI-touching policy. The designation belongs where the duty lives.

**Final §3 structure (v2.2):** IT Director holds the LASO designation by policy mandate. No standalone LASO §3 block. LASO obligations are IT Director sub-bullets. §6.11 (LASO Designation and Authority) establishes the policy mandate, DPS registration, and non-delegable accountability construct. Downstream policies use the "IT Director (as LASO)" parenthetical pattern.

**Operational reality of the designation (per Robert, April 11, 2026):** The LASO is not a lightweight internal appointment. The designee is formally registered with the Nevada Department of Public Safety (DPS), which serves as the state-level CJIS Systems Agency intermediary between local agencies and the FBI. The registration chain is **County LASO → Nevada DPS → FBI**. This creates three drafting requirements that 1.11 §3 must address:

- **Designation transfer is heavyweight, not lightweight.** A reassignment requires formal state re-registration with DPS, not just an internal memo. The §3 language must reflect that the designation is held until formally transferred, not rotated for vacation coverage or short-term absence.
- **Distinguish execution delegation from designation transfer.** The LASO authorizing a designee to execute a specific notification under Policy 1.08 (the existing pattern in 4.06 §6.4) is *execution delegation* — lightweight, internal, does not transfer accountability. A change in who *holds* the LASO designation is *designation transfer* — heavyweight, requires DPS re-registration. These are different mechanisms and 1.11 §3 must not conflate them.
- **Gap-state interim posture.** When a LASO designee becomes unavailable suddenly (medical emergency, separation, etc.), there is a registration delay before a successor is fully recognized by DPS. 1.11 §3 must define who holds the LASO obligations during the gap — the previous designee remains accountable until formally relieved, or the IT Director assumes interim execution authority pending DPS registration of the successor.

**Why this satisfies 1.04 §6.5:** Once 1.11 designates LASO with a defined membership boundary (the individual currently holding the written designation), LASO becomes "a defined group with a clear membership boundary" per the §6.5 Role Identity Requirement. Until then, downstream LASO §3 blocks (e.g., 4.06 v2.2) are forward-references to a designation whose home is pending — acceptable as an interim state.

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

**#304 (Chapter 4 external self-containment)** is **closed** (April 12, 2026). All Chapter 4 policies tightened: 4.01 (v2.0), 4.02 (v2.1), 4.03 (v2.1), 4.04 (v2.2), 4.05 (v2.1), 4.06 (v2.2), 4.07 (v2.1).

### Deferred Cluster: `1.04_Procedural_Cleanup`

A constitutional revision of 1.04 mid-project would invalidate prior tightening work. The cluster collects 1.04 tickets that touch §6.15 (SOPs) and §6.16 (Playbooks) — procedural sections that don't affect policy formatting.

**Cluster source-of-truth rule:** Chapter 4 is the source of truth for playbook structure; the cluster transcribes Chapter 4's de facto patterns into 1.04 §6.16, not the other way around. Conflicts resolve in Chapter 4's favor.

**Cluster members:** #31. (Closed April 12, 2026: #5 — §6.10 Redmine resolved; #30 — 6.01 Glossary draft; #32 — §5 ordering verified compliant; #290 — §6.8 atomic-level clarification executed as additive amendment.)

**Cluster status:** Per Robert's April 11, 2026 ruling, this cluster is **not** a hard blocker on v1.0. Sequence by impact, not by dependency clearing. Only #31 (LyX environment names for §6.15/§6.16) remains.

**Distinction from constitutional changes:** Changes to 1.04 §6.1–§6.14 are constitutional (require unlocking 1.04, ripple to all tightened policies). Changes to §6.15–§6.16 are procedural (safe to defer to cluster).

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
11. **ChatGPT: restore product names (e.g., Redmine) for cross-policy consistency** — 1.04 §6.10 prohibits product names; untightened policies will be cleaned during their sessions. Declined three times across two rounds in 3.09 session (April 12, 2026).
10. **Restore TAC as a §3 role in 1.11** — TACs are department-level CJIS designees at consuming agencies (Justice Court, Sheriff's Office, District Court), not IO personnel. ECIO has no authority to impose obligations on them. Declined twice across two validator rounds (April 11, 2026). IT Director confirmed operational reality.
12. **Accept dash Out of Scope convention as Ch4 standing pattern** — 1.04 §6.4 prescribes "[Topic]: **Policy [X.XX]**." with a colon. The "— governed by" pattern was a regression in 4.04 v2.1, corrected in v2.2. 4.05 verified clean. 4.01 v2.0 uses the correct colon format. Decline any suggestion to treat the dash pattern as acceptable.

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
| 1.04 | Formatting Standards | L | — | 1 | #31 | #31 deferred to `1.04_Procedural_Cleanup` cluster. Closed this session: #5 (§6.10 Redmine resolved), #32 (§5 ordering verified compliant), #290 (§6.8 atomic scope clarified). Also: #236 stale 5.01 title fixed, 6× Redmine removed (#6 partial). |
| 1.05 | Policy Review and Update Procedures | T | v2.2 | 0 | — | Technical Directives construct; LRDA 20070057 verified |
| 1.06 | IT Governance and Oversight Structure | T | v2.1 | 0 | — | Phase 2 complete; #300 filed against 5.07 |
| 1.07 | Workforce Roles | T | v1.3 | 0 | — | Locked-adjacent; #220 explicitly excludes LASO from 1.07 |
| 1.08 | Delegation of Authority | T | v1.3 | 0 | — | |
| 1.09 | Risk Management | T | v2.1 | 0 | — | |
| 1.10 | IT Financial / Procurement | D | — | 4 | #50, #51, #299, +1 | |
| 1.11 | Data Governance and Classification | T | v2.2 | 0 | — | #220 root landed; IT Director holds LASO by policy mandate |
| 1.12 | IT Asset Management | D | — | 6 | #53, #54, #55, #256, #301, +1 | #301 = CI record retirement in §6.10 (ripple from 3.08) |
| 1.13 | Supply Chain Risk Management | D | — | 2 | #56, +1 | |
| 1.14 | Stakeholder Engagement | T | v2.3 | 0 | — | Phase 1 LASO cleanup batch complete (April 11, 2026) |

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
| 3.02 | Service Level Management | T | v2.2 | 0 | — | Source of #288 misreading; resolved |
| 3.03 | Service Communication | T | v2.0 | 0 | — | |
| 3.04 | Service Delivery Feedback | T | v2.2 | 0 | — | |
| 3.05 | Service Request Fulfillment | T | v2.2 | 0 | — | |
| 3.06 | Operational Incident Management | T | v2.2 | 0 | — | |
| 3.07 | Problem Management | T | v2.2 | 0 | — | |
| 3.08 | CMDB | T | v2.1 | 0 | — | Phase 3 feeder for 4.04; completed April 12, 2026. v2.1 committed to repo April 12, 2026 (was missing). #8 closed (Comodo/XCitium removed). |
| 3.09 | Change Management | T | v2.1 | 0 | — | Phase 3 feeder for 4.05; completed April 12, 2026 |
| 3.10 | Release and Deployment | D | — | 4 | #138, #139, #140, +1 | |
| 3.11 | Capacity and Availability | D | — | 4 | #141, #142, #143, +1 | |
| 3.12 | Monitoring and Event Management | D | — | 5 | #144, #145, #146, +2 | |
| 3.13 | Knowledge Management | T | v2.1 | 0 | — | Phase 3 feeder for 4.03; completed April 12, 2026. #305 closed (Incident Response Playbooks added to §6.2 + 4.03 added to §5). |
| 3.14 | IT Project Management | D | — | 4 | #150, #151, #152, #295 | |
| 3.15 | Service Continuity | D | — | 3 | #153, #154, +1 | Feeds 4.05 continuity tier classification |
| 3.16 | Service Improvement | D | — | 4 | #155, +3 | |
| 3.17 | System Maintenance and Vendor Repairs | D | — | 2 | +2 | |

### Chapter 4 — Incident Response

| # | Title | State | Ver | Open | Tickets | Notes |
|---|---|---|---|---|---|---|
| 4.01 | IR Policy Overview | T | v2.0 | 0 | — | |
| 4.02 | Identification and Reporting | T | v2.1 | 0 | — | #267 declined (Stage 1 triage — 4.02 activates post-intake; workflow is upstream). #304 gate passed. IC reference→4.01; IC/declaration authority split; LASO→1.11 pattern; 3.03/5.02 titles fixed; CSF DE.AE-03 title corrected, DE.AE-08 added; non-waivable floor expanded; oral exceptions added. No ripple issues filed. |
| 4.03 | Containment Strategy and Playbooks | T | v2.1 | 0 | — | Phase 3 collector (3.13 → 4.03); completed April 12, 2026. Source of truth for §6.16 transcription. #296 closed (emergency axioms verified). |
| 4.04 | Eradication | T | v2.2 | 0 | — | Phase 3 collector (3.08 → 4.04); v2.1 completed April 12, 2026. v2.2 patch pass (April 12, 2026): #302 CM triggers by-reference, #303 IC designee scope broadened + non-transfer, #306 §2 colon format, #307 notification clock + CJIS IR-6 → FA |
| 4.05 | Recovery and Restoration | T | v2.1 | 0 | — | Phase 3 collector (3.09 → 4.05); completed April 12, 2026. IC designee clarifier scoped to any IO Personnel member. County Manager triggers converted to by-reference. Postmortem deferral struck. #306 §2 Out of Scope format verified clean (already uses colon format) |
| 4.06 | Communication Protocols | T | v2.2 | 0 | — | #284 LASO dissolution + #268 Admin Asst directory landed April 11, 2026 |
| 4.07 | Postmortem and Lessons Learned | T | v2.1 | 0 | — | Phase 3 standalone; completed April 12, 2026. IC block merged into IT Dir with 4.01 §6.1 designee clarifier + non-transfer. #208 resolved. 1.08→5.01 §6.6. §4 Enforcement sub-bullets + non-waivable floor. §5 CR/FA split rebuilt; 3 items moved to FA (CJIS IR-4, RS.AN-03, SP 800-61); added DSS03+ITIL CI to FA; added 3.06/3.08/3.09 to CR; removed 1.04/1.08 from CR. §6.2 "responsible for" fixed. §6.7 "Section 2"→"Section 6.1" (pipeline fix). §6.7 3.06 §6.8 acknowledgment (#259). Product names removed (#6). #304 gate passed (final Ch4). Closed #179, #259, #304. No ripple issues filed. |

### Chapter 5 — Compliance

| # | Title | State | Ver | Open | Tickets | Notes |
|---|---|---|---|---|---|---|
| 5.01 | Implementation, Enforcement, Legal | T | v3 | 0 | — | v3 committed April 12, 2026 with #269 AID Operational Exception Tier merged (§3 AID role + §6.6 two new bullets + §5 2.10 added). #207 closed (CBA review deferred to manual-wide legal review). |
| 5.02 | Internal Audits | D | — | 5 | +5 | |
| 5.03 | Compliance Monitoring | D | — | 2 | +2 | |
| 5.04 | Performance Metrics | D | — | 1 | +1 | |
| 5.05 | Security Control Assessment | D | — | 1 | +1 | |
| 5.06 | Vendor Compliance | D | — | 1 | +1 | #189 closed (VCR glossary entry — resolved by 6.01 draft, April 12, 2026) |
| 5.07 | Annual Policy Review | D | — | 3 | #300, +2 | Consumes outputs from 5.02, 5.04, 3.16, 5.03, 1.09, 5.01; #300 = Board reporting triggers from 1.06 |

### Chapter 6 — Appendices

| # | Title | State | Ver | Open | Tickets | Notes |
|---|---|---|---|---|---|---|
| 6.01 | Glossary | A | draft | 3 | #192, #193, #195 | Draft delivered April 12, 2026 (50 definitions + 13 acronym redirects). #242 (SoE entry) and #194 (VCR + SoE + dead CMS term) closed. #192/#193 commented — final harvest/de-dup deferred to Glossary tightening after all policies finalized. #195 (capitalization QC) untouched. |
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

1. **~~1.11 (Data Governance and Classification)~~** — ✅ **Complete (v2.2, April 11, 2026).** #220 LASO designation landed. #52 §5 split implemented. #231 §4 Assessment added. FIPS versions stripped per #291. TAC removed (department-level actors, not IO). Two cross-validator rounds completed. LASO appointment authority: IT Director; designee must be IO Department member; registered with Nevada DPS.
2. **LASO downstream cleanup batch** — single coordinated session covering:
   - **~~4.06 v2.2~~** — ✅ **Complete (April 11, 2026).** #284 LASO §3 dissolution + #268 Admin Asst directory reassignment. Cross-validators: Gemini (no change), ChatGPT (5 findings, all declined).
   - **~~1.14 v2.3~~** — ✅ **Complete (April 11, 2026).** #285 LASO §3 dissolution — standalone LASO block dissolved, obligations folded into IT Director as LASO-capacity sub-bullets. §3 authority ordering corrected (County Manager before AID). §4 Exceptions "co-approval by LASO" replaced with IT Director LASO-capacity evaluation construct.
   - **~~#283 closed as `superseded`~~** ✅ (April 11, 2026)

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

3. **~~1.09 (Risk Management)~~** — ✅ **Complete (v2.1, April 11, 2026).** POA&M→CAP conversion landed (#45). §4 restructured to 1.04 §6.6 template (#47). §5 Cited/Framework split with 3 hallucinated CSF parentheticals corrected (#48). GLOBAL-G role redistribution absorbed (#270). Temporary risk acceptance delegation removed (1.08 conflict). New §6.8 Risk Acceptance Governance consolidates all risk acceptance rules. Remediation timelines eliminated as dual-maintenance (2.09 authoritative). Two cross-validator rounds completed.
4. **~~1.05 (Policy Review and Update Procedures)~~** — ✅ **Complete (v2.2, April 12, 2026).** #33 Purpose construction fixed. #34 §5 Cited/Framework split implemented. #223 5.01 title updated. "Policy Owners" construct eliminated — all review obligations assigned to IT Director. §4 Exceptions rerouted to 5.01 §6.6 (locked architecture). §4 governance-exception elevation added (County Manager approval for material governance exceptions). Technical Directives (§6.3) separated from Emergency Deviations (§4). LRDA 20070057 verified and cited for retention. Retention framework added (1.11, NRS 239.125, NAC 239.155). Emergency axiom verification tickets filed (#294–#299). Two cross-validator rounds completed.
5. **~~1.06 (IT Governance and Oversight Structure)~~** — ✅ **Complete (v2.1, April 12, 2026).** §1 collapsed to one sentence. §2 Out of Scope routing pointers added. §3 restructured (one-directive sub-bullets). §4 rebuilt to 1.04 §6.6 template (Assessment/Enforcement/Exceptions). §5 Cited/Framework split. §6 preamble with 1.08 boundary clarifier. §6.2 LASO pattern applied. §6.4 HR→Human Resources; notification by-reference to 1.08 §6.5. §6.5 (new) Governance Violations. §6.6 (new) Board Engagement triggers. Closed #35, #36, #212, #224, #230. Filed #300 (5.07 Board reporting). Two cross-validator rounds completed.

---

### Phase 3 — 3→4 Feeder/Collector Pairs

**Goal:** Tighten Chapter 3 feeder policies and their Chapter 4 collectors in adjacent sessions, so the feeder's constructs are fresh in context when the collector is read. Minimizes context-switching cost between dependent policies and catches inter-chapter ripples in-session rather than as deferred discoveries.

6. **~~3.08 (CMDB)~~** — ✅ **Complete (v2.1, April 12, 2026).** §1 collapsed to one sentence. §2 restructured to In/Out of Scope. §3: #208 resolved; AID quarterly CI currency review with evidence artifact (#272); exception routing→5.01 §6.6. §4 rebuilt with oral exceptions clause. §5 Cited/Framework split; 1.08 removed (no body citation). §6: Redmine→System of Engagement; Comodo/XCitium→Endpoint Protection Platform; orphaned directives anchored; §6.4 "assigned technician" pattern (3.05 alignment); §6.4 reframed as supplemental closure condition. Closed #131-134, #272. Filed #301 (1.12 §6.10 CI retirement). Two cross-validator rounds.
7. **~~4.04 (Eradication)~~** — ✅ **Complete (v2.1, April 12, 2026).** Dead pol:4.08 reference removed (4.08 absorbed into 4.06). IC (when not IT Director) §3 block merged into IT Director block with designee clarifier — eliminates dual-maintenance and "incorporatively" nonword. Emergency procurement obligation folded into IT Director block. "IT Department Personnel" → "All Information Operations Personnel" (#208). 5 bare Redmine instances replaced with System of Engagement (#6). 2.10 added to §5 Cited References (was missing — cited in §2 Out of Scope). Truncated Credential and Access Remediation sentence completed. Broken external vendor paragraph restructured with IC role anchor. SP 800-61 Rev. 3 title corrected ("Cyber" → "Cybersecurity"). Emergency axiom verification (#297) — all four axioms satisfied. v2.1: Non-waivable floor clause added to §4 Exceptions (ChatGPT partial accept — evidence/audit-records/incident-documentation cannot be waived by exception). Closed #297, #172. No new ripple issues filed. One cross-validator round (Gemini + ChatGPT).
8. **~~3.09 (Change Management)~~** — ✅ **Complete (v2.1, April 12, 2026).** §1 collapsed to one sentence. §2 restructured to In/Out of Scope with 4.01 routing. §3 reordered (CM before AID); exception routing→5.01 §6.6; #208 resolved. §4 rebuilt to 1.04 §6.6 template. §5 Cited/Framework split; ID.AM-04 dropped, ID.RA-07 added (verified CSF 2.0). §6: 7 bare Redmine→SoE/SoR (#6); standing CCA delegation (#273); 3.07 remediation intake (#263); provisional CCA clarified; new §6.8 Compliance Failure Definitions; emergency axioms verified (#294). Closed #135, #136, #137, #233, #263, #273, #294. No new ripple issues filed. Two cross-validator rounds.
9. **~~4.05 (Recovery)~~** — ✅ **Complete (v2.1, April 12, 2026).** Return-to-drafted candidacy evaluated — proceeded with tightening (no architectural defects). Dead pol:4.08 references replaced with pol:4.06; two 4.06 routing pointers merged in §2. IC block merged into IT Director with broad designee clarifier (any IO Personnel member per 4.01); non-transfer clause added for CCA/exceptions/classification. "IT Department Personnel" → "All Information Operations Personnel" (#208). 4 bare Redmine + 1 "(Redmine)" removed (#6). §4 rebuilt with terminal periods, bold fixes. §5 Cited/Framework split restructured — RC.RP-03, RC.RP-05, CP-10, IR-4, CJIS IR-6 moved to Framework Alignment; SP 800-61 title corrected. "CJIS IR-6 notification clock" → "external notification clock" (body routes through 4.02). County Manager triggers converted to pure by-reference to 3.09 §6.6 (eliminates triple-maintenance). Postmortem deferral struck from §6.6 Handback preconditions (dead letter per 4.07 §6.1). CSA/CSO expanded. CJI governing agreements tightened. CSF 2.0 RC.CO-03 verified valid. Emergency axioms verified (#298). Closed #174, #175, #219, #221, #240, #298. Filed #302 (4.04 CM trigger consolidation), #303 (4.04 IC designee scope), #304 (Ch4 external self-containment gate). No cross-validator round yet.
10. **~~3.13 (Knowledge Management)~~** — ✅ **Complete (v2.1, April 12, 2026).** §1 rewritten from prohibited "The purpose of this policy is to..." to single-sentence "This policy governs..." construction (#147). §2 restructured to In Scope sub-bullets + Out of Scope routing pointer format. §3: "Administrators (general)" descriptive label eliminated — Support Specialist approval and Standard change authoring obligations duplicated to Network Administrator and Systems Administrator blocks; "All IT Department Personnel" → "All Information Operations Personnel" (#208); AID role redistributed per #276 (system ownership retained with explicit 3.06 pre-escalation search linkage; continuous currency removed — domain admins own content). §4: exception routing moved from 1.08 to 5.01 §6.6; oral exceptions clause added; 5.01 and 5.02 titles updated (#148). §5: Cited/Framework split implemented (#149); 3.02 and 3.11 removed (zero body citations); 1.08 removed (no longer cited); COBIT/ITIL → Framework Alignment. §6: 2 bare Redmine → System of Engagement (#6); orphaned directives anchored throughout; Known Error timeframes converted to by-reference to 3.07 (eliminates dual-maintenance); §6.6 Documentation-Before-Closure anchored to assigned technician with Clarification tag; §6.7 split into four labeled topic blocks (Review, Retirement, Retention, Confidentiality); NRS 239.125 body-text citation added; hold language added to Retention (litigation/audit/public records); public records Clarification added to Confidentiality (per 1.04 §6.1 pattern). Closed #147, #148, #149, #276. No new ripple issues filed. One cross-validator round (Gemini + ChatGPT).
11. **~~4.03 (Containment Strategy and Playbooks)~~** — ✅ **Complete (v2.1, April 12, 2026).** §1 collapsed to single sentence; activation/dual-audience context moved to §6 preamble. §2 Out of Scope converted to 1.04 §6.4 colon format (regression identified in 4.04/4.05 — filed #306). In Scope policy pointer removed. §3: IC block merged into IT Director with designee clarifier (any IO Personnel per 4.01) + non-transfer clause (CCA/exceptions); "IT Department Personnel" → "All Information Operations Personnel" (#208); 5 bare Redmine → functional labels (#6). §4: Enforcement broken into individually auditable sub-bullets; non-waivable floor clause added (audit logs, CJI forensic evidence, CJIS notification obligations, containment-complete documentation). §5: 4.05 and 4.07 added to Cited References (missing); CJIS IR-4/IR-5/IR-6, NIST CSF RS.MI-01, NIST SP IR-4/IR-5/IR-8, SP 800-61 Rev. 3 moved to Framework Alignment (no body-text identifier citations); SP 800-61 Rev. 3 title corrected ("Cybersecurity"). §6.1: truncated Isolation definition repaired; IC scope corrected (any IO Personnel per 4.01); "CJIS IR-6 Part (a)" → "external notification clock" (per 4.05 pattern). §6.2: truncated forensic preservation sentence repaired; broadened to IC materiality determination for non-CJI systems + mandatory for CJI (ChatGPT C3 partial accept). §6.3: County Manager triggers → by-reference to 3.09 §6.6; PIR → by-reference to 3.09 §6.5. §6.4: notification windows removed (by-reference to 4.02 §6.6). §6.5: 1.04 §6.9 → §6.16 (wrong playbook formatting section); "shall own" → "shall maintain" (Gemini G5); review trigger anchored to AID. Emergency axioms verified (#296 — all four satisfied). Ch4 self-containment gate (#304) passed. Closed #296. Filed #305 (3.13 playbook KB category), #306 (4.04/4.05 Out of Scope format regression), #307 (4.04 notification clock + SP title). One cross-validator round (Gemini + ChatGPT): Gemini 1/14 accepted (G5 "own"→"maintain"); ChatGPT 2/3 accepted (C2 CJIS notification floor, C3 broadened forensic preservation); ChatGPT C1 declined (conflated Declaration Authority with IC Designation — separate constructs in 4.01).
12. **~~4.02 (Identification and Reporting)~~** — ✅ **Complete (v2.1, April 12, 2026).** #267 declined — IT Dir/AID reviews all work orders before release; 4.02 activates post-intake, so Stage 1 triage is upstream. #304 self-containment gate passed (lifecycle sentence added to §6 preamble). §3 IT Dir sub-bullet 1: IC reference changed from 3.06→4.01 §6.1 with designee clarifier (any IO Personnel per 4.01) and non-transfer clause (declaration authority, exception approval, classification). §3 IT Dir sub-bullet 6 split: IC designation removed (conflated with emergency declaration authority); emergency declaration authority list now standalone sub-bullet (Tier L3+ only per 1.08). §3 IT Dir sub-bullet 4: LASO language updated to 1.11 pattern; 1.11 added to §5 Cited References. §3 All IO Personnel: 3.06 parenthetical added (new first prose use). §4 Exceptions: oral exceptions clause added; non-waivable floor expanded (work order creation, CJI evidence retention, incident record documentation). §5: 3.03 title→"Service Communications Policy"; 5.02 title→"Internal Audits, Self-Assessment, and Control Testing". §5 FA: DE.AE-03 title corrected to "Multi-Source Information Correlation"; DE.AE-08 added. CSF verification against NIST CSWP 29: 7/8 valid, 1 title correction (DE.AE-03). Closed #267. No ripple issues filed. One cross-validator round (Gemini + ChatGPT): Gemini 0/8 accepted (3 false positives including hallucinated prohibited term, 2 already addressed, 1 wrong policy, 1 standing decline #7, 1 redundant); ChatGPT 0/4 accepted (C1 contradicts 4.01/1.08 Designated Appointment construct — no tier prerequisite, C2 dual-maintenance — \"genuinely unavailable\" is settled 4.01/1.08 language, C3 lacks tightened 1.11 source — #220 root resolved, C4 NRS 603A.220 placement correct per 1.04 §6.7).
13. **~~4.07 (Postmortem and Lessons Learned)~~** — ✅ **Complete (v2.1, April 12, 2026).** IC block merged into IT Dir with 4.01 §6.1 designee clarifier + non-transfer Constraint. #208 resolved. 1.08→5.01 §6.6. §4 Enforcement sub-bullets + non-waivable floor. §5 CR/FA rebuilt. §6.7 pipeline fix ("Section 2"→"Section 6.1") + 3.06 §6.8 acknowledgment (#259). Product names removed (#6). §6.2 prohibited term fixed. #304 Ch4 gate complete. Closed #179, #259, #304. No ripple issues. No cross-validator round yet.

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

6.01 (Glossary, highest downstream impact — **draft delivered April 12, 2026**; final tightening pass after all policies finalized) → 6.02 → 6.03 → 6.04.

---

### Phase 8 — `1.04_Procedural_Cleanup` Cluster

Final pre-v1.0 work. Members: #5, #31, #32, #290. (#30 closed — resolved by 6.01 Glossary draft, April 12, 2026.) Transcribes Chapter 4's de facto playbook patterns into 1.04 §6.15 and §6.16, lands the §6.8 atomic-level clarification, addresses procedural decoupling and LyX environment work.

Per Robert's April 11, 2026 ruling: this cluster is **not** a hard blocker on v1.0 readiness.

---

### Phase 9 — v1.0 Declaration and Repo Retirement

Final validation pass, README status update, manual declared at v1.0, repo archived. Ongoing maintenance moves to LyX revision history and System of Engagement.

---

## §7. Open Questions / Pending Decisions

- **#264 partial completion tracking** — confirm which subtasks are actually closed in the repo vs. carried in memory only. May need a sweep to align.
- **~~4.05 return-to-drafted candidacy~~** — ✅ **Resolved (April 12, 2026).** Evaluated during 4.05 session — proceeded with tightening. No architectural defects; all 6 open tickets were fixable within a normal tightening pass.
- **#208/#211 sweep enforcement** — currently absorbed into per-policy tightening; consider whether a single dedicated sweep session would be faster.
- **Phase 3 cross-chapter fatigue check** — the 3→4 pair structure interleaves chapters across sessions. If this proves mentally taxing during execution, consolidate Phase 3 into "all Chapter 3 feeders, then all Chapter 4 collectors."
- **~~LASO registration process specifics (1.11 session prep)~~** — ✅ **Resolved (April 11, 2026).** CJIS v6.0 research confirmed: LASO maps to Section 3.2.9 (Organizational Personnel with Security Responsibilities). No CJIS-mandated qualifications beyond AT-3(d)(4) enhanced training. Registration with Nevada DPS is a state-level administrative requirement, not a CJIS v6.0 statutory mandate. IT Director confirmed: LASO is appointed by the IT Director, can be any IO Department member, was historically appointed informally ("Who is going to handle the audits?"). 1.11 v2.2 reflects this operational reality.
