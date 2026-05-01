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
| #6 | Product-name removal (Redmine) | 1.04, 1.08, 1.14, 3.01–3.17 | Open, absorbed-by-tightening | Multi-policy Redmine sweep. #7 (Office 365) and #10 (HID DigitalPersona) closed April 19 as duplicates of per-policy children #99 and #71 respectively; #8 closed previously. |
| #353 | Set Header Date and Version to uniform `Effective: July 01, 2026 \| Version: 1.0` | Manual-wide | Open, phase-10-deferred | All policies; mechanical normalization at v1.0 declaration per Phase 10 step 3. Dormant until Phase 10 entry. |
| #355 | Manual-wide LRDA citation verification sweep (numbers, titles, retention periods, NRS 239.125/NAC 239.155 companion citations) | Manual-wide | Open, phase-9-deferred | Scoped in §7 Open Questions for Phase 9: verification half → sub-phase 9A; companion-authority consistency → sub-phase 9B. Split into `phase-9a-intake` and `phase-9b-intake` child tickets at Phase 9 entry. Dormant until then. |
| #375 | Universal §6.X-strip sweep — strip section-specific depth from cross-policy body references | Manual-wide | Open, active-root | Two absorption waves completed April 20–21: first wave #360–#372 (13 tickets against tightened Ch1/Ch2/Ch3/Ch4 peers), second wave #402–#424 (23 tickets covering strips + intra-policy disambiguation). 19 of the second wave closed in-session. #413 (3.12) and #418 (4.01) remain open tracking `of that policy` prose-rewrite cases (mechanical strips applied; prose rewrite pending — reopened April 22 post-audit). 1.04 v1.4 §6.15 residual (4 hits) resolved in 1.04 v1.5 via #439 (April 23, 2026). Untightened D-state policies (5.03/5.04/5.06/5.07) and Appendix 6.01 absorb into respective tightening/Phase 7 sessions. Scanner-based filing retired April 20 (regex-gap reliability); PDF-driven visual scan + LyX-source classifier is authoritative. Rule #1 in §4 is the underlying rule statement. [Archive: #436] |
| #456 | LyX CommandInset ref trailing-whitespace defects — render-time space loss after cross-references | Manual-wide | Open, active-root | Children #457 (4.01, 50 occurrences), #458 (4.05, 38 occurrences). Audit method: PDF-rendered visual scan against LyX source. Surfaced April 26, 2026 cross-validator pass. |
| #464 | PDF publication quality — metadata, accessibility tagging, ligature handling | Manual-wide | Open, phase-10-deferred | Compiled `Policy_Manual.pdf` defects affecting publication quality but not content correctness. Dormant until Phase 10 declaration entry. |
| #469 | Convert prohibitive `shall not` directives to verifiable positive `shall` directives where appropriate | Manual-wide | Open, sweep | Filed April 28, 2026 between entries 36 and 37 from in-session observation. Pattern absorbed at 2.10 v2.3 §6.3 (entry 37). Remaining occurrences per parent ticket body. |
| #480 | Retention block architectural uniformity — three patterns coexist across 16 tightened policies (dedicated+bulleted canonical: 1.11/5.02/5.03/5.04; dedicated+prose: 1.10/3.12/4.07/5.01; embedded: 1.05/1.09/1.12/1.14/3.02/3.13/3.15/3.16/4.01) | Manual-wide | Open, phase-9-deferred | Filed May 01, 2026 from Phase 6 entry 43 (5.04 v2.0). Architectural question whether to standardize on dedicated+bulleted manual-wide. 13 policies in scope if standardized. Folds well with #355 LRDA verification sweep at Phase 9. R3 5.04 Gemini "minimum of" / explicit-destruction concerns folded into evaluation scope. Dormant until Phase 9 entry. |
| #481 | Manual-wide open-ended exception inline drift — 9 tightened policies (1.14, 3.02, 3.11, 3.12, 3.13, 3.15, 3.16, 4.01, 4.07) carry inline 5.01 §6.6 exception-management language pre-dating the post-#430 by-reference architecture lock | Manual-wide | Open, sweep | Filed May 01, 2026 from Phase 6 entry 43 (5.04 v2.0) R1 standing-decline-pattern-#20 adjudication. Strip inline language; replace with by-reference form matching 5.02 v2.0 / 5.03 v2.0 / 5.04 v2.0 canonical. Stripping removes the legacy-source argument that drove ChatGPT pattern #41 promotion. Phase 9 sweep candidate or sweep-style absorption during future per-policy touches. |
| #482 | Retention opening prose active-voice anchor needed in 1.11 §6.9, 5.02 §6.6, 5.03 §6.6 — passive "Retention periods shall be applied" / "shall be classified" directives lack explicit role anchor | 1.11, 5.02, 5.03 | Open, ripple | Filed May 01, 2026 from Phase 6 entry 43 (5.04 v2.0) R2 Gemini Gap 1.2 + 1.3 adjudication. 5.04 v2.0 §6.9 corrected in-policy to anchor to AID. May fold into #480 at Phase 9 if retention pattern uniformity sweep proceeds. Low-cost mechanical fix. |
### Closed Roots

| # | Title | Resolved | Notes |
|---|---|---|---|
| #220 | LASO Designation Disentanglement | v2.2, April 11 | Landed in 1.11 §6.11. IT Director holds LASO by policy mandate. Downstream cleanup batch (4.06 v2.2, 1.14 v2.3) complete. Untightened LASO queue (2.01/2.02/2.04/2.06/2.11/2.12/2.13) absorbs into normal tightening using "IT Director (as LASO)" pattern. |
| #283 | LASO is a designation, not a §3 role | April 11 | Superseded by #220 landing. |
| #304 | Chapter 4 external self-containment quality gate | April 12 | All Ch4 policies tightened (4.01–4.07). |
| #291 | Remove hard-coded FIPS 140-2/140-3 transition dates — CMVP by-reference | April 26 | All three children resolved: 1.11 v2.4 (April 11), 2.05 v2.2 (April 26 commit `fcf6b095`), 2.07 v2.2 (April 26 commit `f3d8f876`). CMVP by-reference pattern uniform manual-wide; standing decline #31 is the reflexive-decline rule for future re-push attempts. |
| #467 | §3 role-title trailing-colon compliance per 1.04 §6.5 — manual-wide sweep | April 29 (5D.1) | Resolved across 5 chapter commits (`8d9bb625`, `e805602a`, `d88efe9b`, `da3e8d36`, `c508bc1d`). 233 fixes / 48 files / 49 T-state policies in scope (sweep extended beyond ticket's 36-policy report; 14 ticket-undercount policies absorbed). Carve-outs: 1.04 (constitutional lock, 2 defects, batched to next constitutional revision per ticket text); 5.02 (D-state, 4 defects, tracked as #473 for Phase 6 entry 40 absorption). `sweep_467.py` retained as protocol validator. |
| #468 | §6 governed-clarifier-tag blending compliance per 1.04 §6.12 — manual-wide sweep | April 29 (5D.1) | Resolved across same 5D.1 chapter commits. 10 defects / 6 policies. Per-defect dispositions: 7 Strip + 3 Promote (matches 2.09 v2.0 reference for governed sub-bullet form). Cross-validator review post-commit per IT Director ruling — validator brief produced as session deliverable. `sweep_468.py` retained as protocol validator. |

**Sweep-style roots (#208, #211, #235, #245, #264, #6, #469)** are applied as a quality gate during each policy's tightening session, not as standalone sweep sessions. Roots stay open until every policy has been touched. **Active-root tickets with tracked children (#375, #456)** carry the children to closure under the parent. **Phase-deferred roots (#353, #355, #464)** are dormant and entered at their scheduled phase; they are not absorbed into per-policy tightening.

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
32. **Cross-validator: substitute alternate label for the catch-all "All County Personnel" universal personnel role anchor** — manual-wide convention is "All County Personnel" per 1.04 §6.5 explicit example, used in 2.01 v2.5, 2.04 v2.5, 2.06 v2.7, 2.13 v2.3. Operational scope (including non-employees, contractors, vendors, physical-access holders) is established by §2 enumerated triggers; the §3/§4/§6 catch-all label is convention. Surface framings observed across rounds: "All In-Scope Personnel and Authorized Non-Employees" (R1), "All In-Scope Personnel" (R2 + R3 identical), "All County Personnel and authorized non-employees shall..." (Gem3-2). 3+ rounds re-pushing under rotated framing — pattern #23 trigger; reflexive decline. (origin: 2.03 v2.0 commit `97a451e`)
33. **ChatGPT/validator: restore NRS 205.4765 sanctions language or restore Sanctions §4 bullet citing NRS 205 series** — locked architecture has 5.01 §6.5 owning the sanctions framework manual-wide. April 25 sanctions-restatement sweep (#445–#448) closed this pattern across 1.11/2.01/2.04/2.06. Subsequent rounds confirmed 3+ rotations: 2.05 v2.0 R1 smaller edit #4, 2.05 v2.1 R2 Gap 1. Surface forms rotate ("severe security violation," "legal audit trail," "enforcement actions," "Nevada statutory support"). Reflexive decline; cite #20 architecture + #29 trigger. (origin: #454 / 2.05 v2.2 R2)
34. **Validator hallucinates CJIS v6.0 framework reorganization to delete retained sections** — Gemini round 2 claimed §5.20.7.2/§5.20.7.2.1/§5.20.7.3 belong to obsolete v5.9 because v6.0 transitioned to NIST control-family numbering. Verifiable false: CJIS v6.0 PDF (`Reference/01_CJIS_6.0.pdf`) retains §5.20 mobile policy section structure (TOC p.273 + body text). Distinct from #14 (stale source) — this is positive hallucination of framework reorganization. Decline with PDF page citation. (origin: 2.05 v2.2 R2)
35. **ChatGPT: risk-based softening of CJIS-floor cadences (SI-3 "at least daily" scan, SI-8(2) "at least daily" spam updates)** — CJIS v6.0 SI-3 Control item (c)(1) and SI-8(2) verbatim specify "at least daily" as a hard floor; per authority hierarchy CJIS (#3) outranks NIST SP 800-53 (#4). 2.08 R1/R2/R3 confirmed 3+ rotations: "based on system criticality, operational impact, and CJI exposure" (R1 + R2 + R3 with rotating surface rationale: weekend/holiday compliance trap, server performance, vendor appliances, isolated systems). Operational edge cases route through 5.01 §6.6 exception framework, not policy softening. Reflexive decline; cite CJIS v6.0 Control text + #29 trigger. (origin: 2.08 v2.0 commit `b7384712`)
36. **ChatGPT: restore inline §4 hard-boundary CJI exception language with CSO concurrence requirement** — locked architecture: 5.01 §6.6 owns exception management with CJI Exceptions sub-bullet (CSO concurrence), and 1.09 §6.8 RAM-Prohibition clause forbids waiving CJIS or statutory requirements. 2.09 R1/R2/R3/R4 confirmed 4 rotations of the same architectural target with progressively refined surface framings: "hard boundary statement" (R1) → verbatim repeat (R2) → "exception regression vs. v1.0" (R3) → "exception regression with 12-month cap and remediation owner" (R4). 4-round verbatim/refined repeat satisfies pattern #23 promotion criteria with margin. Reflexive decline; cite #20 (inline 5.01 §6.6 language) + #279 (CJI Constraint strip) + #23 (surface-framing rotation). (origin: 2.09 v2.0 commit `4609e957`)
37. **ChatGPT: enumerate specific non-compliance conditions inline in §4 Enforcement** — locked architecture: 5.01 §6.5 owns the sanctions and enforcement framework manual-wide; per-policy §4 Enforcement uses by-reference to 5.01 (canonical pattern: 2.10 v2.3 §4). Inline enumeration of non-compliance conditions creates dual-maintenance with 5.01 §6.5 and produces an "exhaustive list" interpretation risk that worsens audit posture (auditor zooms to the list, ignores other §3/§6 obligations). 2.14 R1/R2/R3 confirmed 3 rotations of the same architectural target with refined surface framings: "audit defense, mirror Chapter 4 enumeration" (R1) → "audit defense, easier to enforce, easier to audit" (R2) → "drafting pattern in Chapter 4 + audit defense" (R3). 3-round confirmed rotation satisfies pattern #23 promotion criteria. Reflexive decline; cite #20 (inline 5.01 architecture) + #29 (locked-architecture re-push). (origin: 2.14 v2.0 commit `4556509b`)
38. **ChatGPT: substitute "the greater of [framework X] retention or [framework Y] retention" with a hard-coded numeric retention value** — formulation is manual-wide convention from 1.11 v2.5 §6.9. The "greater of" construction is operationally concrete (both values are knowable; computation is deterministic), distinct from genuine subjective thresholds like "sufficient" or "material." ChatGPT substitutes typically hard-code the LRDA value as if it satisfies CJIS — but CJIS AU-9/AU-11 only require the agency to *define* a retention period, not a specific number. Hard-coding eliminates durability across CJIS revisions and creates dual-maintenance with the source schedule. 5.02 R1 + R2 confirmed re-push. Reflexive decline; cite 1.11 §6.9 manual-wide pattern. (origin: 5.02 v2.0 commit `3da57572`)
39. **Validator demands inline restatement of obligations already imposed by upstream policy** — locked by-reference architecture: 1.04 §6.7 establishes Cited References body-cite test, 1.04 §6.11 enforces "Policy X.XX (Title)" first-use citation pattern; both presume by-reference inheritance. Validator findings demanding inline restatement of 1.11 retention/legal-review obligations, 5.01 enforcement/exception obligations, or 1.09 risk obligations within downstream policies create dual-maintenance and progressive divergence as upstream policies are revised. 5.02 R1 (Gemini Gap 4 public-records inline restatement) + R2 (Gemini Gap 5 source-record retention inline restatement) confirmed. Reflexive decline; the upstream policy is the single source of truth. Distinct from #20 (5.01 §6.6 specifically) — this is general by-reference architecture across all upstream policies. (origin: 5.02 v2.0 commit `3da57572`)
40. **ChatGPT: "responsible for" prohibition flagged against non-transfer constructs in §3 role bullets and §2 Scope boundary descriptions** — 1.04 §6.9 prohibits "responsible for" as a directive softener (replacing "shall" with non-binding language). Non-transfer constructs ("The IT Director shall not transfer responsibility for X") and §2 Scope boundary descriptions (describing what is/is not in operational scope) use "responsibility" in its denotative sense, not as a directive softener. 4.04 v2.4 §3 non-transfer construct + 4.05 v2.4 §2 Scope boundary description confirmed during 5D.2. Reflexive decline; the prohibition targets the directive-softening usage, not all forms of "responsibility/responsible." (origin: 5D.2 close note, April 29, 2026; inscribed at 5.02 v2.0 commit `3da57572`)
41. **ChatGPT: inline "no open-ended exceptions" + time-bounding + remediation timeline + compensating measures language into individual policy §4 Exceptions** — locked architecture: 5.01 v2.0 §6.6 Written Documentation bullet owns the exception management framework manual-wide (duration, remediation timeline, compensating measures, "Exceptions shall not be granted on an open-ended basis," CJI Constraint). Per-policy §4 Exceptions uses by-reference (canonical pattern: 5.02 v2.0, 5.03 v2.0, 5.04 v2.0). 5.04 R1/R2/R3 confirmed 3 rotations of the same architectural target with refined surface framings: "incident-response policies use this stronger pattern" (R1, Ch4-precedent framing) → "consistency with similar policies / audit defensibility" (R2, general consistency framing) → "other policies use this stronger formulation including remediation timeline and compensating measures" (R3, specificity-of-formulation framing). 3-round confirmed rotation satisfies pattern #23 promotion criteria. Re-push leverages legacy inline drift in 4.01 v2.1 / 4.07 v1.1 / 7 other policies (captured as ripple #481) as "consistency precedent" — pattern #14 stale-source applies until #481 sweeps the drift. Reflexive decline; cite #20 (origin: #430 inline 5.01 §6.6 architecture) + #29 (locked-architecture re-push) + #14 (mixed source). (origin: 5.04 v2.0 commit `266e9ab3`)

---

## §5. Per-Policy Defect Inventory

State key: **L** = Locked, **T** = Tightened (clean), **T+** = Tightened with open ripples, **D** = Drafted/untightened, **A** = Appendix.

**Last refreshed:** April 30, 2026 post-5.01 v2.0 commit (entry 41 — Phase 6 OMI touch-up). 5.01 T+ v1.2 → T v2.0 (commit `f453669d`; closed #334, #345, #425, #479). Two validator rounds (R3 declined — both validators recycled R1 findings essentially verbatim; diminishing returns). R1 substantive moves: §6.6 Oversight Mechanism Integrity clause inserted (general principle locked from #479; existence/coverage non-waivable, cadence/scope/methodology remain in standard exception path); §6.6 Written Documentation consolidated (remediation timeline, affirmative compensating measures, open-ended bar moved in, CJIS substantive-compliance backstop sentence); §6.6 CJI Exceptions reframed to explicit-negative on CSO concurrence with named CJIS-control examples (IR-6 Part (b), PS-3, AC-7) and instrument-neutral CJIS user agreement language; §6.6 Active Exception Review (renamed from Duration and Review). §6.8 IT-Administrative Enforcement Records (renamed from Corrective Action Records) restructured with population-class LRDA mapping (LRDA 20070321 employees / LRDA 20121869 appointed and elected officials / LRDA 20071300 contractors and vendors); Sanctions Documentation anchored to LRDA 20070321 with HR custodianship; Acknowledgment Records by-reference to originating policy. §6.5 closes CJIS v6.0 PS-8 alignment gap (added "personnel with account management responsibilities"). §6.4 Emergency Protective Action: hard 1-hour notification lock; named-authority next-steps determination; formal-language replacement for "bad act"; "basis" in place of "reasoning". §3 universal label aligned to manual-wide convention ("All County Personnel" per #32). §5 Cited References ripple: CJIS AC-7/IR-6/PS-3 + LRDA 20070321/20071300/20121869 added per body-cite test. R2 absorbed C5-R2 (population-class architecture from ChatGPT). **Watch-list patterns (2 rounds; not yet promoted, need 3+):** ChatGPT enumerated non-waivable list (R1 C1 + R2 Gap 1); ChatGPT OMI cadence/scope/methodology constraint (R1 C2 + R2 Gap 2); ChatGPT §6.3 catch-all narrowing (R1 C3 + R2 Gap 3); ChatGPT CJI verification gate (R1 C4 + R2 Gap 4 — Pattern #23 territory); Gemini "appropriate" → "designated" ISO substitution (R1 G2 + R2 Gap 2). No new standing decline patterns inscribed this session.

**Phase 6 entry 41 complete.** Phase 5C closed (entries 32–39, Chapter 2 cleared); Phase 5D pre-Phase-6 cleanup closed April 29 (5D.1, 5D.2). Phase 6 entry 40 = 5.02 (Internal Audits) committed April 29 at v2.0 (commit `3da57572`). Phase 6 entry 41 = 5.01 (Implementation, Enforcement, Legal — re-tightening) committed April 30 at v2.0 (commit `f453669d`); pulled forward from in-sequence position per IT Director option (a) decision so OMI propagates transitively to 5.03–5.07 before they tighten. Manual-wide tightening count: 41 of 49. Next: Phase 6 entry 42.

### Chapter 0 / Front Matter

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 000 | Front Matter | T | v3 | 0 | — |

### Chapter 1 — Governance

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 1.02 | Code of Ethics | T | v2.3, April 29 | 0 | — |
| 1.03 | Standard Operating Ethos | T | v2.1, April 29 | 0 | — |
| 1.04 | Formatting Standards | T | v1.5 | 0 | — |
| 1.05 | Policy Review and Update Procedures | T | v2.3, April 29 | 0 | — |
| 1.06 | IT Governance and Oversight Structure | T | v2.2, April 29 | 0 | — |
| 1.07 | Workforce Roles | T+ | v1.4, April 29 | 1 | #354 |
| 1.08 | Delegation of Authority | T | v1.6, April 29 | 0 | — |
| 1.09 | Risk Management | T | v2.2, April 29 | 0 | — |
| 1.10 | IT Financial / Procurement | T | v2.3, April 29 | 0 | — |
| 1.11 | Data Governance and Classification | T | v2.5, April 29 | 0 | — |
| 1.12 | IT Asset Management | T+ | v2.7, April 29 | 2 | #329, #426 |
| 1.13 | Supply Chain Risk Management | T | v2.4, April 29 | 0 | — |
| 1.14 | Stakeholder Engagement | T | v2.4, April 29 | 0 | — |

### Chapter 2 — Security

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 2.01 | Acceptable Use | T+ | v2.6, April 29 | 1 | #356 |
| 2.02 | Personnel Security | T | v2.8, April 29 | 0 | — |
| 2.03 | Security Awareness | T | v2.2, April 29 | 0 | — |
| 2.04 | Access Control | T+ | v2.8, April 29 | 1 | #453 |
| 2.05 | Identification and Authentication | T | v2.3, April 29 | 0 | — |
| 2.06 | Privacy and Data Protection | T | v2.8, April 29 | 0 | — |
| 2.07 | System and Communications Protection | T | v2.3, April 29 | 0 | — |
| 2.08 | System Integrity / Malware | T | v2.1, April 29 | 0 | — |
| 2.09 | Vulnerability and Patch Management | T | v2.0, April 28 | 0 | — |
| 2.10 | Secure Configuration Baselines | T | v2.3, April 28 | 0 | — |
| 2.11 | Audit Logging and Monitoring | T | v2.5, April 29 | 0 | — |
| 2.12 | Media Protection and Sanitization | T+ | v2.5, April 29 | 1 | #449 |
| 2.13 | Physical Security | T | v2.4, April 29 | 0 | — |
| 2.14 | Mobile and Remote Access | T | v2.0, April 28 | 0 | — |
| 2.15 | Secure Software Lifecycle | T | v2.0 | 0 | — |

**CSO-exception Constraint strip — pending #425 reframe (5.01 §6.6 clarifier):** All untightened Chapter 2 policies have been processed. Ruling during 2.12 v2.3 session (April 23, 2026) established this pattern reflects CJIS-adjacent formality rather than operational workflow. Standard 5.01 §6.6 exception framework governs. Stripped during tightening: 2.05 v2.2, 2.07 v2.2, 2.08 v2.0, 2.09 v2.0, 2.10 v2.3, 2.14 v2.0. Chapter 2 sweep complete. Does NOT touch genuine CJIS-control-specific CSO clauses (CJIS IR-6 Part (b), PS-3 delegation, AC-7 authorization) in 1.11, 1.13, 1.14, 2.02, 2.04, 4.01, 4.02, 4.05, 4.06, 5.01.

### Chapter 3 — Service Management

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 3.01 | Service Catalog and SLA | T | v2.5, April 29 | 0 | — |
| 3.02 | Service Level Management | T+ | v2.6, April 29 | 1 | #309 |
| 3.03 | Service Communication | T | v2.1, April 29 | 0 | — |
| 3.04 | Service Delivery Feedback | T | v2.2, April 29 | 0 | — |
| 3.05 | Service Request Fulfillment | T | v2.2, April 29 | 0 | — |
| 3.06 | Operational Incident Management | T+ | v2.2, April 29 | 1 | #450 |
| 3.07 | Problem Management | T | v2.4, April 29 | 0 | — |
| 3.08 | CMDB | T+ | v2.3, April 29 | 1 | #461 |
| 3.09 | Change Management | T | v2.1, April 29 | 0 | — |
| 3.10 | Release and Deployment | T+ | v2.1, April 29 | 1 | #377 |
| 3.11 | Capacity and Availability | T+ | v2.1, April 29 | 1 | #451 |
| 3.12 | Monitoring and Event Management | T+ | v2.1, April 29 | 1 | #413 |
| 3.13 | Knowledge Management | T | v2.3, April 29 | 0 | — |
| 3.14 | IT Project Management | T+ | v2.3, April 29 | 1 | #478 |
| 3.15 | Service Continuity | T+ | v2.3, April 29 | 1 | #314 |
| 3.16 | Service Improvement | T+ | v2.1, April 29 | 1 | #452 |
| 3.17 | System Maintenance and Vendor Repairs | T | v2.2, April 29 | 0 | — |

### Chapter 4 — Incident Response

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 4.01 | IR Policy Overview | T+ | v2.1, April 29 | 3 | #418, #457, #477 |
| 4.02 | Identification and Reporting | T | v2.2, April 29 | 0 | — |
| 4.03 | Containment Strategy and Playbooks | T | v2.2, April 29 | 0 | — |
| 4.04 | Eradication | T | v2.4, April 29 | 0 | — |
| 4.05 | Recovery and Restoration | T+ | v2.4, April 29 | 2 | #458, #477 |
| 4.06 | Communication Protocols | T+ | v2.3, April 29 | 1 | #378 |
| 4.07 | Postmortem and Lessons Learned | T+ | v1.1, April 29 | 2 | #477, #478 |

### Chapter 5 — Compliance

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 5.01 | Implementation, Enforcement, Legal | T | v2.0, April 30 | 0 | — |
| 5.02 | Internal Audits | T | v2.0, April 29 | 0 | — |
| 5.03 | Compliance Monitoring | T | v2.0, April 30 | 0 | — |
| 5.04 | Performance Metrics | T | v2.0, May 01 | 0 | — |
| 5.05 | Security Control Assessment | D | — | 1 | #188 |
| 5.06 | Vendor Compliance | D | — | 2 | #281, #331 |
| 5.07 | Annual Policy Review | D | — | 3 | #191, #282, #300 |

### Chapter 6 — Appendices

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 6.01 | Glossary | A | draft | 5 | #192, #193, #195, #328, #352 |
| 6.02 | Policy Matrix | A | — | 4 | #196, #197, #198, #459 |
| 6.03 | Workforce Roles STAK Matrix | A | — | 3 | #199, #200, #214 |
| 6.04 | Revision History and Version Control | A | — | 0 | — |

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
| 31 | ~~2.13 (Physical Security)~~ — ✅ v2.3, April 24, 2026. Closed: #96, #97, #98. Ripples: #440 (1.13), #441 (2.02), #442 (2.11), #443 (2.12) — CJIS "Section" prefix drift regression. [Archive: #444] | 3 (#96, #97, #98) | Completes LASO group; Phase 5B closed |

#### 5C — Chapter 2 Remainder

| Seq | Policy | Tickets | Rationale |
|---|---|---|---|
| 32 | ~~2.03 (Training)~~ — ✅ v2.0, April 25, 2026. Closed: #66, #67, #68, #213, #346, #351. Ripples: #453 (2.04 §6.9 reciprocal training-lapse trigger). Standing decline #31 promoted (catch-all "All County Personnel" label substitution). | 6 (#66, #67, #68, #213, #346, #351) | Training → access recertification tie (#66) with 2.04 |
| 33 | ~~2.05 (I&A)~~ — ✅ v2.2, April 26, 2026. Closed: #71, #72, #73, #292, #333. Standing declines #33 (sanctions-restatement push), #34 (CJIS v6.0 §5.20.x hallucination) promoted. Manual-wide oral-exceptions sweep #454 spawned and closed mid-session (2.02 v2.7, 2.03 v2.1, 2.04 v2.6). [Archive: #455] | 5 (#71, #72, #73, #292, #333) | Depends on 2.04; FIPS fix (#292) |
| 34 | ~~2.07 (System and Communications Protection)~~ — ✅ v2.2, April 26, 2026. Closed: #78, #79, #80, #293. Closes root #291 manual-wide. AID synthesis layer added; AO designation stripped (1.09 owns); CSO-exception Constraint stripped per April 23 ruling; §6.6 Authoritative DNS bullet added (SC-20) per Robert's confirmation that ECIO operates two authoritative DNS servers. Pattern #23 triggers observed in R2 (CSO-Constraint and FIPS-sunset re-push); §4 candidates surfaced but not promoted. [Archive: #465] | 4 (#78, #79, #80, #293) | FIPS fix (#293); pairs with 2.05 encryption |
| 35 | ~~2.08 (System Integrity and Malware Protection)~~ — ✅ v2.0, April 27, 2026. Closed: #81, #83, #84. Ripples: #466 (2.09 SI-5 advisory intake/dissemination directive). Standing decline #35 promoted (ChatGPT recurring CJIS-floor cadence softening for SI-3 daily scan and SI-8 daily spam updates). 3 R-rounds; final commit `b7384712`. | 3 (#81, #83, #84) | Feeds 4.02 (already tightened) |
| 36 | ~~2.09 (Vuln/Patch)~~ — ✅ v2.0, April 28, 2026. Closed: #85, #86, #87, #271, #326, #466. Ripples: #467 (manual-wide §3 role-title trailing-colon, 36 policies / ~178 titles), #468 (manual-wide §6 governed-clarifier-tag-blending, 7 policies / 10 defects). Standing decline #23 promoted (verbatim 4-round CJI exception language re-push). 4 R-rounds; final commit `4609e957`. | 6 (#85, #86, #87, #271, #326, #466) | Feeds 3.09 change management (already tightened) |
| 37 | ~~2.10 (Config Baselines)~~ — ✅ v2.3, April 28, 2026. Closed: #88, #89, #90, #226. CSO-exception Constraint stripped per April 23 ruling. Shadow IT routing implemented per locked architecture: detection → 3.06 operational triage front door (3.06 owns Hard Fork to 4.02 if IoC indicators); registered-system-without-baseline routes to 3.09 change management. CM-7(1) Periodic Review directive added (genuine substantive gap caught at R2). §6.3 positive-directive inversion applied per ticket #469 framing. §6.4 enumerated credential list dropped per Robert's weasel-room concern. CCA assignment removed from §3 (3.09 owns CCA per its tiered model — dual-maintenance avoidance). Standing decline #36 confirmed at rotation 7 cumulative. 3 R-rounds; final commit `a93302b9`. | 4 (#88, #89, #90, #226) | Shadow IT routing fix: 3.06 front door + 3.09 remediation |
| 38 | ~~2.14 (Mobile/Remote)~~ — ✅ v2.0, April 28, 2026. Closed: #99, #101, #102, #229, #332. Ripples: #470 (2.04 §6.6 CJC inactivity-exemption strike, closed in same session — companion commit `34e8edf1` advances 2.04 v2.6 → v2.7). Standing decline #37 promoted (inline §4 enforcement enumeration, 3-round confirmed rotation). CSO-exception Constraint stripped per April 23 ruling (Chapter 2 sweep complete). Three R-rounds; final commit `4556509b`. | 5 (#99, #101, #102, #229, #332) | Final Chapter 2 CSO-exception strip; companion 2.04 v2.7 amendment |
| 39 | ~~2.15 (Secure Software Lifecycle)~~ — ✅ v2.0, April 29, 2026. Closed: #103, #104, #105. Architectural absorption: A1 (drop "System Developer" / "IT Department Personnel" non-roles; map to 1.07 anchors), A2 (ESPs exit §3, become AID contract-enforcement obligation), A3 (production gate single-routes to 3.09; 3.10 routing-pointer in §2 only), A4 (severity schedule by-reference to 2.09 — deduplication), A5 (acquisition-time scope only; operational EOL routes to 2.09; legacy §6.8 deleted), A6 (IP exception path by-reference to 5.01 + 1.09). C1: replaced "Hard Gate" placeholder heading and "stage gates" body language with named constructs Assessment Approval (1.13) + Technical Approval (1.10). §6.4 Applicability scope criteria added — artifact-function-based (Option A): production execution / protected data (CJI/Restricted/Confidential) / authn-authz-audit functions / ESP deliverables / shared-or-scheduled use; ad-hoc interactive admin tooling explicitly out of scope. SA-15(1) Criticality Analysis folded into §6.4 SA-11 testing plan with body cite (rigor-proportional language). Pre-prod data tightened: explicit prohibition on CJI/Restricted absent production-equivalent baseline (CG-7 accepted). All §6 directives role-anchored (§6.5 flaw remediation + production-acceptance to Sysadmin per 2.09 operator-owned pattern; §6.6 to Sysadmin; §6.8 IP property statements converted to IT Director ensure-clauses). Three R-rounds; ChatGPT R2 was textbook Pattern #14 (entire response stale-draft re-push of R1 findings already fixed); Gemini R2 produced three real residual orphans absorbed in R3. Final commit `7dc9aa9c`. | 3 (#103, #104, #105) | Lowest dependency; natural Ch2 closer |

> ## ◆ RECALCULATE SEQUENCE HERE ◆ — Completed April 29, 2026
>
> **Recalc executed April 29, 2026** (commits `951a04c2` plan, `bf2a21ed` README; resolved #462). Five-step recalc protocol completed:
>
> 1. **Architectural roots check** — Active sweep roots refreshed: #208, #211, #235, #245, #264, #6, plus newly-promoted #467, #468, #469. Active-root tickets with tracked children: #375, #456. Phase-deferred: #353, #355, #464. #291 confirmed closed (April 26).
> 2. **Ch3 ripple status** — Reduced from 11 (April 25) to 7 active: #309, #314, #377, #413, #450, #451, #452. Resolution decision (batch / defer / absorb) still pending in §7.
> 3. **Ch5/Ch6 per-policy ticket counts refreshed** — §5 inventory reconciled against open-ticket ground truth (62 open issues verified). Drift corrections: 3.05 T+→T, 3.08 T→T+#461, 4.01 +#457, 4.04 T→T+#460, 4.05 T→T+#458/#460, 6.02 +#459, 6.04 closed.
> 4. **5.07 feeder chain verified** — 1.09 (T v2.1, clean), 5.01 (T+ v1.1, 3 tickets), 3.16 (T+ v2.0, #452 ripple). Ch5 portion (5.02–5.06) is the actual blocker, all D-state, sequence intact.
> 5. **Phase 5 ripples vs. Ch5/Ch6 ordering** — None of #449/#450/#451/#452/#453/#466 affects Phase 6 entry sequence. Sequence intact.
>
> **Outcome — Phase 5D inserted before Phase 6.** Manual-wide sweep roots #463 (folded under #245), #467, #468 are deterministically caught by post-April-28 tightening protocol (verified against entries 37/38/39). One-time sweep against existing T-state corpus is permanent — no regression risk on D-state Ch5/Ch6 or future ripple work. #469 retained as absorbed-by-tightening (per-occurrence judgment, not mechanical). Ch4-pair #460 separately scoped. Phase 5D blocks Phase 6 entry; sequencing detail below.

---

### Phase 5D — Pre-Phase-6 Cleanup (locked April 29, 2026)

**Purpose:** Clear deck of mechanical 1.04-compliance defects against the T-state corpus and resolve the one open Ch4-pair logic seam before Phase 6 opens. Each session is a discrete unit; failure of one does not block the others, but all three must complete before Phase 6 entry 40.

**Sequence:**

| Session | Targets | Mode | Estimate |
|---|---|---|---|
| 5D.1 — Sweep ✅ | ~~#467~~ resolved (233 fixes/48 files); ~~#468~~ resolved (10 fixes/6 policies); #463 deferred (substantive 3.01/3.02 SLA-semantics session, see note below) | ✅ April 29, 2026 (1 session) | — |
| 5D.2 — Ch4-Pair ✅ | ~~#460~~ resolved (4.04 §6.6 ↔ 4.05 §6.1 false-positive disposition seam) | ✅ April 29, 2026 (1 session) | — |

**Pre-flight items required before 5D.1 opens:**

1. **Version-bump ruling for sweep edits.** Mechanical 1.04-compliance corrections against already-tightened policies — patch bump (e.g., 2.10 v2.3 → v2.4), new effective date, or absorbed without version change? IT Director call.
2. **Cross-validator scope for sweep work.** Full R1/R2/R3, single R1 mechanical-correctness check, or none (deterministic patterns)? Recommend single R1 mechanical-correctness round.
3. **Commit granularity.** One file per commit, one chapter per commit, or one mega-commit? Recommend one chapter per commit for audit-trail clarity.
4. **Validator script presence.** #467 references `colon_sweep.py`; #468 references "clarifier-tag-blending validator script". Confirm these exist in repo or address absence before sweep opens.

**Verification evidence supporting one-time-sweep claim:**

- Entries 37 (2.10 v2.3), 38 (2.14 v2.0), 39 (2.15 v2.0) — all tightened after #467/#468 filing date (April 28) — verified clean for §3 trailing-colon and §6 clarifier-tag patterns. Protocol absorbed both checks.
- Entries 37/38/39 verified clean for `business hour` (#463 / #245-child) — protocol catches via 1.04 §6.9 prohibited-language audit.
- D-state Ch5/Ch6 policies will emerge clean from their own future tightening; no latent regression mechanism.

**Sequence enforcement:** Phase 6 entry 40 (5.02 Internal Audits) does not open until 5D.1 and 5D.2 are both committed and corresponding tickets closed.

---

### Phase 5D.1 Completion Note (April 29, 2026)

5D.1 closed in a single session. Three sweep tickets were in pre-flight scope: **#467 (resolved), #468 (resolved), #463 (deferred)**.

**#467 outcome.** 233 §3 trailing-colon fixes across 48 files. Sweep extended past the ticket's reported 36-policy / ~178-title scope: my locator (`sweep_467.py`) found 14 additional T-state policies (1.02, 1.03, 1.08, 1.09, 3.02, 3.08, 3.10–3.12, 3.13, 3.14, 3.16, 3.17, 4.04) plus more defects per policy than the manual sweep had counted. All absorbed into the same 5D.1 sweep. 1.04 carve-out (2 defects, constitutional lock) preserved per ticket text; 5.02 carve-out (4 defects, D-state) tracked as #473 for Phase 6 entry 40 absorption.

**#468 outcome.** 10 §6 governed-clarifier-tag-blending fixes across 6 policies. Per-defect dispositions: 7 Strip (single-line label rewrite) + 3 Promote (structural — split parent into topic + governed-tag sub-bullet, matching 2.09 v2.0 reference). Cross-validator review post-commit per IT Director ruling; validator brief produced as session deliverable.

**#463 deferral.** Locator surfaced 17 occurrences (vs. ticket's 15) across 3.01, 3.02, 3.05, 3.06. Replacement is **not** mechanical — changing "business hour(s)" to either continuous-hour or end-of-business-day form materially changes SLA timer semantics. 3.01 contains the manual-wide *definition* of "business hours" as a unit; 3.02 inherits it via pipeline reference. **Recommendation: handle as a substantive maintenance pass against 3.01 (primary) with 3.02/3.05/3.06 absorbing reciprocally.** The architectural question — should the manual standardize on a business-hours clock or a continuous-hours clock for SLA cadences? — is an IT Director decision, not a sweep edit. Open standalone or inserted into Phase 6 sequencing as appropriate.

**Pre-flight rulings (April 29, 2026):**
1. Patch version bump per touched file with `Effective: April 29, 2026` stamp — applied across all 48 files.
2. No cross-validator pass for the mechanical work — applied. (#468 changes go to validators post-commit.)
3. One chapter per commit — 5 commits: `8d9bb625` (Ch1), `e805602a` (Ch2), `d88efe9b` (Ch3), `da3e8d36` (Ch4), `c508bc1d` (Ch5).
4. Validator scripts on Claude side — `sweep_467.py`, `sweep_468.py`, `sweep_463.py`, `apply_5d1.py`, `commit_chapters.py` retained in working tree. Not committed to repo (session ephemera).

**Standing decline patterns (§4):** No new patterns surfaced. None of the existing 30 active patterns triggered (the 5D.1 mechanical sweep is below the conceptual layer where validator pushback usually appears).

**Sequence:** Phase 5D.2 closed April 29, 2026 (see completion note below). Phase 6 entry 40 (5.02 Internal Audits) is next.

---

### Phase 5D.2 Completion Note (April 29, 2026)

5D.2 closed in a single session. **#460 resolved** at 4.04 v2.4 (commit `6c3fcef2`) and 4.05 v2.4 (commit `dcdbb6e9`).

**Adjudication: Option A.** The recovery-gate seam between 4.04 §6.6 (producing) and 4.05 §6.1 (consuming) was resolved by introducing a second valid recovery-gate credential — *destructive false-positive recovery authorization* — alongside the existing *eradication-complete determination*. Destructive-FP rebuild remains under IC-controlled 4.05 recovery; the gate accepts either credential.

**Edits applied:**
- 4.04 §6.6 paragraph 2: rewritten to require IC documentation of the new authorization (FP determination, original-action justification, actions performed, affected systems) in the work order Notes; authorization included in 4.07 postmortem.
- 4.05 §6.1: bridging sentence inserted before recovery gate establishing the new authorization as alternate handoff state in lieu of an eradication-complete determination and associated verification documentation.
- 4.05 §6.1: gate sentence revised to accept either credential.
- 4.05 §4: forbidden-practice entry revised to mirror the dual-credential gate.

**Housekeeping (folded into 4.05 v2.4):** Two adjacent-section defects surfaced by validator round, single-line each, validator-confirmed independently:
- 4.05 §1: cross-reference correction — "Section 6.6 governs the data and system classification framework for recovery" → "Section 6.2..." (§6.6 is Operational Handback; classification framework is at §6.2).
- 4.05 §6.5: sentence-break repair after Policy 3.08 reference (period inserted, "the" → "The").

**Cross-validator round disposition:** Both validators (ChatGPT, Gemini) reviewed the draft. Neither flagged a defect in the destructive-FP fix itself. Drift into adjacent sections produced standard validator findings; adjudicated as follows:
- ChatGPT "fatal CJI loophole" (§6.2 audit-records language) — declined as logic error (necessary vs. sufficient condition reading).
- ChatGPT "responsible for is prohibited" (4.04 §3 IT Director, 4.05 §2 Scope) — **declined permanently.** Misapplied prohibition. The "personal responsibility / shall not transfer to a designee" construct in 4.04 §3 is the deliberate non-transfer architecture from 1.07 IC role discipline, validated across 1.10/1.11/1.13/1.14. 4.05 §2 Scope's "responsible for maintaining" is boundary description, not a directive subject to shall-verb construct rules. New standing decline pattern (§4 candidate).
- ChatGPT "3.15 BIA dependency gate" — declined as process noise.
- Gemini credential-rollback proposal — declined as substantive scope expansion beyond #460.
- Gemini IC-eligibility narrowing (optional) — declined as out of scope.
- Gemini §1 cross-reference defect — folded as housekeeping (real publication blocker).
- Gemini §6.5 sentence-break defect — folded as housekeeping (real structural defect).

**Tickets filed:**
- **#477 (ripple, 4.01/4.05/4.07):** Descriptive references to "eradication-complete determination" in 4.05 §2 In-Scope/Out-of-Scope, 4.01, and 4.07 §2 Scope need acknowledgment of the dual credential. Strip-at-next-touch; not a publication blocker.
- **#478 (forward-look, 4.07/3.14):** Integrated postmortem rule for cases where 3.14 emergency project is invoked alongside 4.07 incident postmortem on a single destructive-FP event. Hypothetical until 3.14 invocation pattern surfaces in practice.

**Standing decline pattern surfaced:** ChatGPT's "responsible for" prohibition flag (applied to 4.04 §3 non-transfer construct and 4.05 §2 Scope boundary description). To be added to §4 in a separate edit. Pattern: validator flags "responsible for" as prohibited terminology where it appears in legitimate non-transfer constructs (paired with "shall not transfer to a designee") or in Scope statements describing population boundaries.

---

### Phase 6 — Chapter 5 Compliance (provisional)

**Goal:** Tighten the audit, enforcement, and compliance monitoring layer. 5.07 last because it consumes outputs from every other Ch5 policy.

| Seq | Policy | Tickets | Rationale |
|---|---|---|---|
| 40 | 5.02 (Internal Audits) | ✅ Closed v2.0 (`3da57572`, April 29) | Produces audit findings that feed 5.03 CAPs |
| 41 | 5.01 (Implementation, Enforcement, Legal — re-tightening) | ✅ Closed v2.0 (`f453669d`, April 30) | OMI clause + exception discipline + CJI explicit-negative + LRDA fixes; pulled forward per IT Director option (a) so OMI propagates transitively to 5.03–5.07 |
| 42 | 5.03 (Compliance Monitoring) | ✅ Closed v2.0 (`2373f03d`, April 30) | CAP lifecycle; #279 split-architecture applied; OMI inheritance transitive through 5.01 §6.6 by-reference |
| 43 | 5.04 (Performance Metrics) | ✅ Closed v2.0 (`266e9ab3`, May 01) | KPI data feeds 5.07 |
| 44 | 5.05 (Security Control Assessment) | 1 | Control assessment results feed 5.07 |
| 45 | 5.06 (Vendor Compliance) | 1 | Consumes 1.13 (tightened in Phase 5A); feeds 5.07 |
| 46 | 5.07 (Annual Policy Review) | 3 | Capstone — consumes 5.02–5.06, 3.16, 1.09, 1.05 outputs |

---

### Phase 6 Entry 40 Completion Note (April 29, 2026)

**Policy 5.02 (Internal Audits, Self-Assessment, and Control Testing) D v1.0 → T v2.0** (commit `3da57572`).

**Tickets closed:** #184 (retention trigger), #185 (ASR deadline), #186 (LRDA citation add), #278 (self-assessment role split), #473 (§3 trailing-colon carve-out from 5D.1).

**Substantive transitions:**
- §3 split-architecture: Sys Admin / Net Admin / Support Specialist receive self-assessment execution; AITD coordinates the cycle and consolidates results.
- §4 stripped to clean by-reference (5.01-only routing for Assessment, Enforcement, Exceptions); "Oral exceptions are not valid" added per 1.04 §6.6 constitutional mandate.
- §5 References reconciled against 1.04 §6.7 body-cite test; Cited References vs. Framework Alignment split corrected (CJIS CA-1/CA-2 base/CA-7 base, CSF ID.IM-01/02, NIST SP CA-2/CA-7 moved to Framework Alignment).
- §6 substantive tightening: risk-tier nomenclature aligned to 1.09 vocabulary; pipeline timing fix (§6.5 deficiency routing → next business day, preserving 5.03's full 10-BD CAP development window); Annual Audit Summary Report 30-day post-fiscal-year deadline (60-day buffer for 5.07's 90-day output deadline); §6.6 retention restructured per 1.11 v2.5 §6.9 pattern with NRS/NAC/LRDA/Legal Holds/Multiple Schedules bullets.
- R2 cross-validator hardening: subjective term elimination (sufficient → objective; impractical → independence-test anchor; materially/routinely → access-rights mapping); CJIS reportable routing expanded (4.02 + 4.06 as applicable); self-assessment-only restrictions extended to open CAPs and IT Director designation.

**Deferred to entry 41 (5.01):** Oversight Mechanism Integrity clause for §6.6 — adopted as general principle (oversight mechanism's *application to its targets* is not waivable; cadence/scope/methodology details remain waivable through standard framework). Naming locked at "Oversight Mechanism Integrity," scoped to 5.01 §6.6 only, no manual-wide propagation. Inherited transitively by 5.03–5.07 through by-reference architecture; no special clause needed in those policies.

**Standing decline patterns added:** #38 (greater-of retention substitution), #39 (inline restatement of upstream policy obligations), #40 (5D.2 "responsible for" non-transfer pattern, retroactively inscribed).

**Cross-validator round summary:** R1 — ChatGPT GAP 01 (Oral exceptions) constitutional miss accepted; R2 — Robert direction on subjective-term elimination drove ChatGPT GAP 03/04 acceptance; Gemini Gap 1/4/5 refinements accepted; ChatGPT GAP 02 retention declined for third recurrence (now pattern #38).

---

### Phase 6 Entry 41 Completion Note (April 30, 2026)

**Policy 5.01 (Policy Implementation, Enforcement, and Legal Alignment) T+ v1.2 → T v2.0** (commit `f453669d`).

**Tickets closed:** #334 (§6.6 exception discipline strengthening), #345 (§6.8 acknowledgment records by-reference), #425 (§6.6 CJI Exceptions explicit-negative reframe), #479 (OMI clause carry-forward from 5.02 v2.0).

**Substantive transitions:**
- **§6.6 Oversight Mechanism Integrity (new):** locked architectural principle from #479 — where a policy establishes an oversight, audit, monitoring, assurance, or review mechanism that applies to other policies in the manual, that mechanism's application to its targets shall not be waived by exception; cadence/scope/methodology operational details remain in the standard exception path. 5.01 §6.6 only; no manual-wide propagation; downstream policies inherit transitively through by-reference architecture.
- **§6.6 Written Documentation (consolidated):** remediation timeline (semantic upgrade from "proposed duration"); affirmative compensating measures or written justification for none; explicit bar on open-ended exceptions (consolidated from former Duration and Review clause); CJIS substantive-compliance backstop sentence (parallel to 1.09 §6.8 RAM-Prohibition for the policy-exception deviation channel).
- **§6.6 CJI Exceptions (reframed):** explicit-negative on CSO concurrence at policy-framework level per April 23 #425 reframing; CSO concurrence operationally required only where specific CJIS Security Policy control or written CJIS user agreement so requires (named examples: IR-6 Part (b), PS-3, AC-7); instrument-neutral CJIS user agreement language; reordered before Policy-Specific Requirements.
- **§6.6 Active Exception Review (renamed):** former Duration and Review; open-ended bar moved to Written Documentation; clause focuses on annual review obligation only.
- **§6.8 IT-Administrative Enforcement Records (renamed and restructured):** former Corrective Action Records (renamed to disambiguate from 5.03 CAP Lifecycle); population-class LRDA mapping (LRDA 20070321 Master Personnel File for County employees; LRDA 20121869 Administrative Hearing Files for appointed and elected officials; LRDA 20071300 Vendor Performance Case Files for contractors and vendors).
- **§6.8 Sanctions Documentation:** HR custodianship explicit; LRDA 20070321 anchor (formal HR-track sanctions process is employee-only by construction; non-employee enforcement records land in IT-Administrative Enforcement Records).
- **§6.8 Acknowledgment Records:** by-reference to originating policy via applicable LRDA series (replaces unsupported 7-year retention figure; 2.01 v2.6 §3 LRDA 20071725 anchor at 3 calendar years aligns with CJIS AT-4(b) 3-year minimum).
- **§6.5 CJIS notification recipients:** added "personnel with account management responsibilities" — closes CJIS v6.0 PS-8(b) alignment gap.
- **§6.4 Emergency Protective Action:** hard one-hour notification lock (replaces unbounded "immediately"); named-authority next-steps determination ("County Manager, in coordination with Human Resources and the District Attorney's Office"); formal-language replacement for "evidence of a bad act"; "basis" in place of "reasoning".
- **§3 universal label:** "All County Personnel and Contractors" → "All County Personnel" (manual-wide convention per standing decline #32).
- **§6.3 lead:** "the right to take" → "extends to taking" (policy-grade verb).
- **§5 Cited References ripple:** added CJIS AC-7, IR-6, PS-3 (body-cite from §6.6 CJI Exceptions); added LRDA 20070321, 20071300, 20121869 (body-cite from §6.8 population-class architecture).

**Cross-validator round summary:** R1 — five accepts (C7 rename, D1 instrument-neutral, D7 verb form, D5(b) PS-8 fourth role, R1 G3 named authority + D4 1-hour lock + C5 formal language + D8 reasoning→basis); seven declines (G1 §5 flat list, C1 enumerated non-waivable list, C2 OMI cadence/scope/methodology constraint, C3 §6.3 catch-all narrowing, C4 CJI verification gate, C6 1.05 placement misroute, D3 retention floor restoration). R2 — one accept (C5-R2 population-class LRDA architecture); R1 repeats from both validators reflexively declined (no new substance). R3 declined by IT Director — diminishing returns evident from R2 verbatim repeats.

**Standing decline patterns added:** none inscribed this session. Watch-list (2 rounds; need 3+ for promotion): ChatGPT enumerated non-waivable list; ChatGPT OMI cadence/scope/methodology constraint; ChatGPT §6.3 catch-all narrowing (institutional-founding-adjacent); ChatGPT CJI verification gate (Pattern #23 territory); Gemini "appropriate" → "designated" ISO substitution.

**Open ripples filed:** none.

---

### Phase 6 Entry 42 Completion Note (April 30, 2026)

**Policy 5.03 (Compliance Monitoring and Corrective Action) D v1.0 → T v2.0** (commit `2373f03d`).

**Tickets closed:** #187 (upstream routing verification: 1.09 post-POA&M→CAP), #279 (GLOBAL-G role redistribution split: domain admin drafts technical content; AID coordinates/integrates/submits within 10 BD).

**Substantive transitions:**
- §3 split-architecture per #279: Systems Administrator / Network Administrator / Support Specialist draft CAP technical content (root cause, remediation actions, milestones) for deficiencies in their respective operational domains and provide drafts to AID; Assistant IT Director coordinates the cycle, reviews drafts for completeness, adds Risk Register linkage, confirms CJIS impact indicator, and submits completed CAPs to IT Director for approval. The 10 business day development window covers the full chain unchanged. Role names match 1.07 §6.2 canonical labels.
- §3 IT Director: 1.08 exception bullet removed (5.01 §6.6 owns exception management manual-wide; standing decline #6).
- §4 restructured to 5.02 v2.0 by-reference pattern: 5.01 lead-in with first-use title; Assessment routes to 5.02 + 5.07; Enforcement clean by-reference 5.01; Exceptions clean by-reference 5.01 + retained "Oral exceptions are not valid" per 1.04 §6.6 constitutional mandate. Stripped open-ended-basis sentence (now consolidated in 5.01 v2.0 §6.6 Written Documentation).
- §5 References body-cite split per 1.04 §6.7: added 1.07 (body-cited §6.2 Responsible Role), NAC 239.165 (body-cited §6.6), LRDA 20071256 (body-cited §6.6), NRS 239 (subject acknowledgment per 5.02 v2.0 precedent); removed 1.08 (no longer body-cited after §3/§4 fixes); moved CJIS CA-7, NIST SP CA-7/PM-4, CSF ID.IM-01/-03 to Framework Alignment per body-cite test. Cited ordering ECIO → NRS/NAC/LRDA → CJIS → NIST SP. Framework ordering CJIS → CSF → NIST SP → COBIT → ITIL.
- §6.X-strip per Rule #1 / Root #375: 5 cross-policy section-depth violations stripped (5.02 §6.5 references and 3.02 §6.3/§6.4 references); 8 internal self-references retained per Rule #1 in-document scope.
- §6.2 lead reflects #279 split (10-BD window unchanged); CJIS Impact Indicator content bullet stripped of duplicative directive (single source of truth in §3 IT Director); descriptive line + §3 pointer retained. Milestones bullet converted to bold-label topic-block + 3 atomic sub-bullets per 1.04 §6.8 Clarification + §6.12.
- §6.4: passive "shall not be closed" recast to role-anchored positive form ("AID shall close a CAP only upon documented verification...").
- §6.5: NRS 603A.220 monitoring criterion timing delegated to 4.06 (which operationalizes the statute with measurable 24h/48h/5BD windows) replacing imprecise R1 phrasing "within the timeframes mandated by that statute" — NRS 603A.220 mandates a standard (expedient/unreasonable-delay), not fixed timeframes. Annual cadence retained per Q3 lock.
- §6.6 retention: full restructure to 5.02 v2.0 / 1.11 §6.9 canonical pattern. Quality Assurance Review Audits and Reports bullet (LRDA 20071256, three-year minimum from end of calendar year), CJIS-Affecting Records (greater-of CJIS/Nevada), Destruction Standards (NAC 239.165), Legal Holds (1.11 by-reference), Multiple Schedules (longest applicable). Single-line bare NRS 239 subject acknowledgment per 5.02 v2.0 precedent.
- 1.04 §6.5 atomic-bullet compliance: §3 obligation count grew 16 → 24 single-`shall` bullets via decomposition of three compounds (AID review/add/confirm/submit; AID monthly review + update milestone status; SysAdmin/NetAdmin/SupportSpec draft + provide).
- 1.04 §6.10 quantity syntax: "two (2) functions" padded.
- Root #6 (Redmine product-name removal) absorbed: 6 occurrences stripped manual-wide.

**OMI inheritance:** Transitive through 5.01 v2.0 §6.6 by-reference per Phase 6 Entry 41 closure decision; no inline OMI clause needed in 5.03.

**Cross-validator round summary:**
- **R1** — Gemini Gap 1 (chained §3 obligations) full accept (1.04 §6.5 constitutional); Gemini Gap 2 (chained §6 directives) partial accept (§6.2 CJIS Impact Indicator Itemize bullet via dual-maintenance strip; Milestones Itemize via topic-block conversion; §6.3/§6.4/§6.5 prose declined per §6.8 Clarification scope limit to bulleted/numbered items); Gemini Gap 3 (quantity syntax) partial accept ("two (2) functions" padded; "one or more" declined per peer convention 5.02/5.01 v2.0 retain bare for indefinite quantifiers); ChatGPT Gap 1 (inline §4 non-waivable list + 1.08) reflexive multi-pattern decline (#6+#20+#36+#37+#39); ChatGPT Gap 2 (§6.2 one-directive) accept (overlap with Gemini); ChatGPT event-driven trigger declined per Q3 lock; version-control note pre-empted by phase-10 root #353; NRS 603A.220 verification disclosure handled per pattern #22.
- **R2** — Gemini Gap 1 prose-paragraph §6.8 application re-push declined (2nd round, watch-list); Gemini Gap 2 "one or more" padding re-push declined (2nd round, watch-list); ChatGPT Gap 1 inline-§4 non-waivable list re-push reflexive decline (2nd round, surface framing rotated R1 5-item → R2 8-item; watch-list for §23 promotion at R3); ChatGPT Gap 2 §5 flat-list reordering reflexive decline #1 (proposed reordering would intermix Cited and Framework on same CJIS line); ChatGPT NRS 603A.220 phrasing partial accept (delegating fix to Policy 4.06 instead of inline statutory restatement); event-driven trigger re-push declined per Q3 (2nd round, watch-list); uniform topic-block treatment declined (style preference, no compliance gap).
- R3 declined per diminishing returns from R2 verbatim/refined repeats.

**Standing decline patterns added:** None inscribed this session. Watch-list (2 rounds; need 3+ for promotion):
- Gemini prose-paragraph §6.8 application — wants atomic-bullet rule extended to Standard prose narrative.
- Gemini "one or more" §6.10 padding — wants padding on indefinite quantifiers; 5.02/5.01 peer convention is bare.
- ChatGPT §4 inline non-waivable list — already protected by #20/#36/#37/#39 stack; consolidated promotion candidate at R3 if list expands again.

**Open ripples filed:** None. All upstream routings verified intact; downstream consumers (5.04, 5.07) absorb 5.03 v2.0 references in their respective tightening sessions.

---

### Phase 6 Entry 43 Completion Note (May 1, 2026)

**Policy 5.04 (Performance Metrics and Operational KPIs) D v1.0 → T v2.0** (commit `266e9ab3`).

**Tickets closed:** #280 (GLOBAL-G role redistribution: §3 expansion + AID rewrite to validate-and-consolidate).

**Substantive transitions:**
- §3 GLOBAL-G expansion per #280: Systems Administrator / Network Administrator / Support Specialist trifecta added with KPI data preparation obligations sourced from each role's operational area as defined in Policy 1.07 (first-use parenthetical on Sys Admin; subsequent short-form on Net Admin / Support Specialist). AID rewritten from prepare-from-scratch to validate-and-consolidate role: validates domain inputs for completeness/integrity/consistency with KPI register; performs cross-domain trend analysis; consolidates validated inputs into Quarterly KPI Review Summary. Trifecta pattern matches 5.02 v2.0 entry 40 GLOBAL-G implementation and 3.02 v2.6 service-management role split.
- §3 #467 colon absorption (parallel to 5.02 v2.0 #473): all 6 role headers (IT Director / AID / Sys Admin / Net Admin / Support Specialist / All Information Operations Personnel) converted from pre-#467 colon-outside-bold form to canonical post-#467 colon-inside-bold form. D-state policy carrying pre-sweep defects absorbed during this entry's tightening pass.
- §5 PR.AT-03 hallucination → GV.OV-03 + ID.IM-01: PR.AT-03 verified non-existent in CSF 2.0 PDF (PR.AT has only -01 and -02). Replaced with GV.OV-03 (Performance Evaluated and Reviewed) matching 3.02 v2.6 manual-wide pattern; added ID.IM-01 (Improvements Identified from Evaluations) per 3.02/3.16/5.02/5.03/5.07 measure-then-route convention.
- §6.9 retention restructure to 5.02 v2.0 / 1.11 §6.9 canonical bulleted pattern: opening prose anchored to AID (Quarterly KPI Review Summary as authoritative; AID applies retention periods per NRS 239.125; AID classifies records per 1.11). Bullets: Quarterly KPI Governance Records (3yr local minimum, LRDA 20071558 nonannual floor 2yr), Annual KPI Performance Summaries (permanent per LRDA 20071558 annual activity reports — verified vs Reference/07_Nevada_Log_Retention.pdf), Destruction Standards (NAC 239.165), Legal Holds (1.11 by-reference), Multiple Schedules (longest applicable). Annual permanent-retention split surfaced by ChatGPT R1 LRDA verification.
- §6 cross-policy §6.X depth strip per #375 / Q5 ruling: 4 occurrences (§6.2 Vendor Performance Policy 3.02 §6.5; §6.4 Data Sourcing Policy 3.02 §6.4 + Policy 3.14 §6.8; §6.8 Executive Reporting Policy 1.14 §6.2). Intra-policy `Section 6.6` self-reference in §3 retained per 1.04 §6.11 explicit permission.
- (Redmine) product-name strip per #6 / Q4 ruling: 4 occurrences in §3 AID + §6.3 + §6.5 + §6.9.
- §6.7 Organizational Health privacy boundary tightened per validator R1 CG5 + GEM2: dropped "primarily" softener, added hard data-exclusion list (named employee performance ratings / disciplinary facts / medical information / HR-confidential details), declarative scope statement ("This policy is not an employee ranking or disciplinary scorecard"), AID-anchored aggregate presentation, IT-Director-anchored personnel-action routing.
- §6.6 single-period escalation rationale documentation per validator R1 CG3: IT Director discretionary (b) escalation requires documenting the determination in Quarterly KPI Review Summary with affected KPI / service or control domain / operational impact / security or compliance impact / reason immediate tracked improvement is required.
- §6.3 KPI register expanded per validator R1 CG6: added 7 audit-traceability fields (approving authority, approval date, effective date, retired date where applicable, data owner, source-system owner, known data-quality limitations).
- §6.2 Security and Control Health domain per validator R1 CG4: replaced unaudit-able "applicable Chapter 2 policies" with KPI-register-defers pattern matching §6.4 Data Sourcing logic.
- §6.2 + §6.4 + §6.6 + §6.7 passive-voice / orphan-directive fixes per validator R1 GEM2 + R2 Gap 1: anchored "The Department" → AID; "The KPI register shall remain" → AID; "All KPI data shall be sourced" → All Information Operations Personnel; "shall be incorporated" → AID; "shall be documented and monitored" → AID; "Recurring Ticket Ratio... shall be reviewed" → AID; "Retention periods shall be applied" → AID; "shall be classified" → AID; "shall be reviewed primarily in aggregate" → AID; "Individual personnel actions shall be handled" → IT Director.
- §4 Enforcement cleanup per validator R1 GEM3: stripped redundant routing sentence (3.16/5.03 routing already governed by §6.6 Routing bullet) and parallel-pipelines prohibition (already governed by §6.6 declarative "This policy does not create a separate remediation tracker"). Final §4 minimal by-reference: consequence sentence + 5.01 first-use parenthetical.
- §5 Cited References body-cite split per 1.04 §6.7: added 1.11 (body-cited §6.9 classification + Legal Holds) and NAC 239.165 (body-cited §6.9 Destruction Standards). Final §5: 16 ECIO policies (1.07 / 1.10 / 1.11 / 1.12 / 1.14 / 3.01 / 3.02 / 3.11 / 3.12 / 3.14 / 3.16 / 5.01 / 5.02 / 5.03 / 5.06 / 5.07) + NRS 239.125 + NAC 239.165 + LRDA 20071558. Framework Alignment: CSF GV.OV-03 + ID.IM-01, NIST SP CA-7 + PM-6, COBIT MEA01, ITIL Continual Improvement + Measurement and Reporting. Body-cite test 16:16 verified clean.
- 1.04 §6.10 product-name prohibition + §6.11 cross-reference syntax + §6.7 Cited/Framework split all clean.
- Confirmed-correct standing-decline cite stack held against ChatGPT inline-exception re-push (#20 + #29 + #14) and Gemini retention-bound re-push (canonical 1.11/5.02/5.03 pattern; NRS 239 permits longer-than-LRDA retention without formal variance).

**Cross-validator round summary:**
- **R1** — ChatGPT CG1 (LRDA annual-permanent split) accept; ChatGPT CG2 (inline open-ended exceptions) reflexive decline #20 + #14 + #29; ChatGPT CG3 (single-period escalation rationale) accept; ChatGPT CG4 (specify Chapter 2 source) accept; ChatGPT CG5 (privacy boundary) accept modified (no inline approval clause per #20 spirit); ChatGPT CG6 (7 register fields) accept all. Gemini GEM1 (terminal periods §6.1) accept; Gemini GEM2 (passive voice / orphans, 7 occurrences) accept all with role anchors; Gemini GEM3 (procedural in §4) accept (strip redundant routing + parallel-pipelines).
- **R2** — Gemini Gap 1.1/1.2/1.3 (residual passive forms) accept all (anchored to AID); Gemini Gap 2 partial accept (remove explanatory "exceeds" sentence; decline "minimum of" removal — canonical Ch5/1.11 form; decline explicit destruction trigger — canonical pattern uses Multiple Schedules + Legal Holds + Destruction Standards as bounded envelope; legal claim "stricter variance required" factually incorrect). ChatGPT primary (re-push of inline open-ended exceptions, R2 surface framing "consistency with similar policies") reflexive decline #20 + #14 + #29 (2nd round, pattern #23 candidate); ChatGPT optional (anti-shadow-tracking) decline (existing positive form sufficient + inline approval clause = pattern #20 risk + partial self-contradiction with R1 redundancy reasoning).
- **R3** — Gemini single residual (re-push of "minimum of" removal, R3 surface framing "e-discovery footprint risk / litigation in year 6") decline (2nd round; canonical pattern preserved; concern folded into RP1 #480 Phase 9 evaluation scope per IT Director option-1 ruling). ChatGPT required edit (3rd round of inline open-ended exceptions, R3 surface framing "remediation timeline and compensating measures specificity") **pattern #23 promotion confirmed → standing decline pattern #41 inscribed**. ChatGPT optional (2nd round of anti-shadow-tracking, R3 surface framing "audit disputes over unofficial metric sources") watch-list for 3rd round. ChatGPT publication-sync observation (master PDF metadata) acknowledged — administrative, resolves at Phase 10 master regen; no draft action.

**Standing decline patterns added:** #41 (ChatGPT 3-round inline open-ended-exception re-push under rotated surface framings R1/R2/R3 — inscribed at 5.04 v2.0 commit `266e9ab3`).

**Watch-list (2 rounds; need 3+ for promotion):**
- ChatGPT anti-shadow-tracking inline prohibition with inline approval clause (R2 + R3 surface framings rotated; one more round triggers pattern #23 promotion).
- Gemini "minimum of" removal / explicit destruction trigger (R2 + R3 surface framings rotated; resolution direction is RP1 #480 Phase 9 manual-wide evaluation, not 5.04-only fix).

**Open ripples filed:** #480 (RP1 retention block architectural uniformity — manual-wide three-pattern landscape; Phase 9 candidate); #481 (RP3 manual-wide open-ended-exception inline drift in 9 tightened policies; sweep candidate; stripping defangs pattern #41 stale-source argument); #482 (RP4 retention opening prose active-voice anchor for 1.11 §6.9 + 5.02 §6.6 + 5.03 §6.6; may fold into #480 at Phase 9).

---

### Phase 7 — Chapter 6 Appendices (provisional)

**Goal:** Complete 6.01 Glossary at content level. Establish skeleton-only scaffolding for 6.02, 6.03, and 6.04 — the content for these three appendices is populated in Phase 9 (6.02, 6.03 from matrix outputs) or Phase 10 (6.04 from declaration). Completing 6.02/6.03 content at Phase 7 is prohibited; the N-wise analysis required to populate them correctly runs only in Phase 9.

| Seq | Policy | Tickets | Rationale |
|---|---|---|---|
| 47 | 6.01 (Glossary) | 3 | Content-complete at Phase 7. Term harvest from all tightened policies. |
| 48 | 6.02 (Policy Matrix) | 3 | **Skeleton only at Phase 7.** LyX scaffolding, headers, cross-reference machinery. Content populated in Phase 9 from aggregate-audit outputs. |
| 49 | 6.03 (STAK Matrix) | 3 | **Skeleton only at Phase 7.** LyX scaffolding only. NICE/SFIA alignment against 1.07 tightened tiers verified in Phase 9; content populated from Phase 9 role and construct outputs. |
| 50 | 6.04 (Revision History) | 1 | **Skeleton only at Phase 7.** Entry format established. First entry ("v1.0 — Initial publication — July 01, 2026") written at Phase 10. |

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

Entry 50 (6.04 skeleton) completion is the trigger. "Same level" means the whole manual at T before any N-wise work begins.

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
| 9I Architectural Function Ownership | For each load-bearing governance function (sanctions framework, exception routing, sanitization authority, LRDA retention chain, LASO function, risk acceptance authority, delegation/non-delegation authority, and others enumerated during the pass), confirm exactly one policy is the canonical owner and every other invocation is a clean by-reference. Catches the framework-restatement defect class — directives surviving the per-policy tightening pass that duplicate consequences, authorities, or processes another policy already governs. | One canonical owner identified per function; every other invocation routes by reference with no inline restatement of consequences, authorities, or process steps. |

**Gate: Wave 2 complete. Appendices 6.02 and 6.03 populated from Phase 9 matrix outputs.**

#### Wave 3 — Holistic Read

| Sub-phase | Scope | Done-criterion |
|---|---|---|
| 9G Succession Walkthrough | §8 Criterion 3 five-question test, directive-by-directive, cover-to-cover. Single-threaded. | Every directive yields complete answers to the five §8 questions; identified gaps closed. |
| 9H Editorial Pass | Grammar, voice consistency, typography, compiled-PDF render, TOC accuracy, LyX cross-reference inset integrity. Runs last — editorial against still-changing content is wasted effort. | Compiled PDF renders clean; TOC accurate; all LyX insets resolve; no prohibited-language hits per 1.04 §6.9. |

**Phase 9 complete when:** all sub-phases resolved; 6.02 and 6.03 populated; compiled PDF renders clean.

**Scaffolding artifacts produced during Phase 9 (die with repo):**

- Phase 9 finding tickets (labels `phase-9a` through `phase-9i`).
- `Phase9/` folder in repo root: citation consistency matrix, construct registry, role obligation matrices, framework coverage matrices, pipeline traversal reports, succession walkthrough gap report, editorial findings log.

**Persistent outputs (live in LyX / compiled manual):**

- Policy body text corrections.
- 6.02 Policy Matrix populated content.
- 6.03 STAK Matrix populated content.
- Glossary additions (6.01) from construct registry.

**v1.0 Criteria mapping.**

- Criterion 1 (Internal Consistency) — satisfied by 9A, 9B, 9C, 9F, 9H, 9I.
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
- **Ch3 ripple batch (current count 7: #309, #314, #377, #413, #450, #451, #452)** — batch session, defer to v1.0 validation, or absorb opportunistically? Decision pending. April 29, 2026 reconciliation: count reduced from 11 (April 25) via #308/#316/#319/#322 closure and #313→#450, #317→#451, #318→#452 re-filing. Adjacent: #378 (4.06) and the new Ch4-pair #460 (4.04/4.05).
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
- **§2 Out of Scope routing pointer format (Rule #2, April 20, 2026).** Out of Scope routing pointers end at `Policy [X.XX].` — no parenthetical title, no section depth. Per 1.04 §6.4 format spec and §6.11 exception clause.

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
