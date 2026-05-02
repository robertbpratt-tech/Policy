# Section 3 Audit Report

**Status:** Audit closed — D11–D20.6 adjudicated May 01, 2026; ticket scope finalized
**Date:** May 01, 2026
**Auditor:** Claude Opus 4.7
**Scope:** 60 numbered policies (Ch 1–5), §3 (Roles and Responsibilities) — checked against 1.04 §6.5 + manual-wide canonical role conventions (v1.5, locked April 23, 2026)
**Spec authority:** `01/104.lyx` fetched live at session start (5.05 re-fetched after Phase 6 Entry 44 close, commit `74cbfd91`)
**Audit class:** Observation-only, single-session — no source modifications

---

## Executive Summary

§3 is the policy's role anchor — every directive in the policy attaches to a §3 role. Mechanical floor on title format, post-#467 colon placement, and bullet structure is **uniformly met (60/60 on every spec item)**.

**§3 is the heaviest defect surface yet — 41 unique policies touched (68% of in-scope manual).** Variance concentrates in two areas:

1. **Obligation atomicity (D11 + D12 + D13 + D14) — 22 policies.** 18 policies carry at least one chained obligation; 4 multi-sentence obligations; 3 Constraint-tagged non-Shall openers; 5 May-permissive openers. Largest single defect category in the section audit series so far.
2. **Role label canonicalization (D18 + D20) — ~12 policies + 1 covered by existing #356.** Plural variants, combined role labels, acronym parentheticals, activity derivatives, scope clarifiers, deprecated forms.

**Smaller findings:** D15/D16 authority order corrections (25 policies — substantially more than initial estimate after re-sweep against locked sequence); D17 narrative prose block (3.15 only); D19 product name (5.06, D-state, absorbs at E45).

**Three architectural rulings (Q1, Q2, Q3) lock substantive content of D14 reframe direction, the D15/D16 authority sequence, and D20.6 Incident Commander architecture.** Two constitutional amendments queued to land in 1.04 v1.6:

- **§6.5 amendment** (#494) — locked authority sequence + flat institutional-title-before-Department-Heads sub-rule. Updates the §6.5 illustrative example.
- **§9.1 amendment** (#498) — adds `(as Incident Commander)` to the role-clarifier convention alongside `(as LASO)` and `(as Authorizing Official)`.

This is the third of six Phase 5F section audits. Defect IDs use **D11–D20.x** (continuing from §2 audit's D1–D10). Ticket letter codes **I, J, K1, K2, L, M, N** (continuing from §2's H).

---

## Mechanical Floor

| # | Floor item | Spec authority | Result |
|---|------------|---------------|--------|
| F17 | §3 section label = "Roles and Responsibilities" | 1.04 §6.5 | **60/60** ✓ |
| F18 | Role title bolded with colon | 1.04 §6.5 (post-#467) | **60/60** ✓ |
| F19 | No trailing text after colon on role title line | 1.04 §6.5 | **60/60** ✓ |
| F20 | No empty roles (every role has at least one obligation) | 1.04 §6.5 | **60/60** ✓ |
| F21 | Obligations open with "Shall" | 1.04 §6.5 | **50/60** (D13 + D14 surface) |
| F22 | Single-directive (no chain, no multi-sentence) | 1.04 §6.5 | **42/60** (D11 + D12 surface) |
| F23 | §3 free of narrative prose blocks | 1.04 §6.5 (intent) | **59/60** (D17: 3.15 prose block) |
| F24 | Catch-all label is canonical (no deprecated forms) | Pattern #32 + #208 | **59/60** (D18: 2.01 — covered by #356) |
| F25 | §3 free of product names | Pattern #6 | **59/60** (D19: 5.06 Redmine, absorbs at E45) |
| F26 | Authority order matches locked sequence | 1.04 §6.5 (amended per Q2) | **35/60** (D15 + D16 — 25 reorders) |

§3 obligation count distribution: 3 (1.01) to 28 (2.13), mean 17.3. Role count distribution: 2 to 7 roles per policy, mean 4.9. Distribution is operationally driven (denser policies in CJIS-rooted security domain).

---

## Defect Catalog

§3 audit defect classes use **D11–D20.x** (continuing from §2 audit's D1–D10).

### D11 — Chained obligations (multi-Shall in single bullet) (§6.5 single-directive rule)

**Surface:** 18 policies / 22 instances. Largest single defect category in §3 audit. Each chain decomposes into 2 (sometimes 3) atomic obligations.

| Policy | Role | Notable chain |
|--------|------|---------------|
| **1.03** | Assistant IT Director | "Shall reinforce... and shall model the operational ethos in daily operations." |
| **1.13** | IT Director | "Shall hold the LASO designation per Policy 1.11 and shall execute all CJIS liaison..." |
| **3.06** | IT Director | "Shall review Problem records spawned under Section 6.6 and shall fulfill the authorization obligations..." |
| **3.07** | Assistant IT Director (×3) | Three separate chained obligations on the same role |
| **3.08** | AID | "...identifying deployed assets... and shall document quarterly review findings in the System of Engagement..." |
| **3.09** | IT Director | "...alternative resolution path... that authorization shall be documented in the change record..." (multi-sentence) |
| **3.13** | AID | "Shall conduct or coordinate the annual KB review cycle and shall verify..." |
| **3.15** | AID | "Shall own the Business Impact Analysis... and shall maintain it on the cadence..." |
| **3.17** | All IO Personnel | "...remote maintenance sessions... terminated... and shall document termination verification..." |
| **4.04** | IT Director | "Shall retain personal responsibility... these obligations shall not transfer to a designee." (Pattern #40) |
| **4.06** | IT Director | "Shall make law enforcement referral decisions personally and shall not delegate..." (Pattern #40) |
| **4.07** | IT Director | "Shall retain postmortem report approval... non-transferable... that shall not pass to a designee..." (Pattern #40) |
| **5.06** | IT Director | Multi-sentence with meta-clarifier in sentence 2 |

Full list across 18 policies: **1.03, 1.13, 3.03, 3.05, 3.06, 3.07, 3.08, 3.09, 3.13, 3.14, 3.15, 3.17, 4.02, 4.04, 4.05, 4.06, 4.07, 5.06**.

**Pattern #40 architecture preservation.** Several chains in 4.04, 4.05, 4.07 use the locked "shall not transfer to designee" non-transfer construct. Decomposition preserves the architecture: primary directive in one bullet; non-transfer clause in a separate negative bullet. The architecture itself is not the defect — the *chaining* is.

### D12 — Multi-sentence obligations (§6.5 single-directive rule)

**Surface:** 4 policies / 5 instances. Subset of D11; multi-sentence obligations span two complete sentences (period followed by uppercase letter starting new directive).

| Policy | Role | Notable |
|--------|------|---------|
| **3.14** | IT Director | "...emergency project designations... rationale. Normal procedures shall resume..." |
| **4.02** | IT Director | "...Incident Commander... default; the IT Director may designate any IO Personnel... IC designation does..." |
| **4.05** | IT Director (×2) | Two separate IT Director obligations spanning multiple sentences each |
| **5.06** | IT Director | "...risk-relevant findings... Policy 1.09 governs risk severity..." (sentence 2 is meta-clarifier, not directive) |

5.06 case: sentence 2 is meta-clarifier about what *the policy* does — not a directive on the IT Director. Decomposition strips sentence 2 to single-directive form.

### D13 — "Constraint:"-tagged obligations not opening with "Shall" (§6.5 + §6.12)

**Surface:** 3 policies. §6.5 mandates "Shall" opener; §6.12 permits Constraint clarifier-tag in §6 contexts. Whether §3 obligations may use the tag is unsettled architecture.

| Policy | Role | Constraint text (excerpted) |
|--------|------|------------------------------|
| **1.11** | BoCC | "**Constraint:** This delegation applies to Information Operations records... shall not be interpreted as superseding statutory duties..." |
| **2.11** | System and Network Administrators (combined — see D20.2) | "**Constraint:** Personnel administering security access controls shall not modify or delete audit logs..." |
| **4.03** | IT Director | "**Constraint:** CCA review authority and exception approval authority shall not transfer to the designee..." |

### D14 — "May" obligations (§6.5 + §6.9 permissive variant)

**Surface:** 5 policies / 7 obligations. "May" is canonical permissive verb in 1.04 §6.9; §6.5 strict reading mandates "Shall" opener exclusively.

| Policy | Role | Permissive grant |
|--------|------|------------------|
| **2.04** | AID | Approve operational access exceptions within Operational Exception Tier (5.01) |
| **3.06** | IT Director | Designate any IO staff member as IC for a specific incident |
| **3.09** | IT Director | Countermand any Emergency change designation |
| **3.09** | AID | Designate a change as Emergency in accordance with §6.2 |
| **3.09** | Incident Commander | Designate a change as Emergency under active incident response |
| **3.14** | County Manager | Serve as neutral arbitrator |
| **4.04** | IT Director | Designate any IO Personnel member as IC for a specific incident |

### D15 — Authority order: first role not IT Director (§6.5)

**Surface:** 4 policies. Per locked sequence (Q2), County Manager and BoCC outrank IT Director.

| Policy | First role | Reading |
|--------|-----------|---------|
| **1.06** (IT Governance and Oversight Structure) | BoCC | Legitimate per locked sequence |
| **1.11** (Data Governance and Classification) | BoCC | Legitimate per locked sequence |
| **2.02** (Personnel Security) | County Manager | Legitimate per locked sequence (post-Q2) |
| **5.07** (Annual Policy Review) | County Manager | Legitimate per locked sequence (post-Q2) |

**Post-Q2 ruling:** all four are correctly ordered under amended 1.04 §6.5. **No reorder needed for D15.** Reorders below land under D16 + locked-sequence sweep (the broader 25-policy reorder set surfaced after applying the locked sequence).

### D16 — Universal-label position + locked-sequence sweep (§6.5 amended)

**Surface:** 25 policies require §3 reorder against amended 1.04 §6.5. Three categories:

**Category A — IT Director ↔ County Manager swap (12 policies).** Each places IT Director before County Manager; corrected per locked sequence (CM at position 2; ITD at 3): **1.05, 1.07, 1.08, 1.14, 2.04, 2.05, 2.07, 2.11, 3.04, 3.09, 3.14, 5.01.**

**Category B — Network ↔ Systems Administrator swap (6 policies).** Per 5.04 v2.0 convention (Sys Admin first): **3.12, 3.13, 4.02, 4.03, 4.04, 4.05.** (2.07 and 2.11 are A+B; counted in A.)

**Category C — Universal-label / operational role inversions (3 policies).**
- **1.11:** Department Heads(11) before All IO(9) — swap.
- **3.01:** All IO Personnel(9) before Administrative Assistant(8) — swap.
- **3.17:** All IO Personnel(9) before Net/Sys Admin (5/6) — both move ahead of catch-all.

**Category D — Department Heads ↔ institutional title (4 policies).** Per locked sequence flat rule (institutional titles always precede Department Heads catch-all):
- **1.13:** Dept Heads before OFA + HR — reorder
- **2.01:** HR before Dept Heads + correct All IO position
- **2.02:** Dept Heads before HR — reorder
- **2.06:** HR + All IO + Dept Heads alignment
- **2.13:** Already correct under amended §6.5 — no reorder needed

### D17 — Standard prose block within §3 (§6.5 labeled-bullet structure)

**Surface:** 1 policy.

| Policy | Block | Disposition |
|--------|-------|-------------|
| **3.15** | "All roles identified in this section correspond to positions defined in **Policy 1.07** (Workforce Roles, Responsibilities, and Competency Framework)." | Strip. Role-identity mapping to 1.07 is implicit per §6.5 Role Identity Requirement. |

### D18 — Deprecated catch-all label (Pattern #32 + #208)

**Surface:** 1 policy.

| Policy | Current | Disposition |
|--------|---------|-------------|
| **2.01** | "All Users of County IT Resources" | Replace with "All County Personnel" per Pattern #32. **Covered by existing #356** — no new ticket. |

### D19 — Product name in §3 (Pattern #6)

**Surface:** 1 policy. 5.06 currently D-state; absorbs at Phase 6 Entry 45.

| Policy | §3 location | Disposition |
|--------|------------|-------------|
| **5.06** | AID bullet 1 contains "(Redmine)" parenthetical | Strip per Pattern #6. **Absorbs at Phase 6 Entry 45 tightening.** No separate §3 audit ticket. |

### D20 — Role label normalization (multiple sub-classes)

**Surface:** ~12 unique policies across 8 sub-classes.

#### D20.1 — Singular vs plural (1 policy)

| Policy | Current | Correction |
|--------|---------|-----------|
| **4.05** | Support Specialists (plural) | Support Specialist (singular) |

#### D20.2 — Combined role labels (5 policies / 8 instances; always split per Q1)

| Policy | Combined label | Split into |
|--------|---------------|-----------|
| **2.11** | System and Network Administrators | Systems Administrator + Network Administrator |
| **2.12** | Systems Administrators and Network Administrators | Systems Administrator + Network Administrator (also normalize plural) |
| **2.13** | System and Network Administrators | Systems Administrator + Network Administrator |
| **1.09** | Systems Administrators and Network Administrators | Same — split + normalize |
| **1.09** | Department Heads and Elected Officials | Department Heads + Elected Officials |
| **2.09** | Department Heads and Elected Officials | Department Heads + Elected Officials |
| **3.01** | County Personnel and Department Heads | All County Personnel + Department Heads |
| **3.04** | County Personnel and Department Heads | All County Personnel + Department Heads |

#### D20.3 — Acronym parenthetical (2 policies)

| Policy | Current | Correction |
|--------|---------|-----------|
| **1.08** | Human Resources (HR) | Human Resources |
| **5.01** | Human Resources (HR) | Human Resources |

#### D20.4 — Department Heads variants (2 policies / 3 variants)

| Policy | Current | Correction |
|--------|---------|-----------|
| **1.06** | County Department Heads | Department Heads |
| **1.08** | Department Heads (Non-IT County Departments) | Department Heads |
| **1.08** | Requesting Department Head | Department Heads (D20.8 — activity-scoping moves to obligation text) |

#### D20.5 — Office vs bare label variant (1 policy)

| Policy | Current §3 | Correction |
|--------|-----------|-----------|
| **1.08** | Fiscal Affairs | Office of Fiscal Affairs |

Body-prose ripple: 1.06, 4.01, 4.03, 4.04, 4.05 reference "Fiscal Affairs" in §6 prose. Verified: "Finance Department" does not appear anywhere in the manual.

#### D20.6 — Incident Commander role title with scope clarifier — RESOLVED Q3

**Surface:** 4.03 ("Incident Commander (when not the IT Director or Assistant IT Director)") + 4.06 (same form). Plus standalone IC bullets across 3.06, 3.09, 4.02–4.07.

**Q3 ruling:** Option B locked — accountability/execution split per LASO precedent. See Adjudication Queue Q3 below.

#### D20.7 — Legitimate context-specific institutional titles (no defect)

Buildings and Grounds (2.13), DA's Office (1.10), Project Owner (3.14), Elected Officials (post-D20.2 split). Documented for inventory completeness; no normalization needed.

#### D20.8 — Activity-derivative role labels (1 policy)

| Policy | Current | Correction |
|--------|---------|-----------|
| **1.08** | Requesting Department Head | Department Heads + activity-scoping in obligation text ("when requesting deputization authority") |

---

## Adjudication Queue — RESOLVED

### Q1 — D13 / D14 / D20.2 disposition, locked May 1, 2026

**Question:** Three §3 architectural items each have multiple defensible dispositions:
- D13 Constraint-tagged obligations — strict §6.5 reframe to "Shall" / "Shall not", or codify Constraint as permitted §3 sub-bullet form (parallel to §6.12)?
- D14 "May" obligations — accept as permitted permissive variants, reframe as conditional Shall, or codify "May" alongside "Shall" via §6.5 amendment?
- D20.2 Combined role labels — split per D5 strict singular precedent, or accept as legitimate combined defined groups when obligations apply identically?

**Rulings:**
- **D13:** **Strip Constraint tags.** Reframe as direct "Shall" / "Shall not" bullets. Stylistic preference; "Constraint" clarifier preserved as 1.04 §6.12 capability for future editors but not used in current §3 obligations.
- **D14:** **Reframe to "Shall be authorized to..."** Maintains §6.5 strict Shall opener; eliminates ambiguity about permitted vs required action; sets convention for future drafters. 4-word cost per obligation acceptable.
- **D20.2:** **Always split.** "A thought B was going to do it, B thought A was going to do it because they are both listed" — combined causes ambiguity per §6.5 single-directive principle.

**Disposition:** D13 + D14 file under ticket J (#493). D20.2 files under ticket M (#497).

### Q2 — Locked authority sequence, locked May 1, 2026

**Question:** §3 audit surfaces 25 policies with role ordering deviations. The §6.5 illustrative example reads "IT Director, County Manager, Assistant IT Director" — IT Director before County Manager, which contradicts strict descending authority. Should §6.5 be amended? What is the canonical sequence?

**Ruling:** **Lock the canonical authority sequence flat across the manual; amend 1.04 §6.5 to update the example and add ordering sub-rule.**

**Locked sequence (1.04 v1.6 §6.5 amendment per #494):**

1. Board of County Commissioners (when applicable)
2. County Manager (when applicable)
3. IT Director (with permitted clarifier variants: `(as LASO)`, `(as Authorizing Official)`, `(as Incident Commander)`)
4. Assistant IT Director
5. Systems Administrator
6. Network Administrator
7. Support Specialist (singular)
8. Administrative Assistant (when applicable)
9. All Information Operations Personnel
10. Named institutional titles (Human Resources, Office of Fiscal Affairs, Buildings and Grounds, District Attorney's Office, Project Owner, Elected Officials)
11. Department Heads
12. All County Personnel
13. External stakeholders (vendors, contractors)

**Sub-rule (flat institutional-title ordering):** Named institutional titles **always precede** the Department Heads catch-all, regardless of which holds the policy-specific authority. Less "if this, then that, except when, unless..." Consistency outranks contextual precision per IT Director ruling.

**Three concerns surfaced + addressed:**
- IT Trainees omitted from §3 sequence (L0 STAK position exists but no §3 obligations — they learn, they don't anchor obligations).
- Sys Admin → Net Admin (Sys Admin carries more tasks; matches 5.04 v2.0 convention May 1, 2026).
- "All Information Operations Personnel" above Department Heads (manual is from ECIO POV — ECIO catch-all sits with ECIO roles before peer-department leadership starts).

**Disposition:** Filed as **Ticket K1 (#494)** — 1.04 §6.5 amendment, gating Ticket K2. Filed as **Ticket K2 (#495)** — 25-policy reorder per amended §6.5, gated on K1.

### Q3 — D20.6 Incident Commander architecture, locked May 1, 2026

**Question:** Three options for IC architecture:
- **Option A** — Hard-code IC to IT Director, strip per-incident delegation (true LASO parallel).
- **Option B** — Hard-code IC to IT Director, preserve operational delegation under 4.01 §6.1 by-reference (accountability/execution split).
- **Option C** — Keep IC as standalone §3 role bullet, accept §6.5 single-person-designation ambiguity.

**Ruling:** **Option B locked.** Accountability/execution split per LASO precedent (#220, #285, #249). IT Director holds IC function by policy mandate; IT Director may delegate IC execution to any IO Personnel member for a specific incident in writing; IT Director retains accountability regardless of execution delegation.

**Non-transferable authorities (locked enumeration):** CCA review, exception approval, incident severity classification, law enforcement referral, postmortem report approval, external communications under One Voice Rule.

**Architectural mechanics:**
- §3 across affected Chapter 4 policies (4.01–4.07) carries only "IT Director" for IC-function obligations, with `(as Incident Commander)` role-clarifier parenthetical applied per established LASO/AO convention.
- §6 body prose may use "the Incident Commander" — function speaks regardless of who holds it.
- Standalone IC §3 role bullet **dissolves manual-wide.** Awkward "(when not the IT Director or AID)" parenthetical from 4.03 / 4.06 disappears.
- 4.01 §6.1 substantive amendment establishes the architecture as policy mandate.
- 1.04 §9.1 amendment adds `(as Incident Commander)` to the role-clarifier convention (third in family alongside `(as LASO)` and `(as Authorizing Official)`).

**Operational role IC-direction bullets:** Not added — existing role obligations across 4.02–4.07 already imply direction-from-IC during active incidents. Keeps §3 surface lean.

**§6 opening reference convention:** Each Chapter 4 policy gains a one-sentence opening reference to 4.01's IC architecture: "Incident Commander obligations identified in this policy attach to the function defined in Policy 4.01; the function is held by the IT Director by policy mandate, with execution delegation permitted per Policy 4.01 §6.1."

**Disposition:** Filed as **Ticket N (#498)** — heaviest single ticket of §3 audit batch. Touches 9 policies (1.04 §9.1 amendment + 8 Ch 3 / Ch 4 policies) plus 4.01 §6.1 substantive amendment. Validator review at execution time recommended (R1 + R2 minimum on 4.01 §6.1 amendment).

---

## Out-of-Scope (deferred)

- **D18 (2.01 deprecated catch-all label).** Covered by existing **#356**. No new ticket.
- **D19 (5.06 Redmine product name in §3).** Absorbs at Phase 6 Entry 45 tightening per Pattern #6. No separate §3 audit ticket.

---

## Ticket Package (locked)

§3 audit uses ticket letter codes **I, J, K1, K2, L, M, N** (continuing from §2's H).

| Code | Class | Title | Scope | Labels |
|------|-------|-------|-------|--------|
| **I (#492)** | D11 + D12 | `[§3 audit] §3 chained / multi-sentence obligation decomposition per 1.04 §6.5 single-directive rule (18 policies / 23 instances)` | 1.03, 1.13, 3.03, 3.05, 3.06, 3.07, 3.08, 3.13, 3.14, 3.15, 3.17, 4.02, 4.04, 4.05, 4.06, 4.07, 5.06 + 3.09 (D11/D12 coupled) | `cross-cutting`, `substantive`, `1.04` |
| **J (#493)** | D13 + D14 | `[§3 audit] §3 Constraint-tag strip + May reframe to 'Shall be authorized to...' (6 policies / 10 obligations)` | 1.11, 2.04, 2.11, 3.06, 3.09, 3.14, 4.03, 4.04 | `cross-cutting`, `substantive`, `1.04` |
| **K1 (#494)** | Q2 | `[1.04 amendment] §6.5 amendment — locked authority sequence and institutional-title ordering sub-rule` | 1.04 only (constitutional amendment, gates K2) | `substantive`, `1.04`, `central` |
| **K2 (#495)** | D15 + D16 | `[§3 audit] §3 authority-order corrections per amended 1.04 §6.5 (25 policies)` | 1.05, 1.07, 1.08, 1.11, 1.13, 1.14, 2.01, 2.02, 2.04, 2.05, 2.06, 2.07, 2.11, 3.01, 3.04, 3.09, 3.12, 3.13, 3.14, 3.17, 4.02, 4.03, 4.04, 4.05, 5.01 | `cross-cutting`, `format`, `1.04` |
| **L (#496)** | D17 | `[§3 audit] §3 Standard prose block strip — 3.15` | 3.15 | `format`, `1.04` |
| **M (#497)** | D20.1, .2, .3, .4, .5, .8 | `[§3 audit] §3 role label normalization — singular / split / acronym / variant / OFA standardization / activity-derivative strip` | 1.06, 1.08, 1.09, 2.09, 2.11, 2.12, 2.13, 3.01, 3.04, 4.05, 5.01 | `cross-cutting`, `substantive`, `1.04` |
| **N (#498)** | D20.6 | `[§3 audit] §3 Incident Commander architecture sweep — accountability/execution split per locked Option B (8 policies + 1.04 §9.1 amendment)` | 1.04 (§9.1), 3.06, 3.09, 4.01, 4.02, 4.03, 4.04, 4.05, 4.06, 4.07 | `cross-cutting`, `substantive`, `1.04`, `central` |

**Filing dependency:** **K1 gates K2.** 1.04 §6.5 amendment must close before K2 reorders execute. K1 + N §9.1 amendment couple into 1.04 v1.6 single patch bump. Other tickets not gated.

**Coupled-policy execution at Phase 5F (single touch absorbs multiple tickets):**
- **3.09:** I + J + K2 + N — 4 tickets in one patch bump
- **3.14:** I + J + K2 — 3 tickets
- **4.04:** I + J + K2 + N — 4 tickets
- **4.05:** I + K2 + M + N — 4 tickets
- **2.11:** J + K2 + M — 3 tickets

### Existing tickets absorbed (no new filings)

| Existing ticket | §3-audit catalog growth |
|-----------------|------------------------|
| **#356** (2.01 group label normalization) | D18 covered — no new ticket. §3 audit confirms 2.01 "All Users of County IT Resources" → "All County Personnel" sweep is already filed. |
| **#264** (role obligation redistribution L1/L2/L3) | Manual-wide root for operational tier work; potential overlap with D20 role variances, particularly 4.05 Support Specialist obligations. |
| **#208** (universal-label sweep root, "All IT Personnel" → "All IO Personnel") | §3 audit confirms most of manual is on canonical form; D18 (2.01) is the remaining outlier covered by #356. |

### v1.6 Amendment Package — additions surfaced by §3 audit

| Item | Source | Status |
|------|--------|--------|
| §6.5 authority sequence amendment | Q2 ruling (May 1, 2026) | Filed under K1 (#494); queued for v1.6 |
| §9.1 IC clarifier addition | Q3 ruling (May 1, 2026) | Filed under N (#498); couples into v1.6 |

---

## Plan / README updates (post-adjudication)

- **TIGHTENING_PLAN.md Phase 5F section.** §3 audit close note recorded (commits `6c0abfef` + `a5aba818`) with floor summary, defect classes D11–D20, ticket I–N filings (#492–#498), Q1 + Q2 + Q3 ruling dispositions.
- **TIGHTENING_PLAN.md Phase 5F intake count.** 8 → 15 tickets.
- **README.md per-policy ticket assignments.** 41 policy rows updated (commits `d9550082` + `681f5146`). State transitions T → T+ for ~25 policies; ticket additions on remaining policies already at T+ or D.

---

## Audit Conclusion

§3 mechanical floor on title format, post-#467 colon placement, and bullet structure is uniformly met. Variance is concentrated in obligation atomicity (D11–D14, 22 policies) and role label canonicalization (D18 + D20, 12+ policies), plus a substantial authority-order reorder set (D15+D16, 25 policies) once locked sequence is applied.

**41 unique policies (68% of in-scope manual) touched by §3 audit findings — heaviest defect surface in the section audit series so far.**

Locked rulings (May 1, 2026): **Q1** Constraint strip + May reframe + always-split combined labels; **Q2** locked authority sequence + flat institutional-title-before-Department-Heads sub-rule (1.04 §6.5 amendment via K1); **Q3** Option B IC architecture — accountability/execution split per LASO precedent (1.04 §9.1 amendment via N).

Filing scope locked May 1, 2026: **I (#492)** (18 policies / 23 instances), **J (#493)** (6 policies / 10 obligations), **K1 (#494)** (1.04 amendment, gates K2), **K2 (#495)** (25-policy reorder), **L (#496)** (1 policy), **M (#497)** (~12 policies), **N (#498)** (9 policies + 1.04 §9.1 amendment — heaviest §3 ticket).

Two constitutional amendments queued for 1.04 v1.6: §6.5 (K1) + §9.1 (N) — couple into single patch bump at Phase 5F execution start.

§3 audit is the third of six Phase 5F section audits. Sections 4–6 follow.
