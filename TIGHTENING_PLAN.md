# ECIO Policy Manual — Tightening Execution Plan

**Created:** April 11, 2026
**Owner:** Robert Pratt (IT Director)
**Status:** Living document until manual reaches v1.0; retires with the repo
**Scope:** Sequencing and defect tracking for the ECIO Policy Manual tightening pass

This plan is operational scaffolding for the tightening project. It is not a permanent artifact. Once the manual reaches v1.0, this file and the GitHub repo it lives in are retired; ongoing maintenance moves to the LyX revision history and the System of Engagement under the policy maturation cycle.

---

## §1. Session Protocol

### §1.1 Session Start

1. Fetch `TIGHTENING_PLAN.md`, `README.md`, and `01/104.lyx` from the repo.
2. Check §3 (Architectural Roots). Anything changed that affects what's safe to execute?
3. Check §4 (Standing Decline Patterns). Which validator findings get reflexive decline?
4. Check §5 (Per-Policy Defect Inventory). What's the current ticket list against the target?
5. Confirm the target policy. §6 (Recommended Sequence) names the next one; ask if that's the target or a different one.
6. Fetch the target policy's LyX source. Read it in full before proposing anything.
7. Inventory cross-references in §§1–4 and §6, and citations in §5, of the target policy.
8. For each cross-reference that invokes a specific mechanism, threshold, trigger, or obligation — fetch the referenced policy's LyX source.
9. For load-bearing external framework citations — fetch the authoritative source from `Reference/` if not already verified.
10. Search GitHub for open tickets against the target. Use `state=open&per_page=100` across all pages; filter client-side by title tag. The search API is unreliable for policy-number string matches.
11. Produce the Dependency Manifest (§1.4.1). Begin Tightening Pass (§1.2) after.

**Recalc markers.** §6 contains ◆ RECALCULATE SEQUENCE HERE ◆ markers. At a marker: re-run steps 2–4, refresh ticket counts against live GitHub, re-evaluate remaining sequence before starting new tightening work. Skipping is a process violation.

### §1.2 Tightening Pass

Run the five steps in order against the target policy. Every finding notes location, current text or condition, issue, and proposed fix. Cite GitHub ticket numbers for tracked defects.

#### §1.2.1 Structural Compliance (per Policy 1.04)

- Six-section structure present and correctly ordered.
- §1 Purpose follows template: 1–2 sentences, correct opening, no rationale, no filler.
- §2 Scope uses In/Out Scope routing pointers in colon format (per 1.04 §6.4). No directives or enforcement language in §2.
- §3 roles use defined positions from 1.07 or established institutional titles, descending authority order. Each obligation opens "Shall" + one directive.
- §4 uses flat bolded-bullet-label structure. Assessment, Enforcement, Exceptions mandatory. Optional labels from the 1.04 §6.6 governed set only.
- §5 split into Cited References and Framework Alignment per 1.04 §6.7. Categorical ordering per 1.04 §6.11. COBIT and ITIL default to Framework Alignment unless body-cited by identifier.
- §6 uses decimal subsection notation (6.1, 6.2). No nesting beyond two levels.
- List items end with terminal periods except §5 line items.
- Bold labels followed by colons, not periods.

#### §1.2.2 Language Audit

- Scan §6 for prohibited terms per 1.04 §6.9.
- Flag orphaned directives (no capitalized role anchor).
- Flag passive voice that obscures responsibility. Propose active voice with role anchor.
- Flag vague timeframes. Propose objective thresholds.
- Verify time/quantity syntax (word + digit in parentheses) per 1.04 §6.10.
- Audit-test every directive: "How would an auditor verify this?" If no answer, flag it.

#### §1.2.3 Cross-Reference Integrity

- Every policy or appendix cited by number in §§1–4 or §6 appears in §5 Cited References.
- Nothing in Cited References is absent from body text.
- Nothing in Framework Alignment is body-cited by identifier. If it is, promote to Cited.
- First-use parenthetical titles on internal cross-references. Subsequent: short form only.
- Cross-references use LyX `CommandInset ref` insets, not hard-coded plain text.
- In-body cross-references (§§1–4, §6) are bolded (`\series bold`). §5 cross-references are not bolded.
- Load-bearing external framework citations verified against the authoritative source in `Reference/`. No citation from memory.

#### §1.2.4 Pipeline Coherence

- Every invoked mechanism, threshold, trigger, or obligation from another policy verified against that policy's current LyX source.
- One-way references that should be bidirectional — flag.
- Content restated in both target and dependency (vs. defined once and incorporated by reference) — flag as dual-maintenance.
- Stub-policy references (empty skeleton) — note as pending dependency. Don't try to resolve.

#### §1.2.5 Substantive Tightening

- Directive precision, scope clarity, enforceability.
- Governance loops that can stall (circular approvals, missing escalation, undefined tiebreakers) — flag.
- Obligations without defined non-compliance consequence or escalation path — flag.
- Timeframes or thresholds inconsistent with the same item elsewhere in the manual — flag.
- Role assignments conflicting with 1.07 scope or 1.08 delegation — flag.
- Every proposed change justified by compliance gap, ambiguity, broken pipeline, or structural non-conformance. Style preference alone is insufficient.

### §1.3 Cross-Validator Adjudication

Validators do not have access to tightened source or this plan. Feedback is often stale or pre-tightening. Validator agreement is not evidence of correctness.

For each validator finding:

1. Verify the claim against current LyX source. Fetch fresh; in-context copies may be stale after prior same-session edits.
2. Check §4 (Standing Decline Patterns). Reflexive decline if matched.
3. Accept, decline, or modify with specific rationale. "Contradicts 1.04 §6.7" — yes. "Disagree" — no.
4. New reflex pattern worth capturing? Surface for addition to §4 before session close.

### §1.4 Output Format

#### §1.4.1 Dependency Manifest

List of LyX source files being fetched with a one-line reason per file. Delivered as fetch begins, before Tightening Pass.

#### §1.4.2 Findings Summary

Organized by the five Tightening Pass steps. Per finding: location (section + subsection), current text or condition, issue, proposed fix. Ticket numbers for tracked defects.

#### §1.4.3 Ripple List

Changes that would require updates in other policies. Per ripple: target policy, section, change required. Filed as GitHub issues before session close.

#### §1.4.4 Clean Revised Draft

Complete revised LyX source incorporating accepted changes. Produced only after findings review. IT Director may accept, reject, or modify findings before requesting the draft.

#### §1.4.5 Next Session Recommendation

1–3 policy candidates based on Ripple List and dependency connections surfaced this session. State reason per candidate. IT Director decides. Defer to any §6 recalc marker.

### §1.5 Session Close

Do not declare the session complete. Run the checklist, then ask: "Anything else, or are we done?"

1. File all ripple issues immediately. Never defer as a session note.
2. Close resolved issues. Comment with resolution details. Update parent sweep tickets (#208, etc.) with per-policy notes.
3. File session archive. Title `[Archive] YYYY-MM-DD — Policy X.YY vZ.Z` (or descriptor for cross-cutting work). Label `session-archive`. Close as `not_planned`. Body: metadata (policy, version, tickets closed, ripples filed, declines promoted or held) + full narrative (architectural landings, validator rounds, rulings, standing-decline recurrences). Capture the issue number for step 4.
4. Update this plan. §5: target state, version, ticket count; ripple impacts on other policies' rows. §6: mark completed entry with compressed summary ending `[Archive: #NNN]`. Push.
5. Ask IT Director if the session is done. Continue only on confirmation.
6. Commit tightened LyX via API. Update `README.md` to match. Verify version in the metadata line matches what §5 records. IT Director syncs local repo after.
7. Verify synchronization: plan, issue tracker, repo LyX files, `README.md` — all agree.
8. Remind IT Director of the next policy to tackle.
9. Remind IT Director to compile the manual on his machine:
   ```
   cd ~/Downloads/Policy && git pull
   lyx --export pdf Policy_Manual.lyx
   git add .
   git commit -m "Added compiled Policy Manual"
   git push
   ```

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
| #6 | Product-name removal (Redmine) | 1.04, 1.08, 1.14, 3.01–3.17 | Open, absorbed-by-tightening | Multi-policy Redmine sweep. #7 (Office 365) and #10 (HID DigitalPersona) closed April 19 as duplicates of per-policy children #99 and #71 respectively; #8 closed previously. |
| #353 | Set Header Date and Version to uniform `Effective: July 01, 2026 \| Version: 1.0` | Manual-wide | Open, phase-10-deferred | All policies; mechanical normalization at v1.0 declaration per Phase 10 step 3. Dormant until Phase 10 entry. |
| #355 | Manual-wide LRDA citation verification sweep (numbers, titles, retention periods, NRS 239.125/NAC 239.155 companion citations) | Manual-wide | Open, phase-9-deferred | Scoped in §7 Open Questions for Phase 9: verification half → sub-phase 9A; companion-authority consistency → sub-phase 9B. Split into `phase-9a-intake` and `phase-9b-intake` child tickets at Phase 9 entry. Dormant until then. |
| #375 | Universal §6.X-strip sweep — strip section-specific depth from cross-policy body references | Manual-wide | Open, active-root | Two absorption waves completed April 20–21: first wave #360–#372 (13 tickets against tightened Ch1/Ch2/Ch3/Ch4 peers), second wave #402–#424 (23 tickets covering strips + intra-policy disambiguation). 19 of the second wave closed in-session. #413 (3.12) and #418 (4.01) remain open tracking `of that policy` prose-rewrite cases (mechanical strips applied; prose rewrite pending — reopened April 22 post-audit). 1.04 v1.4 §6.15 residual (4 hits) deferred to dedicated 1.04 session per architectural-lock discipline. Untightened D-state policies (5.03/5.04/5.06/5.07) and Appendix 6.01 absorb into respective tightening/Phase 7 sessions. Scanner-based filing retired April 20 (regex-gap reliability); PDF-driven visual scan + LyX-source classifier is authoritative. Rule #1 in §4 is the underlying rule statement. [Archive: #436] |
### Closed Roots

| # | Title | Resolved | Notes |
|---|---|---|---|
| #220 | LASO Designation Disentanglement | v2.2, April 11 | Landed in 1.11 §6.11. IT Director holds LASO by policy mandate. Downstream cleanup batch (4.06 v2.2, 1.14 v2.3) complete. Untightened LASO queue (2.01/2.02/2.04/2.06/2.11/2.12/2.13) absorbs into normal tightening using "IT Director (as LASO)" pattern. |
| #283 | LASO is a designation, not a §3 role | April 11 | Superseded by #220 landing. |
| #304 | Chapter 4 external self-containment quality gate | April 12 | All Ch4 policies tightened (4.01–4.07). |

**Sweep-style roots (#208, #211, #235, #245, #264, #291, #6)** are applied as a quality gate during each policy's tightening session, not as standalone sweep sessions. Roots stay open until every policy has been touched. **Phase-deferred roots (#353, #355)** are dormant and entered at their scheduled phase (Phase 10 and Phase 9 respectively); they are not absorbed into per-policy tightening.

### Deferred Cluster: `1.04_Procedural_Cleanup` ✅ CLOSED

Closed April 16, 2026. Final member #31 was absorbed into the Phase 5.0 1.04 tightening session and resolved architecturally via the new §6.15 Type/Subtype taxonomy (Procedure → Troubleshooting / Playbook; Information → Reference / Context). The cluster is empty.

**Historical members (all closed):** #5, #30, #31, #32, #290.

---

## §4. Standing Decline Patterns

Cross-validator feedback matching these patterns is reflexively declined.

1. **Merge §5 into a flat list** — violates 1.04 §6.7 Cited/Framework split.
2. **Reorder NIST SP before CSF in citations** — violates 1.04 §6.11; citation order ≠ authority order.
3. **LyX CommandInset false positives** — valid cross-references flagged as broken. Confirm via grep.
4. **ChatGPT hallucinated policies (4.09, 4.10)** — do not exist.
5. **ChatGPT: restore dual-maintenance thresholds in 3.07** — dual-maintenance risk.
6. **ChatGPT: reinstate 1.08 in exception path** — locked; exception routing is 5.01 §6.6 (see §9.1).
7. **Stale section references to pre-tightening versions** — validators lack tightened source.
8. **§6.8 topic-block "violation"** — §6.8 applies at atomic bullet level, not topic-block level. Bold-label topic blocks (§6.12) may contain multiple atomic bullets.
9. **CSF subcategory citation hallucinations** — verify against CSF 2.0 Appendix A (e.g., PR.AT-03 does not exist).
10. **Restore TAC as a §3 role in 1.11** — TACs are consuming-agency designees. ECIO cannot impose obligations on them.
11. **ChatGPT: restore product names for cross-policy consistency** — 1.04 §6.10 prohibits product names.
12. **Accept dash Out of Scope convention as Ch4 standing pattern** — 1.04 §6.4 prescribes colon format.
13. **ChatGPT: narrow 3.12 IC designation to pre-work-order scope** — IC is incorporated by reference from 3.06, not independent authority. Narrowing is architecturally incoherent.
14. **Cross-validator reviews stale source on repeat findings** — grep-verify before engaging. (origin: #427)
15. **Cross-validator flags downstream-policy prohibited-language usage as reason to weaken 1.04 §6.9** — fix the downstream policy, not the constitutional prohibition. File ripple against the offender. (origin: #427)
16. **Cross-validator misread LyX CommandInset refs as unresolved placeholders** — validators can't render LyX source. `grep -n "Policy [0-9]\.[0-9]"` confirms refs resolve in compiled PDF. (origin: #428)
17. **Grant-terms savings clause carving out IT asset authority** — locked unitary IT authority (see §9.1); grant compliance is IT's constraint to verify, not a departmental authority. (origin: #428)
18. **"Shall be" applied to definitional headers** — "shall" operates on directives, not descriptions. Classification definitions describe categories; they are not instructions anyone executes. (origin: #428)
19. **Self-generated: option-sets that exclude the architecturally-compliant answer** — discard the set. Re-draft with the architectural frame stated first per Option-Setting Discipline. If no frame-compatible option exists, ask for direction.
20. **ChatGPT: inline 5.01 §6.6 exception-management language into individual policy §4 sections** — violates locked by-reference architecture (see §9.1). File ripple against 5.01, not the downstream policy. (origin: #430)
21. **Validator re-pushes pattern #2 (citation-order vs. authority-hierarchy confusion) across rounds** — once 3+ rounds confirm the same target, reflexive decline on sight; cite pattern #2 without further engagement. (origin: #430)
22. **Validator "absence-of-evidence from incomplete retrieval"** — validator confidence disclosure, not a finding against the draft. Decline with pointer to original verification. (origin: #430)
23. **Surface-framing rotation on locked architectural decisions** — 3+ rounds with rotating surface rationale targeting the same architectural change = meta-pattern. Reflexive decline once confirmed; cite the original decline. (origin: #431)
24. **Validator misread of §4 optional governed labels as exhaustive mandatory set** — 1.04 §6.6 explicitly permits 5 optional labels (Constructive Notice, Emergency Deviations, Sanctions, Universal Applicability, Mandatory Compliance) beyond the 3 mandatory. (origin: #431)
25. **Self-generated: Clarification contextual clarifier applied to substantive directives** — 1.04 §6.12 restricts Clarification to ambiguity resolution. Integrate into parent or make standalone directive instead. (origin: #432)
26. **ChatGPT: add Nevada retention authorities to §5 of any policy that creates retained records** — 1.11 §6.9 owns the retention authority chain manual-wide; body pointer incorporates by reference. (origin: #432)
27. **ChatGPT: add HIPAA or PHI-specific legal authority when PHI in-scope** — manual-wide pattern in 1.11 v2.3 uses "PHI where applicable" without HIPAA citation. Change 1.11 first if intent shifts. (origin: #432)
28. **Gemini: specific numeric volume tiers for record counts in PIAs** — no Elko County benchmark exists; tier values shift between rounds. Current "approximate record count" is audit-testable without arbitrary structure. (origin: #432)
29. **Cross-validator pushback on locked operational-reality decisions via cross-policy dependency citation** — file a ripple toward operational truth, don't reverse the decision. Distinct from #14 (stale source) and #22 (absence-of-evidence). 3+ rounds re-pushing = reflexive decline. (origin: #433)
30. ~~**Surface-framing rotation on §2 parenthetical-title prohibition**~~ — **RETRACTED April 20, 2026.** Original decline misread 1.04 §6.11 exception clause as permissive; it is prohibitive. Gemini's finding was correct. Not a standing decline. (origin: #434)
31. **ChatGPT: restore hardcoded FIPS 140-2/140-3 transition dates citing "other tightened policies" as precedent** — violates root #291 (CMVP by-reference). Claim that tightened peers carry FIPS transition language is stale source (pattern #14); grep-verify. Authoritative pattern is 1.11 v2.3 §6.5. (origin: #438)

---

## §5. Per-Policy Defect Inventory

State key: **L** = Locked, **T** = Tightened (clean), **T+** = Tightened with open ripples, **D** = Drafted/untightened, **A** = Appendix.

**Last refreshed:** April 23, 2026 post-Phase 5B entry 30 (archive #438). Prior session archives: #427–#436 covering entries 21–29 plus the April 20 §6.X strip batch.

**Phase 5B LASO queue status:** Entries 29 (2.11), 30 (2.12) complete. Entry 31 (2.13) remains. Recalc marker after entry 39 (end of 5C). **Next session: entry 31 — 2.13 (Physical Security and Environmental Controls).** 2.13 open tickets: #96, #97, #98 (3 tickets).

### Chapter 0 / Front Matter

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 000 | Front Matter | T | v3 | 0 | — |

### Chapter 1 — Governance

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 1.02 | Code of Ethics | T | — | 0 | — |
| 1.03 | Standard Operating Ethos | T | v2.0 | 0 | — |
| 1.04 | Formatting Standards | T+ | v1.4 | 1 | #375 |
| 1.05 | Policy Review and Update Procedures | T | v2.2 | 0 | — |
| 1.06 | IT Governance and Oversight Structure | T | v2.1 | 0 | — |
| 1.07 | Workforce Roles | T+ | v1.3 | 1 | #354 |
| 1.08 | Delegation of Authority | T | v1.5 | 0 | — |
| 1.09 | Risk Management | T | v2.1 | 0 | — |
| 1.10 | IT Financial / Procurement | T | v2.2 | 0 | — |
| 1.11 | Data Governance and Classification | T | v2.3 | 0 | — |
| 1.12 | IT Asset Management | T+ | v2.6 | 2 | #329, #426 |
| 1.13 | Supply Chain Risk Management | T | v2.2 | 0 | — |
| 1.14 | Stakeholder Engagement | T | v2.3 | 0 | — |

### Chapter 2 — Security

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 2.01 | Acceptable Use | T+ | v2.4 | 1 | #356 |
| 2.02 | Personnel Security | T+ | v2.4, April 19 | 2 | #358, #376 |
| 2.03 | Security Awareness | D | — | 6 | #66, #67, #68, #213, #346, #351 |
| 2.04 | Access Control | T | v2.4, April 20 | 0 | — |
| 2.05 | Identification and Authentication | D | — | 5 | #71, #72, #73, #292, #333 |
| 2.06 | Privacy and Data Protection | T | v2.6, April 18 | 0 | — |
| 2.07 | System and Communications Protection | D | — | 4 | #78, #79, #80, #293 |
| 2.08 | System Integrity / Malware | D | — | 3 | #81, #83, #84 |
| 2.09 | Vulnerability and Patch Management | D | — | 5 | #85, #86, #87, #271, #326 |
| 2.10 | Secure Configuration Baselines | D | — | 4 | #88, #89, #90, #226 |
| 2.11 | Audit Logging and Monitoring | T | v2.3, April 22 | 0 | — |
| 2.12 | Media Protection and Sanitization | T | v2.3, April 23 | 0 | — |
| 2.13 | Physical Security | D | — | 3 | #96, #97, #98 |
| 2.14 | Mobile and Remote Access | D | — | 5 | #99, #101, #102, #229, #332 |
| 2.15 | Secure Software Lifecycle | D | — | 3 | #103, #104, #105 |

**CSO-exception Constraint strip — pending #425 reframe (5.01 §6.6 clarifier):** Six untightened Chapter 2 policies carry blanket "CJI-involving exceptions require CSO approval" language in their §4 Exceptions blocks: **2.05, 2.07, 2.08, 2.09, 2.10, 2.14.** Ruling during 2.12 v2.3 session (April 23, 2026) established this pattern reflects CJIS-adjacent formality rather than operational workflow. Strip the blanket Constraint sub-bullet during each policy's tightening session; standard 5.01 §6.6 exception framework governs. Does NOT touch genuine CJIS-control-specific CSO clauses (CJIS IR-6 Part (b), PS-3 delegation, AC-7 authorization) in 1.11, 1.13, 1.14, 2.02, 2.04, 4.01, 4.02, 4.05, 4.06, 5.01.

### Chapter 3 — Service Management

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 3.01 | Service Catalog and SLA | T | v2.4 | 0 | — |
| 3.02 | Service Level Management | T+ | v2.5 | 1 | #309 |
| 3.03 | Service Communication | T | v2.0 | 0 | — |
| 3.04 | Service Delivery Feedback | T | v2.1 | 0 | — |
| 3.05 | Service Request Fulfillment | T+ | v2.1 | 1 | #308 |
| 3.06 | Operational Incident Management | T+ | v2.1 | 1 | #313 |
| 3.07 | Problem Management | T+ | v2.2 | 1 | #316 |
| 3.08 | CMDB | T | v2.2 | 0 | — |
| 3.09 | Change Management | T | v2.0 | 0 | — |
| 3.10 | Release and Deployment | T+ | v2.0 | 1 | #377 |
| 3.11 | Capacity and Availability | T+ | v2.0 | 1 | #317 |
| 3.12 | Monitoring and Event Management | T+ | v2.0 | 2 | #318, #413 |
| 3.13 | Knowledge Management | T | v2.2 | 0 | — |
| 3.14 | IT Project Management | T | v2.2 | 0 | — |
| 3.15 | Service Continuity | T+ | v2.1 | 2 | #314, #319 |
| 3.16 | Service Improvement | T | v2.0 | 0 | — |
| 3.17 | System Maintenance and Vendor Repairs | T | v2.1 | 0 | — |

### Chapter 4 — Incident Response

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 4.01 | IR Policy Overview | T+ | v2.0 | 1 | #418 |
| 4.02 | Identification and Reporting | T | v2.1 | 0 | — |
| 4.03 | Containment Strategy and Playbooks | T | v2.1 | 0 | — |
| 4.04 | Eradication | T | v2.2 | 0 | — |
| 4.05 | Recovery and Restoration | T | v2.2 | 0 | — |
| 4.06 | Communication Protocols | T+ | v2.2 | 1 | #378 |
| 4.07 | Postmortem and Lessons Learned | T | v1.0 | 0 | — |

### Chapter 5 — Compliance

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 5.01 | Implementation, Enforcement, Legal | T+ | v1.1 | 3 | #334, #345, #425 |
| 5.02 | Internal Audits | D | — | 4 | #184, #185, #186, #278 |
| 5.03 | Compliance Monitoring | D | — | 2 | #187, #279 |
| 5.04 | Performance Metrics | D | — | 1 | #280 |
| 5.05 | Security Control Assessment | D | — | 1 | #188 |
| 5.06 | Vendor Compliance | D | — | 2 | #281, #331 |
| 5.07 | Annual Policy Review | D | — | 3 | #191, #282, #300 |

### Chapter 6 — Appendices

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 6.01 | Glossary | A | draft | 5 | #192, #193, #195, #328, #352 |
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
| 21 | ~~1.04 (Formatting Standards)~~ — ✅ v1.4, April 16, 2026. #31 absorbed and closed. Phase 8 eliminated. Ripples: #322 (3.13), #323 (4.03), #324 (2.12). [Archive: #427] | 1 (#31, absorbed) | Constitutional standard; locked before Phase 5 bulk work |
#### 5A — Remaining Chapter 1

| Seq | Policy | Tickets | Rationale |
|---|---|---|---|
| 22 | ~~1.12 (Asset Management)~~ — ✅ v2.6, April 17, 2026. Closed: #53, #54, #55, #256, #262, #301. Ripples: #325 (3.08), #326 (2.09), #327 (3.01). [Archive: #428] | 6 | Highest Ch1 ticket count; feeds Ch2 asset references |
| 23 | ~~1.10 (Financial/Procurement)~~ — ✅ v2.2, April 17, 2026. Closed: #50, #51, #225, #299. Ripples: #328 (6.01 glossary), #329 (1.12 retention consistency). [Archive: #429] | 4 | Procurement governance feeds supply chain |
| 24 | ~~1.13 (Supply Chain/SCRM)~~ — ✅ v2.2, April 17, 2026. Closed: #56, #232. #235 annotated (zero prohibited-language hits). Ripples: #330 (2.12), #331 (5.06), #332 (2.14), #333 (2.05), #334 (5.01). [Archive: #430] | 2 (#56, #232) | Consumes 1.10; feeds 5.06 vendor governance |
#### 5B — Chapter 2 LASO Priority Group

Closes #220 downstream queue. All policies in this group require the "IT Director (as LASO)" pattern established in 1.11/4.06/1.14.

| Seq | Policy | Tickets | Rationale |
|---|---|---|---|
| 25 | ~~2.01 (Acceptable Use)~~ — ✅ v2.4, April 18, 2026. Closed: #61, #62, #63, #286. Ripples: #345 (5.01 §6.8 LRDA anchor), #346 (2.03 LRDA title harmonization). [Archive: #431] | 4 (#61, #62, #63, #286) | Broadest user-facing policy; sets Ch2 tone |
| 26 | ~~2.06 (Privacy/Data Protection)~~ — ✅ v2.6, April 18, 2026. Closed: #74, #75, #76, #77, #287. Ripples committed: 1.08 v1.5 (#350), 1.11 v2.3 (#347), 3.14 v2.2 (#349). New ripples: #351 (2.03), #352 (6.01). Standing declines promoted to §4: #26, #27, #28. [Archive: #432] | 5 (#74, #75, #76, #77, #287) | Highest Ch2 ticket count; established IT-lead PIA model |
| 27 | ~~2.02 (Personnel Security)~~ — ✅ v2.4, April 19, 2026. Closed: #64, #217. Ripples: #354 (1.07 5-yr rescreening removal), #355 (manual-wide LRDA sweep), #356 (2.01 group label). Standing decline #29 promoted to §4. [Archive: #433] | 2 (#64, #217) | Personnel security feeds access control |
| 28 | ~~2.04 (Access Control)~~ — ✅ v2.3, April 20, 2026. Closed: #69, #70. Ripple: #358 (2.02 Sanctions NRS overstatement). Standing decline #30 promoted then retracted April 20. [Archive: #434] | 2 (#69, #70) | Foundational — 2.05 I&A depends on it |
| 29 | ~~2.11 (Audit Logging)~~ — ✅ v2.3, April 22, 2026. Closed: #91, #92. Ripples: #425 (5.01 §6.6 CJI-exception CSO-approval Constraint), #426 (1.12 §6.10 Log Custody Transfer). [Archive: #435] | 2 (#91, #92) | Consumed by many downstream policies |
| 30 | ~~2.12 (Media Protection)~~ — ✅ v2.3, April 23, 2026. Closed: #94, #95, #228, #324, #330. Ripples: #425 reframed (5.01 §6.6 CJI-exception clarifier), #437 (1.04 §6.4 internal ref §6.9→§6.11). Standing decline #31 promoted (ChatGPT FIPS transition-date re-push). Pattern #21 meta-threshold triggered on §5 flat-list (3 validator rounds). 2.10 rewrite note landed via architectural ruling (drive-retention default). [Archive: #438] | 5 (#94, #95, #228, #324, #330) | LASO + asset lifecycle tie to 1.12 |
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

**Goal:** Complete 6.01 Glossary at content level. Establish skeleton-only scaffolding for 6.02, 6.03, and 6.04 — the content for these three appendices is populated in Phase 9 (6.02, 6.03 from matrix outputs) or Phase 10 (6.04 from declaration). Completing 6.02/6.03 content at Phase 7 is prohibited; the N-wise analysis required to populate them correctly runs only in Phase 9.

| Seq | Policy | Tickets | Rationale |
|---|---|---|---|
| 46 | 6.01 (Glossary) | 3 | Content-complete at Phase 7. Term harvest from all tightened policies. |
| 47 | 6.02 (Policy Matrix) | 3 | **Skeleton only at Phase 7.** LyX scaffolding, headers, cross-reference machinery. Content populated in Phase 9 from aggregate-audit outputs. |
| 48 | 6.03 (STAK Matrix) | 3 | **Skeleton only at Phase 7.** LyX scaffolding only. NICE/SFIA alignment against 1.07 tightened tiers verified in Phase 9; content populated from Phase 9 role and construct outputs. |
| 49 | 6.04 (Revision History) | 1 | **Skeleton only at Phase 7.** Entry format established. First entry ("v1.0 — Initial publication — July 01, 2026") written at Phase 10. |

---

### Phase 8 — `1.04_Procedural_Cleanup` Cluster ✅ ELIMINATED

Phase 8 was eliminated on April 16, 2026. #31 (the last remaining cluster member) was absorbed into the Phase 5.0 1.04 tightening session and resolved architecturally via the new §6.15 Type/Subtype taxonomy. The cluster is empty and closed.

---

### Phase 9 — Final Integration Pass

**Goal:** Run N-wise audits that the session-by-session tightening protocol is structurally blind to. Individual tightening sessions can only see a target policy and its direct dependencies. Phase 9 holds the complete manual in view at once and catches transitive loops, terminology drift at distance, citation-chain decay, role-obligation collisions, and framework-footprint contradictions that never become visible pairwise.

**Entry criteria.** Phase 9 is strictly terminal. Do not start until:

1. Every policy is at state T (no D remaining in §5).
2. Phase 7 appendix skeletons complete — 6.01 content-complete; 6.02/6.03/6.04 scaffolding in place.
3. Open ripple tickets either resolved or explicitly relabeled `phase-9-intake` with documented scope.

Entry 49 (6.04 skeleton) completion is the trigger. "Same level" means the whole manual at T before any N-wise work begins.

**Freeze discipline.** Phase 9 findings fall into two classes.

- **Phase 9 fix.** Finding changes only citation accuracy, label consistency, construct naming, or editorial quality. Minor version bump on the affected policy (e.g., v2.6 → v2.7). Tracked as a Phase 9 ticket. Tightening protocol does not re-run.
- **Phase 9 substantive.** Finding changes what a directive actually *does* — construct behavior, role authority, pipeline closure logic. Pauses Phase 9 on the affected policy, triggers a one-off tightening session, resumes Phase 9 after.

Test: "does this change what a directive *does*, or only how it's *cited / named / worded*?" First case = fix. Second case = re-tightening.

**No cross-validators inside Phase 9.** Validator feedback is reserved for Phase 10. Phase 9 work is between the IT Director and Claude.

**Deliverable discipline.** Nothing produced inside Phase 9 survives the repo except as content in LyX. Matrix artifacts are scratch paper — they serve the audit and die with the scaffolding. Every Phase 9 finding carries a standing question: "does this conclusion land in LyX body text or appendix content, or does it die with the matrix?" Conclusions that cannot land in LyX do not persist; this is correct for audits that confirm the system works (the corrective change persists; the confirmation does not need to).

**Sub-phase ordering.** Three waves. Accuracy before consistency; content stable before role/pipeline/topology audits; succession walkthrough before editorial.

#### Wave 1 — Content Accuracy

| Sub-phase | Scope | Done-criterion |
|---|---|---|
| 9A Citation Accuracy | Verify every LRDA, CJIS, NIST SP, NIST CSF, NRS, NAC, COBIT, and ITIL citation against its authoritative source. One pass per authority type. | Every cited authority verified; findings resolved. |
| 9C Construct / Terminology Consistency | Every named construct (IC, Hard Fork, Known Error, Technical Directive, Directed Deputization, CAP, Vendor Compliance Record, Annual Policy Review Report, SLA Suspension, Parent-Child Linkage, Formal Closure Declaration, Problem Record Spawn Triggers, others enumerated during the pass) has one canonical name, one canonical definition location, and matching invocations manual-wide. | Construct registry complete; every invocation matches canonical name and form. |

9A and 9C are mutually independent. Interleave by session.

**Gate: Wave 1 complete before Wave 2 opens.**

#### Wave 2 — Aggregate Audits

All Wave 2 sub-phases depend on Wave 1's frozen-accurate baseline. Mutually independent among themselves.

| Sub-phase | Scope | Done-criterion |
|---|---|---|
| 9B Citation Consistency | Every obligation, record class, or control invoked by more than one policy cites the same authority across all invocations. Absorbs former #355 verification/consistency scope. | Zero instances of same obligation cited to different authorities across policies. |
| 9D Role Obligation Accumulation | Enumerate total obligations per major role (IT Director, Assistant IT Director, L1/L2/L3 technicians, Systems Administrator, HR, County Manager, Department Heads, Board of County Commissioners). Audit for achievability and SoD collisions against 1.08 and the SoD Matrix. | Per-role obligation matrix complete; no role operationally impossible; no SoD collision against 1.08. |
| 9E Pipeline Chain Closure | Traverse every named pipeline end-to-end: Known Error lifecycle, CAP lifecycle, Annual Policy Review feedback, Parent-Child Linkage closure, Problem Record Spawn triggers, Hard Fork, Exception Routing, Vendor Compliance Record build, plus others enumerated during the pass. | Every named pipeline traversed; closure confirmed for each. |
| 9F Framework Coverage Topology | Aggregate CSF subcategory / SP control / CJIS section footprint mapped and cross-checked. Flag any framework element invoked with contradictory directives across policies. | Framework footprint matches 6.02 claims; no contradictory control invocations. |

**Gate: Wave 2 complete. Appendices 6.02 and 6.03 populated from Phase 9 matrix outputs.**

#### Wave 3 — Holistic Read

| Sub-phase | Scope | Done-criterion |
|---|---|---|
| 9G Succession Walkthrough | §8 Criterion 3 five-question test, directive-by-directive, cover-to-cover. Single-threaded. | Every directive yields complete answers to the five §8 questions; identified gaps closed. |
| 9H Editorial Pass | Grammar, voice consistency, typography, compiled-PDF render, TOC accuracy, LyX cross-reference inset integrity. Runs last — editorial against still-changing content is wasted effort. | Compiled PDF renders clean; TOC accurate; all LyX insets resolve; no prohibited-language hits per 1.04 §6.9. |

**Phase 9 complete when:** all sub-phases resolved; 6.02 and 6.03 populated; compiled PDF renders clean.

**Scaffolding artifacts produced during Phase 9 (die with repo):**

- Phase 9 finding tickets (labels `phase-9a` through `phase-9h`).
- `Phase9/` folder in repo root: citation consistency matrix, construct registry, role obligation matrices, framework coverage matrices, pipeline traversal reports, succession walkthrough gap report, editorial findings log.

**Persistent outputs (live in LyX / compiled manual):**

- Policy body text corrections.
- 6.02 Policy Matrix populated content.
- 6.03 STAK Matrix populated content.
- Glossary additions (6.01) from construct registry.

**v1.0 Criteria mapping.**

- Criterion 1 (Internal Consistency) — satisfied by 9A, 9B, 9C, 9F, 9H.
- Criterion 2 (Self-Feeding and Self-Growing) — satisfied by 9D, 9E, 9F.
- Criterion 3 (Succession Completeness) — satisfied by 9G directly.

---

### Phase 10 — Declaration Pass

**Goal:** External adversarial review of the complete manual; digest findings; normalize metadata; declare v1.0; archive scaffolding.

**Entry criteria.** Phase 9 complete; compiled PDF renders clean.

**Steps, in order.**

1. **Internal drift audit.** For every policy in the manual, pull the pre-tightening LyX source (first commit on the file) and the tightened LyX source (final commit before Phase 10) from git. Run a substantive diff — not a formatting diff — against each pair. For every substantive delta, trace to an authorizing source: (a) a GitHub issue filed during the tightening session, (b) an explicit decision captured in the session record, or (c) a ruling captured in this plan (§3 roots, §4 declines, or per-policy §5 notes). Deltas that cannot be traced to one of those three sources are drift candidates and are surfaced to the IT Director for review before external adversarial review begins.

    The audit reads for four drift categories specifically, in addition to any general deltas:

    - **Scope collapse** — two or more separately-scoped directives merged into one, eliminating a distinction the original draft maintained. (The 2.04 §6.6 device-lock / VPN-conveyance incident is the canonical example: lock-out period and VPN session exemption were distinct controls addressing distinct exposures; merging them eliminated the screen-exposure control while preserving session continuity.)
    - **Anchor shift** — a directive's role anchor changed without an authorizing ruling (e.g., "Systems Administrator shall" rewritten as "Assistant IT Director shall" when the original assignment was intentional).
    - **Threshold drift** — a numerical value, cadence, or time window that moved without authorization. Includes both permissive drift (loosening) and strict drift (tightening beyond what was authorized).
    - **Boundary erosion** — a carve-out, exemption, or exception that expanded beyond the original, OR a constraint that narrowed. Carve-outs that happen to match framework-permitted baselines (CJIS NOTE carve-outs, NIST SP conditional exceptions) receive special scrutiny, because this is the class of drift that passes framework-checking review while failing the stricter ECIO standard.

    Drift candidates are not automatically reverted. The IT Director rules on each: either the drift is ratified (the tightened version is correct, original was defective), or the original is restored, or a third formulation is authored. All rulings are captured in the session record for the audit.

    **Why this step exists, and why it runs first.** The tightening process layers stricter-than-baseline decisions on top of framework compliance across every policy. Those stricter-than-baseline decisions are currently preserved only by the IT Director's memory and the session record — no automated control catches permissive drift back toward the framework baseline, because framework-checking validators and 1.04 compliance sweeps are both blind to it by construction. Phase 10 step 1 is the mechanical catch: git holds the original, git holds the final, the diff is deterministic, and the authorization trace runs against artifacts that also live in git. External adversarial review (step 2) cannot perform this check because validators lack the session record and the plan's rulings. If drift runs into external review unchecked, adversarial validators will see the drifted manual as given and calibrate their findings against it, compounding the problem.

2. **External adversarial review.** Complete manual (compiled PDF + LyX source) handed to Gemini, ChatGPT, and Grok with instruction: "Aggressively tear this apart." Broad-overview sweeps. No session protocol, no structured finding format — raw output. This is the only role validators play in the final two phases.
3. **Joint digest.** IT Director and Claude review all three validator outputs together. Each finding lands in LyX before declaration OR is explicitly declined with rationale captured in the session record. No deferrals to post-v1.0. Scaffolding dies with the repo; nothing gets carried forward as "follow-up."
4. **Header normalization (#353).** Every policy metadata header set to a uniform string: `Effective: July 01, 2026 | Version: 1.0`. No policy carries its development version number into v1.0. This is the mechanical embodiment of the "fully formed from Zeus' head" posture — the manual reads as given, not as developed.
5. **6.04 Revision History initialization.** Single entry: "v1.0 — Initial publication — July 01, 2026." No back-entries for tightening history. Development archaeology does not exist in the published manual.
6. **Final compilation.** Compile master LyX to PDF. Verify clean render, clean TOC, clean cross-references.
7. **v1.0 declaration.** IT Director marks the manual at v1.0.
8. **Publication handoff.** LyX source and compiled PDF migrate to the System of Engagement as authoritative reference per 1.04 §6.1.
9. **Repo retirement.** GitHub repo archived. `TIGHTENING_PLAN.md`, issue tracker, `Phase9/` matrix folder, all session archives retire with the repo.

**What survives v1.0:**

- LyX master source.
- Compiled PDF.
- 6.04 Revision History (initialized with the single v1.0 entry).

**What does not survive v1.0:**

- GitHub repository.
- `TIGHTENING_PLAN.md`.
- Issue tracker and all tickets (open, closed, superseded).
- `Phase9/` matrix artifacts.
- Session archives, adjudication rounds, standing decline rationales.
- Cross-validator transcripts.

**Post-v1.0 maintenance model.** Future revisions respond to specific events — statutory amendments, framework revisions, organizational changes, operational challenges to policy language. Each change is a LyX edit, recorded as a new 6.04 entry. The development baseline does not reopen. v1.0 is the floor.

---

## §7. Open Questions / Pending Decisions

- **#264 partial completion tracking** — confirm which subtasks are actually closed in the repo vs. carried in memory only. May need a sweep to align.
- **#208/#211 sweep enforcement** — currently absorbed into per-policy tightening; consider whether a single dedicated sweep session would be faster.
- **Ch3 ripple batch (now 11 tickets: #308, #309, #313, #314, #316, #317, #318, #319, #322, plus #323 on 4.03)** — batch session, defer to v1.0 validation, or absorb opportunistically? Decision pending.
- **Ch1 ripples from 1.10 session** — #329 (1.12 NRS 239.125/NAC 239.155 consistency) — small Ch1 ripple; absorb when 1.12 touches next, or file as scheduled cleanup. #328 routes to 6.01 Glossary and absorbs into the 6.01 tightening session.
- **Manual-wide LRDA verification sweep (#355)** — filed April 19, 2026. Scoped for Phase 9 under the April 19 scoping discussion: verification half (LRDA numbers, titles, retention periods) absorbs into sub-phase 9A; companion authority consistency (NRS 239.125 / NAC 239.155 presence across policies that create retained records) absorbs into sub-phase 9B. Action: split #355 into `phase-9a-intake` and `phase-9b-intake` child tickets at Phase 9 entry (or earlier if convenient). Both sit dormant until Phase 9 opens.

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

**Residual work tolerance (revised April 19, 2026):** Under the April 19 scoping decision — v1.0 is fully formed from Zeus' head, no history, no baggage — there is no deferral bucket for development-era items. Every Phase 9 or Phase 10 finding either lands in LyX before declaration or is explicitly declined with rationale captured in the session record. The `1.04_Procedural_Cleanup` cluster is closed (§6 Phase 8 eliminated, April 16, 2026). Post-v1.0 maintenance exists only for genuinely forward-looking operational drivers — statutory amendments, framework revisions, organizational changes, operational challenges — not for deferred tightening work.

---

## §9. Named Constructs and Architectural Positions

Cross-policy definitions Claude needs to preserve during tightening. Modifying a definition here without downstream audit breaks a pipeline.

### §9.1 Core Architectural Positions

- **Unitary IT Authority over IT Assets.** IT manages IT equipment, personnel, and decisions. Departments have no concurrent authority over IT assets regardless of funding source (including grant-funded equipment), department preference, or historical convention. Grant compliance is a constraint IT verifies against, not a departmental authority. Locked — do not propose mediating framings carving out departmental verification, approval, or custody roles.
- **Policy 4.08 absorbed into 4.06.** 4.08 does not exist. Route all Communication Protocols references to 4.06.
- **Exception Routing.** All policy exceptions route to 5.01 §6.6, regardless of the policy being deviated from. Policy 1.08 is a delegation ceiling constraint, not an exception path. Locked — do not propose re-routing exceptions through 1.08.
- **LASO Designation.** Per 1.11 §6.11, the IT Director holds LASO by policy mandate. In body text of other policies, cite as "IT Director (as LASO)" when the CJIS liaison function is specifically invoked.
- **No section-specific cross-references in body prose (Rule #1, April 20, 2026).** Cross-references to other ECIO policies in the body of any policy use `Policy X.XX (Policy Title)` on first use within that policy and `Policy X.XX` thereafter. Section-specific depth (`§6.X`, `Section 6.X`, `§6.11`) shall not appear appended to cross-policy references. Self-references within the same policy are permitted — navigation within the current document is in-scope.
- **§2 Out of Scope routing pointer format (Rule #2, April 20, 2026).** Out of Scope routing pointers end at `Policy [X.XX].` — no parenthetical title, no section depth. Per 1.04 §6.4 format spec and §6.11 exception clause. 1.04 v1.4 §2 itself carries the defect; ripple to file against 1.04 when touched.

### §9.2 Named Constructs

Selection rule: include only constructs that cross multiple policies in non-obvious ways, where the row saves actual session work. Constructs cleanly defined in one policy without cross-policy complexity are not listed — fetch the defining policy when they come up.

| Construct | Primary Definition | Cross-policy pattern / load-bearing notes |
|---|---|---|
| **IC Designation vs. Declaration Authority** | 4.01 §6.1 | Declaration Authority (who calls an incident) is narrow, defined by incident type. Designation Authority (who can be named IC) is broad — any Information Operations Personnel. Do not conflate. |
| **IC Designee Clarifier + Non-Transfer Pattern** | 4.03 / 4.04 / 4.07 | Where a policy invokes IC responsibilities, cite as "IT Director or designee per 4.01 §6.1" with explicit non-transfer sub-bullet stating declaration authority does not transfer to designees. |
| **Known Error Lifecycle** | 3.07 §6.5 → 3.13 → 3.06 §6.4 | Closed loop: Known Error declared and workaround documented (3.07) → Knowledge Base publication within 2 business days (3.13) → mandatory workaround search before escalation (3.06). |
| **Deprecated Asset Labor Ceiling Trigger** | 3.05 §6.5 | 90-day window to evaluate accelerated replacement. Distinct from 30-day Recurring Incident trigger (3.06 / 3.07). Both may fire on the same asset simultaneously. |
| **Directed Deputization** | 1.08 §6.2 | IT Director assigns specific authorities to named personnel for defined durations. Non-delegable list: policy exceptions, risk acceptance, IC declaration, self-access approval, SoD Matrix functions. 10-day lapse remediation window. HR notification via authoritative originator with emergency fallback. |
| **Corrective Action Plan (CAP) Lifecycle** | 5.03 | Governs all remediation tracking manual-wide regardless of originating label. Intakes: 5.02 audit deficiencies, 3.02 sustained SLA non-compliance, 1.09 risk response remediation, 5.03 §6.5 compliance monitoring findings. |
| **Annual Policy Review Report** | 5.07 | Capstone report. Consumes: 5.02 audit summary, 5.04 KPI data, 3.16 improvement summary, 5.03 open CAPs, 1.09 risk register, 5.01 enforcement records. Produces maturity tier assignments. Routes findings back through 5.03, 1.05, 3.16, 1.09. |
| **SLA Suspension** | 3.01 | Only condition under which 3.01 SLA obligations suspend is Hard Fork transfer to Ch4 jurisdiction. No other suspension mechanism exists for routine 3.06 incidents. |

Constructs added during tightening: append to §9.2 only if the row saves session work per the selection rule above. Construct definition changes: file a ripple against the defining policy; do not silently edit §9.2 ahead of the LyX change.
