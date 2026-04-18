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

### Deferred Cluster: `1.04_Procedural_Cleanup` ✅ CLOSED

Closed April 16, 2026. Final member #31 was absorbed into the Phase 5.0 1.04 tightening session and resolved architecturally via the new §6.15 Type/Subtype taxonomy (Procedure → Troubleshooting / Playbook; Information → Reference / Context). The cluster is empty.

**Historical members (all closed):** #5, #30, #31, #32, #290.

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
14. **Cross-validator reviews stale source on repeat findings** — ChatGPT has twice cited draft text that no longer exists in current source (1.04 Phase 5.0 session, rounds 2 and 3 both flagged "legally authoritative" after it was removed in v1.2). Sub-type of the general "stale section references" pattern. Reflexive decline; confirm via grep before engaging.
15. **Cross-validator flags downstream-policy prohibited-language usage as reason to weaken 1.04 §6.9** — the correct response is to fix the downstream policy, not relax the constitutional prohibition. File ripple against the offending policy; decline the 1.04 change. Example: 1.04 Phase 5.0 round 3 — ChatGPT cited 2.12 "Where technically feasible" usage as rationale to narrow §6.9; ripple #324 filed against 2.12, §6.9 unchanged.
16. **Cross-validator misread LyX CommandInset refs as unresolved placeholders** — validators cannot render LyX source; raw text `Policy \begin_inset CommandInset ref` reads as "Policy ." or "Policy (...)" to naive text extraction. All cross-references using LyX insets render correctly in compiled PDF. Confirm via `grep -n "Policy [0-9]\.[0-9]"` against the current source before engaging; reflexive decline for "unresolved cross-references" findings when grep returns zero plain-text matches. (1.12 Round 2 Gap 2, ChatGPT.)
17. **Grant-terms savings clause reintroducing Department Head or external authority over IT asset disposition** — architectural position locked: IT holds unitary authority over IT equipment regardless of funding source. Grant-terms compliance is grant-administration's problem, not a constraint on IT authority. Validators repeatedly propose "savings clauses" that carve out Department Head, Grant Authority, or donor-approval paths. Reflexive decline. (1.12 Rounds 2, 3, 4, ChatGPT. Round 4 instance also quoted pre-tightening source text — compound stale-source + architectural error.)
18. **"Shall be" applied to definitional headers** — "shall" operates on directives, not descriptions. A classification definition (e.g., "IT-Managed: Assets that are...") describes a category; it is not an instruction anyone executes. Applying "shall" to definitional prose produces grammatical noise without governance effect. Obligations associated with each classification live in sub-bullets and are correctly "shall"-anchored. (1.12 Round 3 Gap 2, Gemini.)
19. **Self-generated: option-sets that exclude the architecturally-compliant answer** — when Claude proposes a binary or narrow option-set under a locked architectural decision and omits the option compatible with that decision, the entire option-set is discarded. Do not treat the IT Director's selection from an incomplete menu as an "answer" to build the next step on, and do not flag downstream "tensions" that are artifacts of the flawed menu. Re-draft with the architectural frame stated first (per project instructions Option-Setting Discipline), and offer only frame-compatible options. If no frame-compatible option exists, say so and ask for direction. This is a Claude-side behavioral pattern, not validator feedback, but is captured here because the detection and decline mechanics are identical.
20. **ChatGPT: inline 5.01 §6.6 exception-management language into individual policy §4 sections** — violates the locked by-reference architecture used across the tightened manual (1.05, 1.06, 1.10, 1.11, 1.12, 1.14, 4.03, 1.13, and others all route exceptions to 5.01 §6.6 via short-form reference). When cross-validators propose strengthening exception discipline (time-bounding, remediation timelines, CJIS backstops, open-ended-exception bars) inside a downstream policy's §4, the correct response is to file a ripple against 5.01, not to inline the language downstream. Doing so would create dual-maintenance across ~15 policies and break the pattern 1.10 v2.2 established. Reflexive decline; file ripple against 5.01. (1.13 Rounds 2 and 3, ChatGPT — same proposal re-pushed after Round 2 decline; ripple #334 filed.)
21. **Elevated: pattern #2 citation-order-vs-authority-hierarchy confusion** — original pattern #2 captures that 1.04 §6.11 citation ordering is intentionally distinct from the authority hierarchy. The 1.13 session saw four instances across three rounds from both validators (Gemini R1 Gap 1, Gemini R2 Gap 2, ChatGPT R1 Gap 1, ChatGPT R3 Gap 2), reinforcing that validators consistently misread the Cited/Framework split in 1.04 §6.7 as a flat legal-hierarchy list. When three or more validator rounds reinforce the same "finding" against the same architectural choice, treat that as evidence of validator-level confusion about the source, not a source defect. Reflexive decline on sight; cite pattern #2 without further engagement.
22. **Cross-validator "absence-of-evidence from incomplete retrieval" pattern** — Validator discloses it could not retrieve an authoritative source, then flags the citation as unverified. This is not a finding against the draft; it is the validator's confidence disclosure. When the verification was already performed during drafting against the authoritative source (e.g., CJIS v6.0 PDF, NIST CSF 2.0 CSWP.29, NIST SP 800-53 R5 PDF, Nevada retention schedule), with page numbers or line references cited, the validator claim is moot. Reflexive decline with a pointer back to the original verification. (1.13 Round 3 Gap 3, ChatGPT — LRDA 20070378 and 20070474 verified during v2.1 drafting against 07_Nevada_Log_Retention.pdf pages 8 and 341; ChatGPT could not retrieve and self-rated confidence Low.)
23. **Surface-framing rotation on locked architectural decisions** — Validators repeatedly target the same architectural choice across sequential rounds, rotating the surface rationale each round while the underlying recommendation is identical. Detected when three or more rounds produce "new findings" that resolve to the same architectural change. Reflexive decline on sight once the pattern is confirmed; cite the original standing decline without re-engaging the surface framing. (2.01 Rounds 1–4, ChatGPT — inline 5.01 §6.6 exception-management language targeted four times with four rationales: final-approver ambiguity → CJI non-waiver → IT Director/AID split → 12-month cap restoration. Also 2.01 Rounds 2–4, ChatGPT — LRDA 20071725 verification requested three times with "Low confidence" disclosure each round. All variants fall under decline patterns #20 and #22 respectively; pattern #23 is the meta-pattern identifying that the same target is being re-attempted across rounds.)
24. **Validator misread of §4 optional governed labels as exhaustive mandatory set** — When a policy's §4 uses one of the five governed optional labels (Constructive Notice, Emergency Deviations, Sanctions, Universal Applicability, Mandatory Compliance) from 1.04 §6.6, validators sometimes flag the label as non-canonical, apparently treating the three mandatory labels (Assessment, Enforcement, Exceptions) as the complete governed set. 1.04 §6.6 explicitly permits the five optional labels in addition to the three mandatory ones. Reflexive decline; cite 1.04 §6.6 optional governed set. (2.01 Round 3 Gap 1, ChatGPT — "Universal Applicability" flagged as substantive content that should move to §6, when in fact it is on the 1.04 §6.6 optional governed set and fits the exact use case defined: "For policies that apply regardless of location or work status.")

---

## §5. Per-Policy Defect Inventory

State key: **L** = Locked, **T** = Tightened (clean), **T+** = Tightened with open ripples, **D** = Drafted/untightened, **A** = Appendix.

**Last refreshed:** April 18, 2026 (2.01 Phase 5B session complete — v2.4 committed, #61/#62/#63/#286 closed, sweep-root absorption notes posted on #208/#235/#245/#6/#264, ripples #345 (5.01 §6.8 unsupported 7-year retention)/#346 (2.03 LRDA title harmonization) filed, two new standing-decline patterns captured from Round 3–4 validator behavior).

### Chapter 0 / Front Matter

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 000 | Front Matter | T | v3 | 0 | — |

### Chapter 1 — Governance

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 1.02 | Code of Ethics | T | — | 0 | — |
| 1.03 | Standard Operating Ethos | T | v2.0 | 0 | — |
| 1.04 | Formatting Standards | T | v1.4 | 0 | — |
| 1.05 | Policy Review and Update Procedures | T | v2.2 | 0 | — |
| 1.06 | IT Governance and Oversight Structure | T | v2.1 | 0 | — |
| 1.07 | Workforce Roles | T | v1.3 | 0 | — |
| 1.08 | Delegation of Authority | T | v1.4 | 0 | — |
| 1.09 | Risk Management | T | v2.1 | 0 | — |
| 1.10 | IT Financial / Procurement | T | v2.2 | 0 | — |
| 1.11 | Data Governance and Classification | T | v2.2 | 0 | — |
| 1.12 | IT Asset Management | T+ | v2.6 | 1 | #329 |
| 1.13 | Supply Chain Risk Management | T | v2.2 | 0 | — |
| 1.14 | Stakeholder Engagement | T | v2.3 | 0 | — |

### Chapter 2 — Security

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 2.01 | Acceptable Use | T | v2.4 | 0 | — |
| 2.02 | Personnel Security | D | — | 2 | #64, #217 |
| 2.03 | Security Awareness | D | — | 4 | #66, #67, #68, #213 |
| 2.04 | Access Control | D | — | 2 | #69, #70 |
| 2.05 | Identification and Authentication | D | — | 4 | #71, #72, #73, #292 |
| 2.06 | Privacy and Data Protection | D | — | 5 | #74, #75, #76, #77, #287 |
| 2.07 | System and Communications Protection | D | — | 4 | #78, #79, #80, #293 |
| 2.08 | System Integrity / Malware | D | — | 3 | #81, #83, #84 |
| 2.09 | Vulnerability and Patch Management | D | — | 4 | #85, #86, #87, #271 |
| 2.10 | Secure Configuration Baselines | D | — | 4 | #88, #89, #90, #226 |
| 2.11 | Audit Logging and Monitoring | D | — | 2 | #91, #92 |
| 2.12 | Media Protection and Sanitization | D | — | 4 | #94, #95, #228, #324 |
| 2.13 | Physical Security | D | — | 3 | #96, #97, #98 |
| 2.14 | Mobile and Remote Access | D | — | 4 | #99, #101, #102, #229 |
| 2.15 | Secure Software Lifecycle | D | — | 3 | #103, #104, #105 |

### Chapter 3 — Service Management

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 3.01 | Service Catalog and SLA | T | v2.3 | 0 | — |
| 3.02 | Service Level Management | T+ | v2.5 | 1 | #309 |
| 3.03 | Service Communication | T | v2.0 | 0 | — |
| 3.04 | Service Delivery Feedback | T | v2.1 | 0 | — |
| 3.05 | Service Request Fulfillment | T+ | v2.1 | 1 | #308 |
| 3.06 | Operational Incident Management | T+ | v2.1 | 1 | #313 |
| 3.07 | Problem Management | T+ | v2.2 | 1 | #316 |
| 3.08 | CMDB | T | v2.1 | 0 | — |
| 3.09 | Change Management | T | v2.0 | 0 | — |
| 3.10 | Release and Deployment | T | v2.0 | 0 | — |
| 3.11 | Capacity and Availability | T+ | v2.0 | 1 | #317 |
| 3.12 | Monitoring and Event Management | T+ | v2.0 | 1 | #318 |
| 3.13 | Knowledge Management | T+ | v2.1 | 1 | #322 |
| 3.14 | IT Project Management | T | v2.1 | 0 | — |
| 3.15 | Service Continuity | T+ | v2.1 | 2 | #314, #319 |
| 3.16 | Service Improvement | T | v2.0 | 0 | — |
| 3.17 | System Maintenance and Vendor Repairs | T | v2.1 | 0 | — |

### Chapter 4 — Incident Response

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 4.01 | IR Policy Overview | T | v2.0 | 0 | — |
| 4.02 | Identification and Reporting | T | v2.1 | 0 | — |
| 4.03 | Containment Strategy and Playbooks | T+ | v2.0 | 1 | #323 |
| 4.04 | Eradication | T | v2.2 | 0 | — |
| 4.05 | Recovery and Restoration | T | v2.2 | 0 | — |
| 4.06 | Communication Protocols | T | v2.2 | 0 | — |
| 4.07 | Postmortem and Lessons Learned | T | v1.0 | 0 | — |

### Chapter 5 — Compliance

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 5.01 | Implementation, Enforcement, Legal | T+ | v1.1 | 1 | #345 |
| 5.02 | Internal Audits | D | — | 5 | #183, #184, #185, #186, #278 |
| 5.03 | Compliance Monitoring | D | — | 2 | #187, #279 |
| 5.04 | Performance Metrics | D | — | 1 | #280 |
| 5.05 | Security Control Assessment | D | — | 1 | #188 |
| 5.06 | Vendor Compliance | D | — | 1 | #281 |
| 5.07 | Annual Policy Review | D | — | 3 | #191, #282, #300 |

### Chapter 6 — Appendices

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 6.01 | Glossary | A | draft | 4 | #192, #193, #195, #328 |
| 6.02 | Policy Matrix | A | — | 3 | #196, #197, #198 |
| 6.03 | Workforce Roles STAK Matrix | A | — | 3 | #199, #200, #214 |
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

### Phase 4 — Remaining Chapter 3 ✅

**Goal:** Close out the service management chapter. No tight Chapter 4 dependencies remaining after Phase 3.

14. ~~3.10 (Release and Deployment)~~ — ✅ v2.0, April 13, 2026.
15. ~~3.11 (Capacity and Availability)~~ — ✅ v2.0, April 13, 2026. Ripples: #309 (3.02 data intake), #310 (3.12 threshold receipt).
16. ~~3.12 (Monitoring and Event Management)~~ — ✅ v2.0, April 13, 2026. Ripple: #311 (1.11 LRDA title correction).
17. ~~3.14 (IT Project Management)~~ — ✅ v2.1, April 13, 2026. Ripple: #312 (4.07 reciprocal Out of Scope pointer).
18. ~~3.15 (Service Continuity)~~ — ✅ v2.1, April 14, 2026. Ripples: #313 (3.06 bidirectional reference), #314 (LRDA series mapping).
19. ~~3.16 (Service Improvement)~~ — ✅ v2.0, April 14, 2026. Ripples: #316 (3.07 bidirectional SIR routing), #317 (3.11 remediation plan SIR routing), #318 (3.12 threshold breach SIR routing), #319 (3.15 tabletop findings SIR routing).
20. ~~3.17 (System Maintenance and Vendor Repairs)~~ — ✅ v2.1, April 14, 2026. No ripple issues. Closed #160, #161. Sweep notes on #208, #6, #235. Hallucinated CSF 2.0 PR.MA-02 replaced with verified PR.PS-02/PR.PS-03.

> ~~◆ RECALCULATE SEQUENCE HERE ◆~~ — **Completed April 14, 2026.**
>
> **Recalculation results:**
> - Architectural roots: all 7 active root clusters unchanged; no new roots from Phases 2–4
> - Per-policy ticket counts: all 104 open issues verified against §5; all counts match; "+1" placeholders resolved to confirmed ticket numbers
> - Chapter 2 LASO downstream queue: ordering confirmed (2.01 → 2.06 → 2.02 → 2.04 → 2.11 → 2.12 → 2.13)
> - 5.07 pull-forward: declined — still depends on untightened 5.02–5.06 outputs; stays last in Ch5
> - 1.04_Procedural_Cleanup: stays at Phase 8 after appendices; not a v1.0 blocker
> - **Decision (Robert, April 14):** Tighten 1.04 first (Phase 5 entry 21) before proceeding to remaining Ch1/Ch2, so the constitutional standard is fully locked before the final wave of tightening sessions
>
> **Chapter 3 ripple tickets** (8 open: #308, #309, #313, #314, #316, #317, #318, #319): These are small targeted fixes against already-tightened Ch3 policies (bidirectional references, LRDA series mapping). Resolution approach TBD — may batch, defer to v1.0 validation, or absorb opportunistically.

---

### Phase 5 — Constitutional Lock + Remaining Ch1 + Chapter 2

**Goal:** Lock the formatting standard, clear remaining governance policies, then tighten the entire security chapter. LASO downstream queue (from closed root #220) is prioritized within Ch2 to close out that cleanup batch.

#### 5.0 — Constitutional Lock ✅

| Seq | Policy | Tickets | Rationale |
|---|---|---|---|
| 21 | ~~1.04 (Formatting Standards)~~ — ✅ v1.4, April 16, 2026. #31 absorbed and closed; Phase 8 eliminated. Ripples filed: #322 (3.13), #323 (4.03), #324 (2.12). | 1 (#31, absorbed) | Constitutional standard; must be fully tightened before Phase 5 bulk work so every subsequent session measures against a locked foundation |

#### 5A — Remaining Chapter 1

| Seq | Policy | Tickets | Rationale |
|---|---|---|---|
| 22 | ~~1.12 (Asset Management)~~ — ✅ v2.6, April 17, 2026. Tickets #53, #54, #55, #256, #262, #301 closed. Ripples filed: #325 (3.08 operational state alignment), #326 (2.09 software inventory field alignment), #327 (3.01 IT Asset Catalog reciprocal). | 6 | Highest Ch1 ticket count; feeds Ch2 asset references (2.10 config baselines, 2.12 media protection, 2.09 vuln management) |
| 23 | ~~1.10 (Financial/Procurement)~~ — ✅ v2.2, April 17, 2026. Tickets #50, #51, #225, #299 closed. Ripples filed: #328 (6.01 Glossary terms — Technical Authority, Financial Authority, Technical Approval, Emergency Technical Approval, No Tag/No Registration No Pay), #329 (1.12 NRS 239.125 / NAC 239.155 retention citation consistency). Architectural landing: Emergency Procurement construct renamed to Emergency Technical Approval to preserve Technical/Financial Authority separation; invocation narrowed to IT Director / AID / 1.08-delegated technical approver (within delegation scope only); CJIS citation corrected from legacy 5.1.1.5 to v6.0 SA-9 + Appendix H; CJIS compliance duties anchored to IT Director (as LASO); §6.4 Asset Intake consolidated to by-reference pointer at 1.12 §6.1 (eliminates dual-maintenance liability). | 4 | Procurement governance feeds supply chain |
| 24 | ~~1.13 (Supply Chain/SCRM)~~ — ✅ v2.2, April 17, 2026 (supersedes premature v2.0 commit). Tickets #56, #232 closed. #235 annotated (1.13 removed from sweep scope — zero prohibited-language hits). Ripples filed: #330 (2.12 carry SP 800-88 + sanitization authority), #331 (5.06 §6.1 "where applicable" cleanup), #332 (2.14 remote-access reciprocal), #333 (2.05 named-accounts reciprocal), #334 (5.01 §6.6 exception-management tightening). Architectural landings (v2.0 → v2.2): §4 exception routing corrected from 1.08 to 5.01 §6.6; CJIS legacy sections converted to v6.0 anchors (IR-6, PS-3, SA-9, Appendix H) matching 1.10 v2.2 pattern; §6.4 collapsed to by-reference pointer at 1.12 (eliminates GREEN-tag / IT-Managed dual-maintenance); Unauthorized Commitments relocated from §4 to new §6.9; AID role added for day-to-day vendor governance; vendor incident notification split into CJI 1-hour (CJIS IR-6(a)) and non-CJI 24-calendar-hour branches; covered-equipment graduated timeframes (5 BD doc / 10 BD segregation / 30 CD replacement plan); Enhanced Due Diligence requires independent assurance artifact (vendor-authored questionnaires may supplement but shall not substitute); Subcontractor Flow-Down with default-deny posture; Vendor Personnel Notification (1 business day); IEA tie to 1.14 §6.5; Contractor-Owned Device Support with IO-side-infrastructure carve-out via Clarification tag; Office of Fiscal Affairs CJIS verification reframed as payment-gate-until-LASO-confirms; Monitoring and Service Oversight concrete minimum floor (automated log access / SOC 2 Type II / SIEM integration); new §6.10 Vendor Records Retention (LRDA 20070474 six fiscal years for contracts; LRDA 20070378 three fiscal years for vendor files; one-business-day retrievability via 1.14 §6.5 standard; legal hold suspension). Session ran three cross-validator rounds; Round 3 produced zero new acceptances. | 2 (#56, #232) | Consumes 1.10; feeds 5.06 vendor governance |

#### 5B — Chapter 2 LASO Priority Group

Closes #220 downstream queue. All policies in this group require the "IT Director (as LASO)" pattern established in 1.11/4.06/1.14.

| Seq | Policy | Tickets | Rationale |
|---|---|---|---|
| 25 | ~~2.01 (Acceptable Use)~~ — ✅ v2.4, April 18, 2026. Tickets #61, #62, #63, #286 closed. Ripples filed: #345 (5.01 §6.8 unsupported 7-year acknowledgment retention — anchor to LRDA by-reference), #346 (2.03 LRDA 20071725 title and trigger harmonization at tightening). Sweep notes on #208, #235, #245, #6, #264. Architectural landings: §3 restructured to 6 roles in descending authority with LASO in sub-bullet (closes #286); §4 rebuilt to Assessment / Enforcement / Exceptions labels with optional Universal Applicability; §5 Cited/Framework split with verified CSF 2.0 subcategories (GV.PO-01, GV.RR-04) replacing misattributed PR.AT-01; NRS 205.4765 cited specifically in body + §5; LRDA 20071725 3-year retention authoritative custody assigned to Assistant IT Director; §6.1 three-bullet legal chain (status → consent → notice) with "Users shall have no expectation of privacy" per Q4 decision; §6.4 prohibitions split to one-directive-per-bullet with AI clause scoped to "not a County-managed service" closing public/private/paid loophole; §6.5 four-bullet reporting with 1-hour user-level clock matching CJIS IR-6(a), sensitive-data routing from general assets to Security Incidents, and Exclusion tag carving routine AUP violations out of Chapter 4 intake. 5.01 §6.6 exception routing preserved by-reference. Four cross-validator rounds; standing declines #1, #20, #22 held repeatedly; ChatGPT exception-authority target rotated four framings (final-approver → CJI non-waiver → IT/AID split → 12-month cap) all declined. | 4 (#61, #62, #63, #286) | Broadest user-facing policy; sets Ch2 tone |
| 26 | 2.06 (Privacy/Data Protection) | 5 | Highest Ch2 ticket count; DA approval question (#74) |
| 27 | 2.02 (Personnel Security) | 2 | Personnel security feeds access control |
| 28 | 2.04 (Access Control) | 2 | Foundational — 2.05 I&A depends on it |
| 29 | 2.11 (Audit Logging) | 2 | Consumed by many downstream policies |
| 30 | 2.12 (Media Protection) | 3 | LASO + asset lifecycle tie to 1.12 |
| 31 | 2.13 (Physical Security) | 3 | Completes LASO group |

#### 5C — Chapter 2 Remainder

| Seq | Policy | Tickets | Rationale |
|---|---|---|---|
| 32 | 2.03 (Training) | 4 | Training → access recertification tie (#66) with 2.04 |
| 33 | 2.05 (I&A) | 4 | Depends on 2.04; FIPS fix (#292) |
| 34 | 2.07 (Comms Protection) | 4 | FIPS fix (#293); pairs with 2.05 encryption |
| 35 | 2.08 (Malware) | 3 | Feeds 4.02 (already tightened) |
| 36 | 2.09 (Vuln/Patch) | 4 | Feeds 3.09 change management (already tightened) |
| 37 | 2.10 (Config Baselines) | 4 | Shadow IT routing fix: split IoC → 4.02 vs. config-mgmt remediation → 3.09/2.10 |
| 38 | 2.14 (Mobile/Remote) | 4 | Office 365 product name removal (#7/#99) |
| 39 | 2.15 (Secure Software) | 3 | Lowest dependency; natural Ch2 closer |

> ## ◆ RECALCULATE SEQUENCE HERE ◆
>
> **Stop. Before starting Phase 6:**
>
> - Re-run the architectural roots check — all sweep roots (#208, #211, #235, #245, #6/#7/#10) should be fully resolved or nearly so after Phase 5
> - Refresh Ch3 ripple ticket status — determine if batch resolution is needed before Ch5 compliance work
> - Refresh per-policy ticket counts for Ch5 and Ch6
> - Verify 5.07 feeder chain: are 5.02–5.06 ready to sequence as planned?
> - Evaluate whether any Phase 5 ripples affect Ch5/Ch6 ordering
>
> The remaining phases are **provisional**. Treat them as a starting point for re-planning, not a fixed schedule.

---

### Phase 6 — Chapter 5 Compliance (provisional)

**Goal:** Tighten the audit, enforcement, and compliance monitoring layer. 5.07 last because it consumes outputs from every other Ch5 policy.

| Seq | Policy | Tickets | Rationale |
|---|---|---|---|
| 40 | 5.02 (Internal Audits) | 5 | Produces audit findings that feed 5.03 CAPs |
| 41 | 5.03 (Compliance Monitoring) | 2 | CAP lifecycle; consumes 5.02 findings |
| 42 | 5.04 (Performance Metrics) | 1 | KPI data feeds 5.07 |
| 43 | 5.05 (Security Control Assessment) | 1 | Control assessment results feed 5.07 |
| 44 | 5.06 (Vendor Compliance) | 1 | Consumes 1.13 (tightened in Phase 5A); feeds 5.07 |
| 45 | 5.07 (Annual Policy Review) | 3 | Capstone — consumes 5.02–5.06, 3.16, 1.09, 1.05 outputs |

---

### Phase 7 — Chapter 6 Appendices (provisional)

**Goal:** Finalize supporting appendices. Glossary first because Ch2/Ch5 tightening will have added terms.

| Seq | Policy | Tickets | Rationale |
|---|---|---|---|
| 46 | 6.01 (Glossary) | 3 | Draft delivered April 12; needs term harvest from all tightened policies |
| 47 | 6.02 (Policy Matrix) | 3 | Framework mapping + dependency matrix; currently empty |
| 48 | 6.03 (STAK Matrix) | 3 | NICE/SFIA alignment verification against 1.07 tightened tiers |
| 49 | 6.04 (Revision History) | 1 | Establish consistent entry format |

---

### Phase 8 — `1.04_Procedural_Cleanup` Cluster ✅ ELIMINATED

Phase 8 was eliminated on April 16, 2026. #31 (the last remaining cluster member) was absorbed into the Phase 5.0 1.04 tightening session and resolved architecturally via the new §6.15 Type/Subtype taxonomy. The cluster is empty and closed.

---

### Phase 9 — v1.0 Declaration and Repo Retirement

Final validation pass, README status update, manual declared at v1.0, repo archived. Ongoing maintenance moves to LyX revision history and System of Engagement.

---

## §7. Open Questions / Pending Decisions

- **#264 partial completion tracking** — confirm which subtasks are actually closed in the repo vs. carried in memory only. May need a sweep to align.
- **#208/#211 sweep enforcement** — currently absorbed into per-policy tightening; consider whether a single dedicated sweep session would be faster.
- **Ch3 ripple batch (now 11 tickets: #308, #309, #313, #314, #316, #317, #318, #319, #322, plus #323 on 4.03)** — batch session, defer to v1.0 validation, or absorb opportunistically? Decision pending.
- **Ch1 ripples from 1.10 session** — #329 (1.12 NRS 239.125/NAC 239.155 consistency) — small Ch1 ripple; absorb when 1.12 touches next, or file as scheduled cleanup. #328 routes to 6.01 Glossary and absorbs into the 6.01 tightening session.

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
