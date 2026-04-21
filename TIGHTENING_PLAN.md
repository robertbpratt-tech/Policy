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
| #6 | Product-name removal (Redmine) | 1.04, 1.08, 1.14, 3.01–3.17 | Open, absorbed-by-tightening | Multi-policy Redmine sweep. #7 (Office 365) and #10 (HID DigitalPersona) closed April 19 as duplicates of per-policy children #99 and #71 respectively; #8 closed previously. |
| #353 | Set Header Date and Version to uniform `Effective: July 01, 2026 \| Version: 1.0` | Manual-wide | Open, phase-10-deferred | All policies; mechanical normalization at v1.0 declaration per Phase 10 step 3. Dormant until Phase 10 entry. |
| #355 | Manual-wide LRDA citation verification sweep (numbers, titles, retention periods, NRS 239.125/NAC 239.155 companion citations) | Manual-wide | Open, phase-9-deferred | Scoped in §7 Open Questions for Phase 9: verification half → sub-phase 9A; companion-authority consistency → sub-phase 9B. Split into `phase-9a-intake` and `phase-9b-intake` child tickets at Phase 9 entry. Dormant until then. |
| #375 | Universal §6.X-strip sweep — strip section-specific depth from cross-policy body references | Manual-wide | Open, active-root | **First wave absorbed April 20, 2026 evening:** 13 child tickets (#360–#372) resolved against tightened peers (1.03, 1.06, 1.10, 1.13, 1.14, 2.01, 2.02, 2.06, 3.09, 3.10, 3.14, 4.06, 4.07). #374 (1.04 v1.4 §2 Out of Scope parentheticals) closed — resolved in commit `57cace1b70` prior to ripple filing. **Second wave filed April 20, 2026 (late evening):** PDF-driven visual scan surfaced 130 additional §6.X cross-policy hits across 21 tightened policies. 21 child tickets filed (#402–#422) — one per affected policy. #375 itself continues tracking 1.04 v1.4 §6.15 (4 hits, deferred to dedicated 1.04 session per architectural-lock discipline). Plus #423 (1.12) and #424 (3.02) filed as intra-policy disambiguation siblings to #378 (false-positives surfaced by scan; same pattern as 4.06). Untightened (D-state) policies 5.03/5.04/5.06/5.07 (34 hits combined) and Appendix 6.01 (30 hits) absorb into respective tightening/Phase 7 sessions — no new tickets for those. Scanner-based filing retired per IT Director ruling April 20, 2026 due to regex-gap reliability; PDF-driven scan is now the authoritative second-wave methodology. Rule #1 in §4 is the authoritative statement of the underlying rule. |

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
25. **Self-generated: Clarification contextual clarifier applied to substantive directives rather than ambiguity resolutions** — Per 1.04 §6.12, the Clarification tag is specifically for "resolving a potential ambiguity in the directive's application." When Claude reaches for the Clarification tag to attach a substantive directive (e.g., a non-delegation rule, a routing pointer, a scope restriction) to a parent bullet, that is misuse — the content belongs either as a standalone directive at the same level or integrated into the parent. Clarification reads as defensive or "weaseling" when applied to non-ambiguity content. Detected when the tag is attached to a shall/shall-not/should statement rather than to a "this means X, not Y" disambiguation. (2.06 Phase 5B entry 26, Round 1 cleanup — IT Director feedback: "feels like us trying to weasel or defend." Two instances in 2.06 v2.1 draft: §6.1 non-delegation statement and §6.4 cryptographic-standards routing pointer; both removed in v2.2.) This is a Claude-side drafting discipline, not validator feedback, but captured here because the detection and re-draft mechanics are identical.
26. **ChatGPT: add Nevada retention authorities (NRS 239.125, NAC 239.155/165, LRDA) to the §5 of any policy that creates retained records** — retention authority chain is owned by 1.11 §6.9 manual-wide; policy-level §5 additions create dual-maintenance. Pointer to 1.11 §6.9 from the creating policy's body incorporates the authority chain by reference. (2.06 Phase 5B entry 26, Rounds 3/4/5, ChatGPT — three rounds, identical recommendation with varying specificity: Round 3 "PIA retention path"; Round 4 "add NRS 239.125, NAC 239.155, LRDA to §5"; Round 5 "direct references to NRS 239.125 and applicable LRDA." All three declined; PIA retention sub-bullet points to 1.11 §6.9.)
27. **ChatGPT: add HIPAA or PHI-specific legal authority when PHI is in-scope** — manual-wide pattern established in 1.11 v2.3 §6.5 uses "PHI where applicable" without HIPAA citation. Until 1.11 is changed to cite HIPAA explicitly, downstream policies match 1.11's posture. If the manual intends to cite HIPAA, change 1.11 first; downstream policies propagate automatically. (2.06 Phase 5B entry 26, Rounds 4/5, ChatGPT — Round 4 "identify governing health-privacy authority"; Round 5 "pick one of two paths: add HIPAA authority or remove PHI." Both declined; 2.06 matches 1.11 v2.3 pattern.)
28. **Gemini: specific numeric volume tiers for record counts in PIAs (<500, 500-5,000/10,000, >5,000/10,000)** — no Elko County benchmark exists for these tier boundaries; tier values shift between rounds (5,000 in Round 4, 10,000 in Round 5) demonstrating arbitrary selection. Gemini himself caveats in Round 4: "If thresholds are not currently established, state: 'Confidence low; requires manual verification.'" The current "approximate record count or estimated data volume" language is audit-testable without imposing arbitrary structure. (2.06 Phase 5B entry 26, Rounds 4/5, Gemini — two rounds, same recommendation with different tier values. Both declined.)
29. **Cross-validator pushback on locked operational-reality decisions via cross-policy dependency citation** — When a validator cites a downstream dependency in a tightened policy as reason to reverse a locked IT Director decision, the correct resolution is to file a ripple against the dependency to align with the operational decision, not to reverse the decision. Distinct from decline #14 (stale source) and #22 (absence-of-evidence): pattern #29 applies when the validator cites *accurate* source with a genuine dependency, but the locked decision renders that dependency obsolete rather than the decision wrong. The ripple flows *toward* operational truth, not *away* from it. Third-recurrence rule: when three or more rounds re-push the same target citing the same dependency, reflexive decline on sight with pointer back to the original adjudication and to the filed ripple that resolves the dependency. (2.02 Phase 5B entry 27, Rounds 1/2/3, ChatGPT — all three rounds cited 1.07 v1.3 §6.1 L1031 5-year CJI rescreening requirement as reason to reverse 2.02's event-triggered model. IT Director ruling Round 1 Path A: file ripple #354 against 1.07 to align with 2.02. Rounds 2 and 3 re-pushed identical finding with identical rationale; both declined under Pattern #29.)

30. **~~Surface-framing rotation on §2 parenthetical-title prohibition~~** [**RETRACTED April 20, 2026 — WAS WRONG**] — Originally filed as a standing decline during 2.04 Phase 5B entry 28 claiming Gemini was incorrect to flag §2 parenthetical titles. **Retraction reason:** The original decline was based on a misread of 1.04 §6.4 which specifies the routing pointer format ending at `Policy [X.XX].`; §6.11's "does not apply to Scope section routing pointers" is prohibitive, not permissive. 1.04 v1.4 §2 itself contains the same defect and requires ripple cleanup. Do NOT use this as a standing decline going forward; Gemini's finding was correct. **Related ruling captured below as Rule #1.**

### Universal Manual Rules (Confirmed April 20, 2026)

**Rule #1 — No section-specific cross-references in body prose.** Cross-references to other ECIO policies in the body of any policy use `Policy X.XX (Policy Title)` on first use within that policy and `Policy X.XX` thereafter. Section-specific depth (e.g., `§6.X`, `Section 6.X`, `§6.11`) shall NOT appear appended to cross-policy references. Rationale: readers can read the full referenced policy. Self-references within the same policy (`Section 6.X`) are NOT in scope — navigation within the current document is permitted. Confirmed by IT Director April 20, 2026. Ripples filed #360–#372 against tightened peers carrying the defect.

**Rule #1 execution status (April 20, 2026 evening):** First batch of 13 ripples (#360–#372) absorbed and closed. Remaining ~80 cross-policy §6.X hits identified by scanner v5 across 11 additional tightened policies (3.01, 3.02, 3.05, 3.06, 3.07, 3.11, 3.12, 3.13, 3.15, 3.16, 3.17). These were missed by the auto-filer that generated #360–#372 due to regex-gap in the filer's pattern. **Remediation method pivoted to PDF-driven visual scan**: IT Director will compile a fresh PDF from current source, visually identify rendered `Section 6.X` / `§6.X` occurrences attached to cross-policy references, file a ripple per hit against the owning policy, and absorb. Scanner-based ripple filing retired for this sweep category due to regex-gap reliability concerns. The `of this policy` qualifier pattern (#378) may be applied opportunistically during the PDF pass or filed as a separate disambiguation ripple.

**Rule #2 — §2 Out of Scope routing pointers end at `Policy [X.XX].`** No parenthetical title, no section depth. Per 1.04 §6.4 format spec and §6.11 exception clause. Confirmed April 20, 2026. 1.04 v1.4 §2 itself carries the defect and requires cleanup — ripple to file against 1.04 when touched.

---

## §5. Per-Policy Defect Inventory

State key: **L** = Locked, **T** = Tightened (clean), **T+** = Tightened with open ripples, **D** = Drafted/untightened, **A** = Appendix.

**Last refreshed:** April 20, 2026 post-§6.X-strip-batch (Phase 5B mid-session ripple absorption pass — 13 §6.X-strip ripples absorbed across previously-tightened peers). Preceded by: Phase 5B entry 28 complete (2.04 v2.4, April 20).

**Session log — April 20, 2026 evening (§6.X Strip Batch Absorption):**
This session was cross-cutting maintenance, not a new tightening session. Applied Universal Manual Rule #1 (no section-specific cross-references in body prose) to 13 previously-tightened policies. Per-file ripple absorption, diff-reviewed and pushed:

- **Absorbed and closed:** #360 (1.03 `d2b6c2db96`), #361 (1.06 `b323c4af8f`), #362 (1.10 `0c8ce22aa4`), #363 (1.13 `d852d950ea`), #364 (1.14 `770f985d22`), #365 (2.01 `0cdf25fc40`), #366 (2.02 `d2402716a1`), #367 (2.06 `3f74871a0b`), #368 (3.09 `df41300b71`), #369 (3.10 `5d94459a4a`), #370 (3.14 `b6ca977e64`), #371 (4.06 `c4424b71f6`), #372 (4.07 `4246b41707`). All 13 files no version-bumped (IT Director ruling: mechanical fix below version-increment threshold).
- **Pre-batch housekeeping:** #6 (GLOBAL-D Redmine) closed — 0 hits manual-wide; #374 (1.04 v1.4 §2 parenthetical-title strip) closed — resolved in commit `57cace1b70` (April 20 12:06Z "Fixed 1.04 Scope") which landed 31 minutes before the ripple auto-filed.
- **Ripples filed during session:** #375 (1.04 v1.4 §6.15 §6.X strip — 4 cross-policy hits against 3.13 and 4.03; deferred to dedicated 1.04 session per architectural-lock discipline), #376 (2.02 missing first-use parentheticals at L470 for 1.11 and L552 for 1.13), #377 (3.10 missing first-use parenthetical at L451 for 3.09), #378 (4.06 intra-policy self-reference disambiguation — 4 bare `Section 6.X` forms without `of this policy` qualifier).
- **Architectural landings:** 2.06 §6.3 at-rest/in-transit encryption blocks restructured to collapse dual `Policy 1.11 §6.4 (Confidential)` + `Policy 1.11 §6.5 (Restricted)` references into single `Policy 1.11` ref with in-prose "Confidential and Restricted data requirements defined in" clarifier (IT Director ruling during session). Opportunistic strip of wrong-placement parentheticals on subsequent uses applied where encountered (2.06 L1475 1.11 subsequent, 2.06 L1853 4.06 subsequent).
- **Scanner development:** v5 scanner iteration — v2 missed § glyph (caught in 1.03 session after only finding "Section" word-form); v3 matched auto-filer counts but over-attributed multi-ref lines; v4 added sentence-boundary filter but lost "of this policy" filter (caught in 3.09 L383 false positive); v5 restored "of this policy" filter and validated against all 8 previously-pushed files (all clean).
- **Scope discovery:** v5 scanner identified ~80 additional §6.X cross-policy hits across 11 untouched policies (3.01, 3.02, 3.05, 3.06, 3.07, 3.11, 3.12, 3.13, 3.15, 3.16, 3.17). These files were missed by the auto-filer that generated #360–#372 (same regex-gap pattern as my v2 scanner). IT Director direction: remaining §6.X cleanup shall proceed via PDF-driven visual scan rather than scanner-driven ripple filing — anything that renders visibly in the compiled PDF as a section-specific cross-reference gets a ripple and a fix. Scanner-based approach retired for this sweep category due to regex-gap reliability concerns.

**Phase 5B LASO queue status:** Entries 29 (2.11), 30 (2.12), 31 (2.13) remain. Recalc marker after entry 39 (end of 5C).

### Chapter 0 / Front Matter

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 000 | Front Matter | T | v3 | 0 | — |

### Chapter 1 — Governance

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 1.02 | Code of Ethics | T+ | — | 1 | #402 |
| 1.03 | Standard Operating Ethos | T | v2.0 | 0 | — |
| 1.04 | Formatting Standards | T+ | v1.4 | 1 | #375 |
| 1.05 | Policy Review and Update Procedures | T+ | v2.2 | 1 | #403 |
| 1.06 | IT Governance and Oversight Structure | T | v2.1 | 0 | — |
| 1.07 | Workforce Roles | T+ | v1.3 | 1 | #354 |
| 1.08 | Delegation of Authority | T | v1.5 | 0 | — |
| 1.09 | Risk Management | T | v2.1 | 0 | — |
| 1.10 | IT Financial / Procurement | T | v2.2 | 0 | — |
| 1.11 | Data Governance and Classification | T+ | v2.3 | 1 | #404 |
| 1.12 | IT Asset Management | T+ | v2.6 | 3 | #329, #405, #423 |
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
| 2.11 | Audit Logging and Monitoring | D | — | 2 | #91, #92 |
| 2.12 | Media Protection and Sanitization | D | — | 5 | #94, #95, #228, #324, #330 |
| 2.13 | Physical Security | D | — | 3 | #96, #97, #98 |
| 2.14 | Mobile and Remote Access | D | — | 5 | #99, #101, #102, #229, #332 |
| 2.15 | Secure Software Lifecycle | D | — | 3 | #103, #104, #105 |

### Chapter 3 — Service Management

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 3.01 | Service Catalog and SLA | T+ | v2.4 | 1 | #406 |
| 3.02 | Service Level Management | T+ | v2.5 | 3 | #309, #407, #424 |
| 3.03 | Service Communication | T | v2.0 | 0 | — |
| 3.04 | Service Delivery Feedback | T | v2.1 | 0 | — |
| 3.05 | Service Request Fulfillment | T+ | v2.1 | 2 | #308, #408 |
| 3.06 | Operational Incident Management | T+ | v2.1 | 2 | #313, #409 |
| 3.07 | Problem Management | T+ | v2.2 | 2 | #316, #410 |
| 3.08 | CMDB | T+ | v2.2 | 1 | #411 |
| 3.09 | Change Management | T | v2.0 | 0 | — |
| 3.10 | Release and Deployment | T+ | v2.0 | 1 | #377 |
| 3.11 | Capacity and Availability | T+ | v2.0 | 2 | #317, #412 |
| 3.12 | Monitoring and Event Management | T+ | v2.0 | 2 | #318, #413 |
| 3.13 | Knowledge Management | T+ | v2.2 | 1 | #414 |
| 3.14 | IT Project Management | T | v2.2 | 0 | — |
| 3.15 | Service Continuity | T+ | v2.1 | 3 | #314, #319, #415 |
| 3.16 | Service Improvement | T+ | v2.0 | 1 | #416 |
| 3.17 | System Maintenance and Vendor Repairs | T+ | v2.1 | 1 | #417 |

### Chapter 4 — Incident Response

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 4.01 | IR Policy Overview | T+ | v2.0 | 1 | #418 |
| 4.02 | Identification and Reporting | T+ | v2.1 | 1 | #419 |
| 4.03 | Containment Strategy and Playbooks | T+ | v2.1 | 1 | #420 |
| 4.04 | Eradication | T+ | v2.2 | 1 | #421 |
| 4.05 | Recovery and Restoration | T+ | v2.2 | 1 | #422 |
| 4.06 | Communication Protocols | T+ | v2.2 | 1 | #378 |
| 4.07 | Postmortem and Lessons Learned | T | v1.0 | 0 | — |

### Chapter 5 — Compliance

| # | Title | State | Ver | Open | Tickets |
|---|---|---|---|---|---|
| 5.01 | Implementation, Enforcement, Legal | T+ | v1.1 | 2 | #334, #345 |
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
| 26 | ~~2.06 (Privacy/Data Protection)~~ — ✅ v2.6, April 18, 2026. Five cross-validator rounds plus IT-lead PIA architectural pivot (Round 4, IT Director direction). Tickets #74, #75, #76, #77, #287 closed. Ripples committed this session: 1.08 v1.5 (#350 PIA non-delegable), 1.11 v2.3 (#347 non-CJI residency rules), 3.14 v2.2 (#349 charter PIA flag); #348 (annual classification review) withdrawn — already present in 1.11. New ripples filed: #351 (2.03 privacy role-based training track), #352 (6.01 "Privacy Incident" glossary evaluation). Sweep absorption notes on #208, #235, #264, #291. Architectural landings: §3 restructured to 6 roles in descending authority with IT-lead PIA model (AID prepares + retains, Department Heads notify/contribute/acknowledge residual risk, IT Director approves non-delegable); §4 flat bolded-bullet-label structure with Assessment/Enforcement/Exceptions routing to 5.01 §6.6; §5 split per strict 1.04 §6.7 body-citation test — Cited References (11 ECIO + NRS 603A + NRS 603A.220 + CJIS v6.0 Section 4 + CJIS IR-6) vs. Framework Alignment (CJIS SC-13/SC-28 + 3 CSF + 11 SP alphanumerically-ordered + 2 COBIT + 1 ITIL); §6 framing preamble establishes privacy-governance overlay posture; §6.1 PIA construct with six objective triggers (Round 5 bounding on "material change" trigger), Department-Head data authority tied to legal-authority enumeration, AID custodial chain routing retention through 1.11 §6.9; §6.4 encryption routes entirely to 1.11 §6.4/§6.5 (single source of truth, no dual-maintenance, correct section refs verified against 1.11 v2.3); §6.7 and §6.8 decomposed from prose into labeled bullets (Round 5 atomic decomposition). Three new standing declines promoted to §4: #26 (retention citations in 2.06 — 3rd recurrence), #27 (PHI authority / HIPAA — 2nd recurrence), #28 (volume tiers — 2nd recurrence). Five cross-validator rounds; standing declines #1 (flat-list §5, 3rd recurrence), #14 (stale source on Data Owners), #20 (inline 5.01 exception into §4), #25 (Clarification-tag misuse, self-detected Round 1) held. | 5 (#74, #75, #76, #77, #287) | Highest Ch2 ticket count; established IT-lead PIA model and framing preamble pattern |
| 27 | ~~2.02 (Personnel Security)~~ — ✅ v2.4, April 19, 2026. Tickets #64, #217 closed. Ripples filed: #354 (1.07 remove 5-year CJI rescreening, Path A — closes Pattern #29 dependency; 1.07 moves T→T+), #355 (manual-wide LRDA citation verification sweep — numbers, titles, retention periods, companion NRS 239.125/NAC 239.155 citations), #356 (2.01 §3 universal group label normalization — outlier "All Users of County IT Resources" vs. dominant "All County Personnel" convention; 2.01 moves T→T+). Sweep absorption notes on #208 (scope-correct "All County Personnel" not IO-personnel error), #235 (zero prohibited-language hits), #245 (not applicable), #264 (role distribution applied), #6/#7/#8/#10 (zero product names). Architectural landings: §3 restructured to 6 roles descending authority with AID added (L3 day-to-day workflow documentation) and HR role expanded (fingerprint submission coordination separated from CJIS adjudication per Gemini substantive gap — PS-3 adjudication authority vested in CSO/CSA, not HR); §4 rebuilt to Assessment/Enforcement/Exceptions flat bolded-label structure with Universal Applicability + Sanctions optional governed labels + Constraint sub-bullet on CJI exception prohibition; §5 Cited/Framework split with 11 of 11 Cited entries verified load-bearing per 1.04 §6.7 strict enforcement (body-citation audit run at Round 3 after Gemini Defect 1 — 5 entries lacked body citations, all added in v2.3); CJIS legacy "Section 5.12" converted to v6.0 PS-family anchors (PS-3, PS-4, PS-5, PS-7) matching 1.13 v2.2 / 1.10 v2.2 pattern; NRS 205 narrowed to NRS 205.4765 (Unlawful acts regarding computers) matching 2.01 v2.4 pattern; NRS 239.125 + NAC 239.155 added as companion retention authority alongside LRDA 20070321 direct cite matching 1.13 v2.2 pattern; §6.3 CJI Adjudication restructured with conditional-delegation pattern (CSO retains adjudication authority unless formally delegated to IT Director) per ChatGPT Gap 2; §6.3 Authorized CJI Access List added per CJIS PS-3(a)(7) with blended directive split into parent + 2 atomic sub-bullets per 1.04 §6.8; §6.4 renamed "Continued Access Review" — 5-year rescreening removed per IT Director decision, event-triggered HR→IT Director notification flow established; §6.4 Self-Reporting Non-Compliance suspend-not-revoke + 30-minute SLA per Gemini Gap 1 + ChatGPT Gap 3; §6.5 lead-in expanded to cover HR (1.08 §6.5) + vendor (1.13 §6.3) notification sources; §6.6 Exit Interview split into three population-class bullets (County personnel with HR-handled + Exception clarifier + Constraint for non-waivable credential/asset recovery; contractors/vendors via 1.13; interns/volunteers/electeds via sponsoring/appointing authority); §6.7 High-Risk Individual Definition with determination authorities anchored (HR/IT Director/County Manager/DA's Office for credible threat; LE/DA/federal agency for investigation notice; IT Director (as LASO)/CSO for CJI integrity threat). Three cross-validator rounds plus IT Director §3 label challenge at Round 3 close; Round 1 Path A locked removal of 5-year rescreening; Round 2 surfaced 5 body-citation gaps + blended directives in §6.3/§6.6; Round 3 adjudicated blended directives, HR adjudication authority, reference load-bearing; final label check normalized §3 to manual-dominant "All County Personnel" convention. Standing declines #1, #9, #20, #22 held repeatedly; new Pattern #29 promoted to §4 (cross-validator pushback on locked operational-reality decisions via cross-policy dependency citation — third-recurrence confirmed Rounds 1/2/3 on 5-year rescreening). | 2 (#64, #217) | Personnel security feeds access control |
| 28 | ~~2.04 (Access Control)~~ — ✅ v2.3, April 20, 2026. Tickets #69, #70 closed. Ripple filed: #358 (2.02 §4 Sanctions NRS 205.4765 civil/criminal overstatement — single-line fix, v2.4 → v2.5; 2.02 moves T→T+). Sweep absorption notes on #208 (§3 6-role restructure, IT Admins/Data Owners retired, All County Personnel added), #235 (one prohibited "attempt to" hit fixed during drafting plus Round 1 "promptly"/"without delay" vague-timing fixes), #245 (not applicable), #264 (role redistribution across IT Director/AID/DH/HR/ACP), #291 (FIPS 140 inline replaced with 1.11 §6.5 CMVP by-reference), #6 (zero product names). Architectural landings: §2 In/Out Scope with routing pointers to 2.02, 2.05, 2.07, 2.10, 2.11, 2.13, 2.14, 5.01; §3 6-role descending-authority Ch2 LASO pattern (IT Director → CM → AID → DH → HR → ACP); §4 mandatory Assessment/Enforcement/Exceptions + CJI Constraint sub-bullet + Universal Applicability + Sanctions; §5 Cited/Framework split with 13 ECIO policies, NRS 205.4765, 18 CJIS sections (AC-*, IA-*, IR-6(a), PS-4/5), NIST SP 800-53 AC-2 all body-cited; §5 invalid IA-5(2)(c) replaced with IA-11 (Re-Authentication) verified against CJIS v6.0; §6.1 Termination split into Involuntary (30 min) / Standard (24 hr PS-4) / Transfer extracted as separate modify-not-disable directive per 2.02 §6.5 + PS-5, High-Risk dual-path (HR notification + independent LASO discovery), Inactivity 30-day stricter than CJIS 90-day floor (Rationale tag); §6.2 collapsed to 1.08 §6.6 by-reference eliminating SoD dual-maintenance; §6.3/§6.4/§6.5/§6.6/§6.7/§6.8/§6.9 all active-voice with AID/IT Director/All County Personnel role anchors; §6.6 15-min device lock stricter than CJIS AC-11 30-min floor (Rationale tag); §6.6 AC-11 NOTE carve-out as Exception sub-bullet; §6.7 FIPS 140 → 1.11 §6.5 CMVP by-reference; §6.9 quarterly/semi-annual/annual/privileged recertification cadence tied to 1.11 classification levels + 1.09 quarterly risk cycle for CJI + 1.07 competency maintenance for privileged access + documentation split into three atomic directives routing retention to 1.11 §6.9. Three cross-validator rounds. New Pattern #30 promoted to §4 (surface-framing rotation on §2 parenthetical prohibition — Gemini raised Round 1 and Round 3 with rotated surface rationale; 1.04 v1.4's own §2 demonstrates parentheticals are permissive; third-recurrence rule applies). Standing declines #1, #7, #15, #20, #22, #23, #26 held repeatedly across three rounds. | 2 (#69, #70) | Foundational — 2.05 I&A depends on it |
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
