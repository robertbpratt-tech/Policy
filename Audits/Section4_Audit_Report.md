# Section 4 Audit Report

**Status:** Audit closed — Q1–Q7 + Q-supplemental adjudicated May 01, 2026; ticket scope finalized
**Date:** May 01, 2026
**Auditor:** Claude Opus 4.7
**Scope:** 60 numbered policies (Ch 1–5), §4 (Compliance) — checked against 1.04 §6.6 + Plan §9.1 Rule #1 (v1.5, locked April 23, 2026)
**Spec authority:** `01/104.lyx` fetched live at session start
**Audit class:** Observation-only, single-session — no source modifications

---

## Executive Summary

§4 is the policy's compliance and enforcement section — Assessment, Enforcement, Exceptions are the constitutional triad per 1.04 §6.6. Mechanical compliance is **uniform on the structural floor** (every policy has §4 Subsection*, every policy carries the mandatory three bullets at d=0 with A < En < Ex relative ordering, no numbered subsections, no non-Standard / non-Itemize layouts, no cross-policy §6.X depth violations).

**Seven defect classes (D21–D27) span 30 unique policies.** Variance lives in three layers:

1. **Inline §4 exception drift (D23) — 24 T+ policies.** Substantively understated by pre-audit ticket #481 (which scoped 9 policies). The audit's structured manual-wide inventory found inline open-ended-exception language across 24 T+ policies — paralleling the #467 understatement pattern from §3 audit. Q7 ruling locks Standard form (5.04 / 5.05 v2.0 pattern naming IT Director as approver explicitly) as the canonical replacement; Compact form (5.02 / 5.03 v2.0 pattern) preserved as a controlled variant where policy-specific approver applies.
2. **§6.12 clarifier-tag importation into §4 (D25.1) — 10 policies.** §6.12 governed clarifier tags (Constraint, Clarification, Exclusion) imported into §4 bullets. Q2 ruling: strip from §4. Architectural review extended the ruling manual-wide via Q-supplemental: §6.12 governed clarifier set narrows to Rationale + Exception only (50 §6 use-sites + 16 §4 use-sites = 66 total surface absorbed into Phase 5F-pending strip-and-restructure).
3. **Custom §4 sub-architecture, unlabeled d=1 sub-lists, Sanctions-warrant misuse (D25.2 + D26 + D27) — smaller surface.** 1.08 Operational/Governance/Stand-in tri-architecture; 2.11 / 2.12 Sanctions sub-architecture; 4.03 / 4.05 / 4.07 unlabeled enforcement enumerations; 2.13 Sanctions warrant. All restructure into inline prose; substance preserved verbatim.

**Two architectural amendments locked May 01, 2026:**

- **§6.6 amendment (#506).** Optional-bullet set narrows to **Sanctions only**. Universal Applicability, Emergency Deviations, Constructive Notice, Mandatory Compliance — all four stripped per Q-supplemental. Mandatory-three contiguity locked: A / En / Ex shall be the first three bullets in §4. Optional bullets follow.
- **§6.12 amendment (#509).** Governed clarifier-tag set narrows to **Rationale + Exception only** (Constraint, Clarification, Exclusion stripped). Rationale definition tightened semantically to the audit-defensibility use case ("…requirement that exceeds an external minimum or carries architectural status not self-evident…"). Manual-wide strip-and-restructure across ~25 policies, 49 use sites. **Absorbs #493 Constraint-strip component.**

Both amendments couple into 1.04 v1.5 → v1.6 release alongside #494 (§6.5) and #498 (§9.1) — **four-amendment v1.6 single-release** at audit close (later expanded to five with §6.11 amendment #515 from §5 audit).

This is the fourth of six Phase 5F section audits. Defect IDs use **D21–D27** (continuing from §3's D11–D20.x). Ticket letter codes **O, P, Q, S, T, U, V, W, X, Y, Z** (continuing from §3's I, J, K1, K2, L, M, N — letter R skipped per filing-time decision).

---

## Mechanical Floor

| # | Floor item | Spec authority | Result |
|---|------------|---------------|--------|
| F27 | §4 section label = "Compliance" | 1.04 §6.6 | **60/60** ✓ |
| F28 | Mandatory three bullets present at d=0 (Assessment, Enforcement, Exceptions) | 1.04 §6.6 | **60/60** ✓ |
| F29 | A < En < Ex relative ordering | 1.04 §6.6 | **57/60** (D24 contiguity violations — 1.05, 1.10, 2.01) |
| F30 | No numbered subsections in §4 | 1.04 §6.6 | **60/60** ✓ |
| F31 | No non-Standard / non-Itemize layouts in §4 | 1.04 §6.6 | **60/60** ✓ |
| F32 | No cross-policy §6.X depth violations in §4 | 1.04 §6.11 / Plan §9.1 Rule #1 | **60/60** ✓ |

§4 mechanical floor is the cleanest of any audited section. The constitutional triad is universally honored; structural skeleton holds at the spec-template level. Defect surface is concentrated at the bullet-content layer (D21–D23 mandatory-three content variance), the optional-bullet layer (D25 / D27 — addressed via §6.6 amendment), and the d=1 nesting layer (D26 — three policies' Enforcement enumerations).

---

## Defect Catalog

§4 audit defect classes use **D21–D27** (continuing from §3's last defect D20.x).

### D21 — Missing "Oral exceptions are not valid" constitutional sentence (§6.6)

**Surface:** 3 T+ policies. Per 1.04 §6.6, the Exceptions bullet body shall include the constitutional sentence "Oral exceptions are not valid." 1.14 v2.3, 4.02, 4.06 omit the sentence; restore mechanically.

| Policy | Disposition |
|--------|-------------|
| **1.14** v2.3 | Add sentence to Exceptions bullet body |
| **4.02** | Add sentence to Exceptions bullet body |
| **4.06** | Add sentence to Exceptions bullet body |

### D22 — Multi-Standard opening sentence in §4 (§6.6)

**Surface:** 1 policy. 4.03 §4 opens with multiple Standard layouts before mandatory triad.

| Policy | Current | Disposition |
|--------|---------|-------------|
| **4.03** | Multi-Standard prose preceding mandatory three bullets | Strip; §4 opens directly with Assessment bullet per §6.6 template |

### D23 — Inline §4 exception drift (§6.6 + by-reference architecture per #430)

**Surface:** 24 T+ policies — substantially larger than #481's documented 9-policy scope.

24 policies carry inline open-ended-exception language in §4 Exceptions bullet bodies that should route by reference to the centralized exception architecture. Audit's structured inventory found the surface ~2.7× larger than #481 documented — paralleling the #467 understatement pattern from §3 audit.

**Per Q7 ruling (May 01, 2026):** Standard form (5.04 / 5.05 v2.0 pattern, naming IT Director as approver explicitly) is the canonical replacement. Compact form (5.02 / 5.03 v2.0 pattern) preserved as a controlled variant where policy-specific approver applies (e.g., 1.06 routes governance exceptions to County Manager).

**Disposition:** New ticket P (#500). **Supersedes #481.** Substantive — heaviest §4 ticket.

### D24 — Mandatory-three contiguity violations (§6.6)

**Surface:** 3 policies. Optional bullets (Universal Applicability, Emergency Deviations) interleave between mandatory triad bullets, breaking A / En / Ex contiguity.

| Policy | Interleave pattern |
|--------|-------------------|
| **1.05** | Emergency Deviations interleaves between Enforcement and Exceptions |
| **1.10** | Emergency Deviations interleaves; also Universal Applicability before Assessment |
| **2.01** | Universal Applicability before Assessment |

**Per Q1 ruling (May 01, 2026):** Strict — A / En / Ex are the first three bullets in §4. Optional bullets follow. Resolves all three by stripping the interleaving optional bullets entirely (Emergency Deviations / Universal Applicability stripped per §6.6 amendment; see Q-supplemental).

### D25 — §6.12 clarifier-tag importation + custom §4 sub-architecture

**D25.1 — §6.12 clarifier-tag importation into §4:** 10 policies. Constraint, Clarification, Exclusion clarifier tags imported into §4 bullets where prose carries the same load.

**Per Q2 ruling (May 01, 2026):** Strip Constraint + Clarification + Exclusion from §4. Same architectural ruling extended manual-wide via Q-supplemental review (see below).

**D25.2 — Custom §4 sub-architecture restructure:** 3 policies.

| Policy | Custom architecture | Disposition |
|--------|---------------------|-------------|
| **1.08** | Operational / Governance / Stand-in tri-architecture under Exceptions bullet via d=1 labels | Restructure into Exceptions bullet body inline prose; substance preserved verbatim, d=1 label scaffolding strips (Q3) |
| **2.11** | Sanctions sub-architecture under Sanctions bullet via d=1 labels | Restructure into Sanctions bullet body inline prose; substance preserved verbatim; extra-framework Sanctions warrant maintained, d=1 label scaffolding strips (Q4) |
| **2.12** | Sanctions sub-architecture under Sanctions bullet via d=1 labels | Same disposition as 2.11 (Q4) |

### D26 — Unlabeled d=1 sub-lists in §4 (§6.6)

**Surface:** 3 policies (4.03, 4.05, 4.07) plus 1.10 (absorbed by #508 Emergency Technical Approval procedural sub-list dissolution).

| Policy | Unlabeled d=1 location |
|--------|-----------------------|
| **4.03** | Enforcement enumeration |
| **4.05** | Enforcement enumeration |
| **4.07** | Enforcement enumeration |
| **1.10** | Emergency Technical Approval procedural sub-list (absorbed by #508) |

**Per Q5 ruling (May 01, 2026):** Strict — d=1 nesting not permitted in §4. Restructure 4.03 / 4.05 / 4.07 Enforcement enumeration as inline prose. 1.10 Emergency Technical Approval procedural sub-list dissolves into §6 body via Ticket Y migration.

### D27 — 2.13 Sanctions warrant misuse (§6.6)

**Surface:** 1 policy. 2.13 carries a Sanctions optional bullet labeling violation enumeration that does not warrant the extra-framework Sanctions architecture (Sanctions is reserved for consequences genuinely beyond the standard enforcement framework owned by 5.01).

**Per Q6 ruling (May 01, 2026):** Strip the Sanctions label from 2.13; inline violation enumeration into Enforcement bullet body. Future architectural decision to elevate physical security to 2.11 / 2.12 Sanctions parity is preserved as a separate substantive tightening question, not absorbed into Phase 5F.

---

## Adjudication Queue — RESOLVED

### Q1 — D24 contiguity strict, locked May 01, 2026

**Question:** D24 surfaces three policies (1.05, 1.10, 2.01) with optional-bullet interleaving between mandatory triad bullets. Should the contiguity rule be strict (A / En / Ex shall be the first three bullets) or loose (relative ordering preserved with optional interleaves permitted)?

**Ruling:** **Strict.** Assessment / Enforcement / Exceptions are the first three bullets in §4. Optional bullets follow. Resolves 1.05, 1.10, 2.01 by stripping the interleaving optional bullets entirely (Emergency Deviations / Universal Applicability stripped per §6.6 amendment).

**Disposition:** Codified in §6.6 amendment (Ticket W / #506). Per-policy execution under tickets X (#507) and Y (#508).

### Q2 — D25.1 §6.12 clarifier-tag strip from §4, locked May 01, 2026

**Question:** Strip §6.12 governed clarifier tags (Constraint, Clarification, Exclusion) from §4 bullets where prose carries the same load?

**Ruling:** **Strip.** §4 is the compliance section; clarifier tags belong in §6 governance prose where they qualify directives. §4 bullets carry compliance directives whose force is independent of qualifier annotations.

**Disposition:** Filed under ticket S (#502). Gated on §6.12 amendment (#509) landing.

### Q3 — D25.2 1.08 custom labels, locked May 01, 2026

**Question:** 1.08's Operational / Governance / Stand-in tri-architecture under Exceptions bullet uses d=1 labels not permitted by §6.6. Restructure how?

**Ruling:** **Restructure into Exceptions bullet body inline prose.** Substance preserved verbatim; d=1 label scaffolding strips. The tri-architectural distinction (Operational vs Governance vs Stand-in deviations) is meaningful and load-bearing; preserved as inline prose distinction within the Exceptions bullet body.

**Disposition:** Filed under ticket T (#503).

### Q4 — D25.2 2.11 / 2.12 Sanctions sub-architecture, locked May 01, 2026

**Question:** 2.11 and 2.12's Sanctions sub-architecture under Sanctions bullet uses d=1 labels. Restructure how?

**Ruling:** **Restructure into Sanctions bullet body inline prose.** Substance preserved verbatim; extra-framework Sanctions warrant maintained (the policies' Sanctions architecture justifies the optional Sanctions bullet); d=1 label scaffolding strips.

**Disposition:** Filed under ticket T (#503).

### Q5 — D26 unlabeled d=1 sub-lists, locked May 01, 2026

**Question:** 4.03 / 4.05 / 4.07 carry unlabeled d=1 sub-lists under Enforcement enumeration. Restructure how?

**Ruling:** **Strict — d=1 nesting not permitted in §4.** Restructure 4.03 / 4.05 / 4.07 Enforcement enumeration as inline prose. 1.10 Emergency Technical Approval procedural sub-list dissolves into §6 body via Ticket Y migration.

**Disposition:** Filed under ticket U (#504); 1.10 case absorbed by ticket Y (#508).

### Q6 — D27 2.13 Sanctions warrant, locked May 01, 2026

**Question:** 2.13's Sanctions optional bullet labels violation enumeration that doesn't warrant extra-framework Sanctions architecture. Strip or elevate?

**Ruling:** **Strip the Sanctions label from 2.13; inline violation enumeration into Enforcement bullet body.** Future architectural decision to elevate physical security to 2.11 / 2.12 Sanctions parity is preserved as a separate substantive tightening question, not absorbed into Phase 5F.

**Disposition:** Filed under ticket V (#505).

### Q7 — D23 canonical Exceptions form, locked May 01, 2026

**Question:** 24 T+ policies carry inline open-ended-exception language. What's the canonical replacement form?

**Ruling:** **Standard form is canonical.** 5.04 / 5.05 v2.0 pattern names IT Director as approver explicitly — this becomes the default replacement. Compact form (5.02 / 5.03 v2.0 pattern) preserved as a controlled variant where policy-specific approver applies (e.g., 1.06 routes governance exceptions to County Manager).

**Disposition:** Filed under ticket P (#500). Substantive — heaviest §4 ticket. **Supersedes #481.**

### Q-supplemental — Manual-wide §6.6 + §6.12 architectural narrowing, locked May 01, 2026

**Background.** During audit, IT Director surfaced concern that the §6.6 optional-bullet set carried weasel architecture — soft addenda that should have been load-bearing in their architecturally-correct location. Audit confirmed: Universal Applicability is §2 Scope content; Emergency Deviations is §6 procedural content; Constructive Notice and Mandatory Compliance are unused. Sanctions is the only optional label doing distinct architectural work.

**Locked decision (May 01, 2026):** Strip Universal Applicability, Emergency Deviations, Constructive Notice, Mandatory Compliance; retain Sanctions as sole governed §6.6 optional. Future-editor preservation rationale explicitly retracted.

**Ruling extended to §6.12** after manual-wide inventory (66 uses across 27 policies; 50 in §6 body; 16 in §4 per D25.1). Inventory surfaced that Rationale (8 §6 uses — audit-defensibility documentation of County standards intentionally exceeding federal/state minimums) and Exception (9 §6 uses — defined-circumstance directive carve-outs) carry distinct architectural status that prose alone signals weakly. Constraint, Clarification, Exclusion are decorative.

**Locked decision (May 01, 2026):** Retain Rationale + Exception in §6.12; strip Constraint + Clarification + Exclusion. Rationale definition tightened semantically to the audit-defensibility use case ("…requirement that exceeds an external minimum or carries architectural status not self-evident…").

**Disposition:** Codified in §6.6 amendment (Ticket W / #506) and §6.12 amendment (Ticket Z / #509). Per-policy execution under tickets X (#507) and Y (#508) for §6.6 strip; absorbed manual-wide into #509 for §6.12 strip.

---

## Out-of-Scope (deferred)

- **2.13 physical security → 2.11 / 2.12 Sanctions parity elevation.** Preserved as a separate substantive tightening question per Q6 ruling. Not absorbed into Phase 5F.
- **Forward-look May reframe component of #493** preserved as forward action item for Phase 5F intake or absorption (the Constraint-strip component absorbs into #509 at audit close).

---

## Ticket Package (locked)

§4 audit uses ticket letter codes **O, P, Q, S, T, U, V, W, X, Y, Z** (continuing from §3's I–N; letter R skipped at filing time).

| Code | Class | Title | Scope | Labels |
|------|-------|-------|-------|--------|
| **O (#499)** | D21 | `[§4 audit] D21 — Add "Oral exceptions are not valid" constitutional sentence (3 policies)` | 1.14, 4.02, 4.06 | `format`, `1.04`, `cross-cutting` |
| **P (#500)** | D23 | `[§4 audit] D23 — Strip inline §4 exception drift across 24 T+ policies; Q7 Standard form canonical replacement` | 24 policies | `cross-cutting`, `substantive`, `1.04` (**Supersedes #481**) |
| **Q (#501)** | D22 | `[§4 audit] D22 — Strip multi-Standard opening sentence in 4.03 §4` | 4.03 | `format`, `ch4-incident-response` |
| **S (#502)** | D25.1 | `[§4 audit] D25.1 — Strip §6.12 clarifier-tag importation from §4 (Constraint, Clarification, Exclusion; 10 policies)` | 10 policies | `cross-cutting`, `format`, `1.04` (gated on #509) |
| **T (#503)** | D25.2 | `[§4 audit] D25.2 — Restructure custom §4 sub-architecture into inline prose (1.08 tri-arch, 2.11 / 2.12 Sanctions sub-arch)` | 1.08, 2.11, 2.12 | `cross-cutting`, `substantive`, `1.04` |
| **U (#504)** | D26 | `[§4 audit] D26 — Restructure unlabeled d=1 Enforcement sub-lists as inline prose (4.03, 4.05, 4.07)` | 4.03, 4.05, 4.07 | `format`, `ch4-incident-response`, `1.04` |
| **V (#505)** | D27 | `[§4 audit] D27 — Strip Sanctions label from 2.13; inline violation enumeration into Enforcement` | 2.13 | `substantive`, `ch2-security`, `1.04` |
| **W (#506)** | §6.6 amendment | `[1.04] §6.6 amendment to v1.6 — narrow optional-bullet set to Sanctions only; lock mandatory-three contiguity` | 1.04 | `1.04`, `central`, `substantive`, `cross-cutting` |
| **X (#507)** | §6.6 cleanup | `[§4 audit] Universal Applicability strip + §2 Scope migration (5 policies)` | 5 policies | `cross-cutting`, `substantive`, `1.04` (gated on #506) |
| **Y (#508)** | §6.6 cleanup | `[§4 audit] Emergency Deviations strip + §6 body migration (1.05, 1.10)` | 1.05, 1.10 | `cross-cutting`, `substantive`, `1.04` (gated on #506) |
| **Z (#509)** | §6.12 amendment | `[1.04] §6.12 amendment to v1.6 + manual-wide strip of Constraint / Clarification / Exclusion (~25 policies, 49 use sites)` | 1.04 + manual-wide | `1.04`, `central`, `substantive`, `cross-cutting` (**Absorbs #493**) |

**Filing dependencies:**
- **S (#502)** gates on **Z (#509)** landing (§6.12 amendment must be in 1.04 before per-policy clarifier strips begin).
- **X (#507)** and **Y (#508)** gate on **W (#506)** landing (§6.6 amendment must be in 1.04 before optional-bullet strips begin).
- **W (#506)** and **Z (#509)** couple into v1.6 release alongside #494 (§6.5) and #498 (§9.1).

### Tickets superseded / absorbed at §4 audit close

| Disposition | Ticket | Reason |
|-------------|--------|--------|
| Closed as superseded | **#481** (open-ended exception inline drift) | Documented 9 policies; audit's structured inventory found 24-policy scope. Full scope + Q7 canonical replacement filed under #500. |
| Closed; component absorbed | **#493** (Constraint + May reframe component) | Constraint-strip component absorbs into #509 manual-wide §6.12 strip. May reframe component preserved as forward action item for Phase 5F intake or absorption. |

### Architectural Codification (no separate ticket — folded into #506 + #509)

| Item | Disposition |
|------|-------------|
| **§6.6 amendment** (#506) | Optional-bullet set narrows to Sanctions only; mandatory-three contiguity locked as first-three-bullets requirement. |
| **§6.12 amendment** (#509) | Governed clarifier-tag set narrows to Rationale + Exception only; Rationale definition semantically tightened to audit-defensibility use case. |

Both amendments couple into 1.04 v1.5 → v1.6 release alongside #494 (§6.5) and #498 (§9.1) — **four-amendment v1.6 single-release** at §4 audit close (later expanded to five with §6.11 amendment #515 from §5 audit).

---

## Plan / README updates (post-adjudication)

- **TIGHTENING_PLAN.md Phase 5F section.** §4 audit close note recorded (commit `6c0abfef`, May 1, 2026) with floor summary, defect classes D21–D27, ticket O–Z filings (#499–#509), Q1–Q7 + Q-supplemental ruling dispositions, supersession notes for #481 and #493.
- **TIGHTENING_PLAN.md v1.6 amendment list.** Added #506 (§6.6) and #509 (§6.12) — package size 2 → 4 amendments at §4 audit close.
- **TIGHTENING_PLAN.md Phase 5F intake count.** 14 → 25 tickets (8 from §1 + §2 + §3 audits → 25 with §4 audit).
- **README.md per-policy ticket assignments.** ~30 policy rows updated (commit `d9550082`, May 1, 2026) covering D21 (3), D23 (24), D22 (1), D25.1 (10), D25.2 (3), D26 (3), D27 (1), and §6.6-cleanup downstream tickets X / Y (7 policies) plus §6.12-cleanup #509 surface (~25 policies; 16 §4 use-sites + 50 §6 use-sites).

---

## Audit Conclusion

§4 mechanical floor is uniform across all six floor items (F27–F32) — the constitutional triad and structural skeleton hold cleanly across all 60 policies. Variance lives in seven fileable defect classes (D21–D27) addressed by 9 cleanup tickets (#499–#505, #507, #508) plus 2 constitutional amendments (#506, #509) and 2 ticket supersessions (#481 → #500, #493 absorbed by #509).

Locked rulings (May 01, 2026): **Q1** strict mandatory-three contiguity (A / En / Ex first three bullets); **Q2** strip §6.12 clarifier tags from §4; **Q3** restructure 1.08 tri-architecture into inline prose; **Q4** restructure 2.11 / 2.12 Sanctions sub-architecture into inline prose; **Q5** strict — d=1 nesting not permitted in §4; **Q6** strip Sanctions label from 2.13; **Q7** Standard form canonical replacement for inline exception drift; **Q-supplemental** §6.6 optional-bullet narrowing to Sanctions only and §6.12 governed-clarifier narrowing to Rationale + Exception only.

Architectural codification: **§6.6 amendment** (#506) and **§6.12 amendment** (#509) — both queued for 1.04 v1.5 → v1.6 release.

Filing scope locked May 01, 2026: **O (#499)** (3 sites), **P (#500)** (24 policies — heaviest §4 ticket), **Q (#501)** (1 policy), **S (#502)** (10 policies; gated on #509), **T (#503)** (3 policies), **U (#504)** (3 policies), **V (#505)** (1 policy), **W (#506)** (constitutional), **X (#507)** (5 policies; gated on #506), **Y (#508)** (2 policies; gated on #506), **Z (#509)** (constitutional + ~25 policies / 49 use sites). No new standing decline patterns inscribed; §4 audit absorbs into existing pattern stack (#20, #36, #37, #41).

§4 audit is the fourth of six Phase 5F section audits. Sections 5 and 6 follow.
