# Section 2 Audit Report

**Status:** Audit closed — D1–D10 adjudicated May 01, 2026; ticket scope finalized
**Date:** May 01, 2026
**Auditor:** Claude Opus 4.7
**Scope:** 60 numbered policies (Ch 1–5), §2 (Scope) — checked against 1.04 §6.4 + Plan §9.1 Rule #2 (v1.5, locked April 23, 2026; Rule #2 locked April 20, 2026)
**Spec authority:** `01/104.lyx` fetched live at session start
**Audit class:** Observation-only, single-session — no source modifications

---

## Executive Summary

§2 is the policy's applicability declaration and boundary marker. Mechanical compliance varies more than §1 — §2 has more structural surface (single applicability sentence, In Scope subsection, Out of Scope subsection, routing pointer format) and therefore more failure modes.

**Eight defect classes (D1–D8) plus two structure classes (D9–D10) span 22 unique policies (37% of in-scope manual).**

The variance breaks into three layers:

1. **Applicability statement defects (D1 + D2 + D3) — 10 policies.** Wrong opener verb ("governs" vs. "applies to"), multi-sentence applicability statements that smuggle in rationale or scope extensions, parenthetical policy titles in applicability prose. The largest single ticket (#486 / Ticket C).
2. **Routing pointer compliance (D4 + D5 + D6) — 12 policies.** Out of Scope parenthetical-title strip per Rule #2 (3 policies / 8 occurrences), Out of Scope compound-reference splits (7 policies, 8→16 items), In Scope policy-pointer strip (2 policies / 3 items). Mostly mechanical.
3. **Narrative prose and structure violations (D7 + D8 + D9 + D10) — 10 policies.** Standard prose blocks where §2 demands labeled sub-bullets (3.08, 3.09); non-Policy routing pointers (3.08); asymmetric §2 with only Out of Scope and missing In Scope (4 policies); simple-policy exemption claimed but not warranted (4 policies).

**Two architectural rulings (Q1 + Q2) lock the substantive content of D2 sub-class disposition and the D10 simple-policy exemption test.** No new plan-level rule codified — D1–D10 dispositions execute under existing §6.4 spec + Rule #2.

This is the second of six Phase 5F section audits. Defect IDs use **D1–D10** (continuing numbering convention; §1 used F-codes for mechanical-floor framing). Ticket letter codes **C, D, E, F, G, H** (continuing from §1's A, B).

---

## Mechanical Floor

| # | Floor item | Spec authority | Result |
|---|------------|---------------|--------|
| F10 | §2 section label = "Scope" | 1.04 §6.4 | **60/60** ✓ |
| F11 | Applicability statement opens with "This policy applies to..." | 1.04 §6.4 | **51/60** (D1 + D2 surface variances) |
| F12 | Single applicability sentence (no rationale extension, no scope extension) | 1.04 §6.4 | **52/60** (D2 multi-sentence cases) |
| F13 | In Scope and Out of Scope as labeled subsections (when present) | 1.04 §6.4 | **58/60** (D7 narrative prose violations) |
| F14 | Routing pointer form `[Topic]: Policy [X.XX].` | 1.04 §6.4 + Rule #2 | **52/60** (D4 + D5 + D6 surface) |
| F15 | No directives or compliance language in §2 (Exclusion clause) | 1.04 §6.4 | **59/60** (3.08 "shall not" Exclusion block) |
| F16 | No In Scope items contain policy pointers | 1.04 §6.4 | **58/60** (D6 violations) |

§2 length and structure varies by policy operational scope: applicability-only form (1.01, 1.03 — exemption preserved per D10 ruling) through full applicability + In Scope + Out of Scope structure (typical for operationally complex policies). Section structure variance is content-driven, not a defect class.

---

## Defect Catalog

§2 audit defect classes use **D1–D10** (substantive defects; numbering starts at D1 per Phase 5F convention).

### D1 — Wrong applicability opener verb (§6.4)

**Surface:** 1 policy. §2 opens with "This policy governs..." instead of "This policy applies to..."

| Policy | Current | Disposition |
|--------|---------|-------------|
| **4.01** | "This policy governs the establishment, authority, structure, and program framework of the ECIO cybersecurity incident response capability. It applies to all IT systems, services, and infrastructure operated or managed by the Information Operations Department..." | Drop sentence 1 (wrong opener; restates §1 governance scope). Recast sentence 2's "It applies to" as "This policy applies to" — the proper §6.4 single applicability statement. |

### D2 — Multi-sentence applicability (§6.4 — single applicability mandate)

**Surface:** 8 policies. Applicability extends across 2 sentences. Per IT Director ruling May 1, 2026, disposition varies by sub-class content:

| Policy | Sub-class | Sentence 2 (current) | Disposition |
|--------|-----------|---------------------|-------------|
| **1.01** | Rationale strip | "It serves as the strategic anchor point for departmental planning, service delivery, policy enforcement, and cross-departmental coordination." | Strip; relocate to §6 opening if substantively needed |
| **1.03** | Rationale strip | "It governs the cultural and professional baseline for Department interactions, decision-making, and conflict resolution." | Strip; "governs" framing overlaps §1 governance scope; redundant |
| **1.13** | Scope extension migrate | "This policy does not govern commodity off-the-shelf consumables (e.g., toner, cables) where the vendor has no access to County systems, data, or security functions." | Migrate to Out of Scope as bare noun phrase: "Commodity off-the-shelf consumables without access to County systems, data, or security functions." |
| **2.01** | Definition to Glossary | "County IT resources include County-owned, County-managed, and County-provisioned systems and services, including endpoints, networks, applications, cloud services, mobile devices, and data." | Move to Glossary (6.01) as defined term `County IT resources`. Strip from §2. |
| **2.06** | Scope extension fold | "This policy applies regardless of location, medium, or funding source, and regardless of whether the data is held in County-owned, County-managed, or third-party-administered systems." | Fold into sentence 1 as single applicability statement covering personnel + scope-extending qualifiers. |
| **2.08** | Scope extension migrate | "Technical implementation requirements apply to all information systems, networks, endpoints, and supporting infrastructure owned, leased, managed, or operated by Elko County." | Migrate to In Scope items under new In/Out Scope structure created by Ticket H (D10). 2.08 is a cross-ticket coupled fix. |
| **3.02** | §3 pointer strip | "County Department Heads hold limited review and feedback obligations as defined in Section 3." | Strip. Obligations defined in §3 do not need §2 hat-tip. |
| **4.01** | Order issue | "It applies to all IT systems, services, and infrastructure operated or managed by the Information Operations Department, and to all Information Operations personnel." | Recast as proper §6.4 opener (D1 disposition); not strip |

### D3 — Parenthetical policy title in applicability sentence (§6.4)

**Surface:** 2 policies. Applicability sentence contains `Policy X.XX (Policy Title)` form when bare `Policy X.XX` is mandated by §6.4 (§2 does not get the first-use parenthetical convention that body prose receives in §6).

| Policy | Current | Disposition |
|--------|---------|-------------|
| **3.10** | "...packaging, testing, and deployment of applications, drivers, firmware, and associated documentation under **Policy 3.09 (Change Management Policy)**." | Strip parenthetical title: "...under **Policy 3.09**." |
| **5.06** | "...active vendor, contractor, and third-party service provider relationships that fall within the scope of **Policy 1.13 (Supply Chain Risk Management (SCRM) and Vendor Governance)**." | Strip parenthetical title: "...within the scope of **Policy 1.13**." |

### D4 — Out of Scope parenthetical-title strip per Rule #2 (§6.4)

**Surface:** 3 policies / 8 occurrences. Pre-Rule-#2 drift in policies tightened before April 20, 2026.

| Policy | Occurrences | Origin |
|--------|-------------|--------|
| **1.12** | 1 occurrence — "Media Sanitization and Handling Procedures: **Policy 2.12** (Media Protection and Sanitization Policy)." | Tightened April 17, 2026 (pre-Rule-#2) |
| **2.02** | 5 occurrences — Policy 2.04, 1.11, 1.13, 1.12, 2.13 each with parenthetical title | Tightened April 19, 2026 (pre-Rule-#2) |
| **3.07** | 2 occurrences — Policy 3.06, 4.07 each with parenthetical title | Tightened pre-April-20 (Phase 3, April 12) |

**Disposition:** Strip parenthetical title from each. Routing pointer reduces to bare `Policy [X.XX].` form per Rule #2.

### D5 — Out of Scope compound-reference (§6.4 strict singular form)

**Surface:** 7 policies, 8 items decomposing into 16 singular items.

| Policy | Compound item | Split |
|--------|--------------|-------|
| **1.10** | "Technical review of system design and implementation changes: **Policy 3.09** and **Policy 2.15**." | "Technical review of system design and implementation changes: **Policy 3.09**." + "Secure software lifecycle review of design and implementation: **Policy 2.15**." |
| **1.11** | "Access control enforcement mechanisms and identity management: **Policy 2.04** and **Policy 2.05**." | "Access control enforcement mechanisms: **Policy 2.04**." + "Identification and authentication: **Policy 2.05**." |
| **3.04** | "Professional conduct standards: **Policy 1.02** and **Policy 1.03**." | "Professional conduct standards: **Policy 1.02**." + "Cultural baseline and operational ethos: **Policy 1.03**." |
| **3.08** | "Financial controls governing asset acquisition and payment: **Policy 1.10** and **Policy 1.12**." | "Financial controls governing asset acquisition and payment: **Policy 1.10**." + "IT asset lifecycle management: **Policy 1.12**." |
| **3.13** | "Policy documents: **Policy 1.04** and **Policy 1.05**." | "Policy documentation formatting and structural standards: **Policy 1.04**." + "Policy review and update procedures: **Policy 1.05**." |
| **3.13** | "Incident and Problem records: **Policy 3.06** and **Policy 3.07**." | "Operational incident records: **Policy 3.06**." + "Problem investigation records: **Policy 3.07**." |
| **5.03** | "Service level target-setting and SLA deviation thresholds: **Policy 3.01** and **Policy 3.02**." | Split by SLA-vs-deviation aspect |
| **5.07** | "Standard Operating Procedures, playbooks, and operational documentation maintained in the System of Engagement: **Policy 1.04** and **Policy 3.13**." | Split by documentation-taxonomy-vs-knowledge-management aspect |

**Disposition:** Strict singular form per Q1 ruling. Topic recomposition required per pair.

### D6 — In Scope items containing policy pointers (§6.4)

**Surface:** 2 policies / 3 items. §6.4 In Scope: "Capitalized noun phrases identifying what the policy governs... No policy pointers are required, as the governed items reside within this policy."

| Policy | In Scope item with policy pointer | Disposition |
|--------|-----------------------------------|-------------|
| **3.17** | "All asset support classifications — IT-Managed, IT-Supported, and Vendor-Managed — with differentiated obligations for each classification as defined in **Policy 1.12**." | Strip "as defined in **Policy 1.12**" clause. Recompose as bare noun phrase. |
| **5.06** | "Vendor enforcement notification intake from **Policy 5.01**." | Strip "from **Policy 5.01**" — recompose as bare noun phrase. |
| **5.06** | "Vendor compliance data feed to the KPI framework in **Policy 5.04**." | Strip "in **Policy 5.04**" — recompose as bare noun phrase. |

### D7 — Standard prose blocks within §2 (§6.4 narrative prohibition)

**Surface:** 2 policies. §6.4: "When boundaries are drawn, they shall be drawn with labels and sub-bullets, not with narrative prose."

| Policy | Block | Disposition |
|--------|-------|-------------|
| **3.08** | **Exclusion** Standard block: "This policy enforces the CI record update obligation that is the downstream consequence of every authorized change. **It shall not** govern change authorization itself." | Strip block entirely. Boundary already redundant with existing Out of Scope item "Change authorization: **Policy 3.09**." Two violations: narrative prose for boundary + compliance language ("shall not"). |
| **3.09** | **Clarification** Standard block: "The CI record update obligation and catch-up RFC documentation obligation apply following any Emergency change, regardless of whether the change originated from an incident response context, per **Policy 3.08** and Section 6.7 of this policy." | Strip block. Cross-incident-response applicability is operational detail belonging in §6.7, not §2. |

### D8 — Non-Policy routing in Out of Scope (§6.4)

**Surface:** 1 policy / 1 item.

| Policy | Item | Disposition |
|--------|------|-------------|
| **3.08** | Out of Scope item 3: "Active endpoint configuration state, including OS version, patch level, and software inventory: **Endpoint Protection Platform** as defined in Section 6.2." | Convert OoS → InS per IT Director ruling. The EPP framework is governed within 3.08 itself, not externally — In Scope is the correct placement. |

### D9 — Asymmetric §2 (Only Out of Scope, missing In Scope)

**Surface:** 4 policies. §2 articulates what the policy does *not* govern but cannot articulate what it *does* govern.

| Policy | Current state | Disposition |
|--------|--------------|-------------|
| **1.06** | OoS only (4 items) | Add In Scope items: governance bodies, oversight cadence, escalation paths, departmental authority |
| **1.14** | OoS only (6 items) | Add In Scope items: communication boundaries, stakeholder coordination posture, public-facing communication, incident-adjacent reporting |
| **3.03** | OoS only (3 items) | Add In Scope items: operational communication standards, end-user notification, vendor coordination, service status |
| **3.07** | OoS only (2 items) | Add In Scope items: investigation framework, root-cause methodology, permanent remediation, Known Error Lifecycle |

### D10 — Simple-policy exemption claimed but not warranted

**Surface:** 4 policies. §6.4 exemption: "Not every policy requires both In Scope and Out of Scope subsections. Simple policies where the applicability sentence is sufficient may omit them." IT Director ruling May 1, 2026 establishes the exemption test: applies only to genuinely aspirational/cultural policies with no operational mechanics or specific obligations.

**Exemption preserved (genuinely simple):** 1.01 (Mission), 1.03 (Standard Operating Ethos). No edit.

**Exemption revoked, structure required:**

| Policy | Why structure required (operational mechanics or obligations) |
|--------|-----------------------------------------------------------|
| **1.02** | Code of Ethics has substantive obligations: COI disclosures, confidentiality, outside employment standards, public representation |
| **1.08** | Delegation framework: Directed Deputization, non-delegable authority list, lapse remediation windows |
| **1.09** | Risk Management: Risk Register lifecycle, risk-acceptance ladder, RAM-Prohibition, treatment planning |
| **2.08** | System Integrity: technical implementation requirements (per D2 migrate from sentence 2), continuous monitoring obligations |

---

## Adjudication Queue — RESOLVED

### Q1 — D2 disposition by content sub-class, locked May 1, 2026

**Question:** D2 surfaces 8 multi-sentence applicability statements with heterogeneous content. Should all 8 receive identical disposition (e.g., universal strip), or content-class-specific dispositions?

**Ruling:** **Per content class.** Generic strip would lose substantive content (scope extensions, definitions, scope qualifiers) that belongs elsewhere in the policy. Five sub-classes:
- **Rationale strip** — sentence 2 explains why (1.01, 1.03). Strip.
- **Scope extension migrate** — sentence 2 extends Out of Scope (1.13, 2.06, 2.08). Migrate to OoS or fold into sentence 1.
- **Definition to Glossary** — sentence 2 defines a term (2.01). Move to Glossary.
- **§3 pointer strip** — sentence 2 hat-tips §3 obligations (3.02). Strip.
- **Order issue** — sentence 1 wrong opener (4.01, also D1). Drop sentence 1; recast sentence 2.

**Disposition:** Filed under ticket C (#486) — applicability cleanup. Per-policy treatment per sub-class.

### Q2 — D10 simple-policy exemption test, locked May 1, 2026

**Question:** Which policies legitimately qualify for the §6.4 simple-policy exemption (applicability statement only, no In/Out Scope structure)?

**Ruling:** **Operational mechanics + specific obligations test.** Policies generating operational artifacts (Risk Register, COI disclosures, exception logs, etc.) or imposing specific role obligations require structural compliance regardless of how the §2 currently reads. Genuinely aspirational/cultural policies (Mission, Operating Ethos) qualify.

| Policy | Has operational mechanics? | Has specific obligations? | Exemption verdict |
|--------|---------------------------|--------------------------|-------------------|
| 1.01 Mission | No | No | **Preserved** |
| 1.02 Code of Ethics | Yes (COI disclosures) | Yes | **Revoked** |
| 1.03 Standard Operating Ethos | No | No | **Preserved** |
| 1.08 Delegation of Authority | Yes (DD framework) | Yes | **Revoked** |
| 1.09 Risk Management | Yes (Risk Register) | Yes | **Revoked** |
| 2.08 System Integrity | Yes (technical implementation) | Yes | **Revoked** |

**Disposition:** Filed under ticket H (#491) — §2 structure additions. 4 policies gain In/Out Scope structure (1.02, 1.08, 1.09, 2.08); 4 policies (D9 group: 1.06, 1.14, 3.03, 3.07) gain In Scope to balance asymmetric §2.

---

## Out-of-Scope (deferred)

§2 audit produces no out-of-scope deferrals. All D1–D10 findings file under tickets C through H or absorb existing tickets (no absorption occurred at §2 audit close).

---

## Ticket Package (locked)

§2 audit uses ticket letter codes **C, D, E, F, G, H** (continuing from §1 audit's A, B).

| Code | Class | Title | Scope | Labels |
|------|-------|-------|-------|--------|
| **C (#486)** | D1 + D2 + D3 | `[§2 audit] §2 applicability statement cleanup — wrong opener, multi-sentence, parenthetical titles (10 policies)` | 1.01, 1.03, 1.13, 2.01, 2.06, 2.08, 3.02, 3.10, 4.01, 5.06 | `cross-cutting`, `substantive`, `1.04` |
| **D (#487)** | D4 | `[§2 audit] §2 Out of Scope parenthetical-title strip per Rule #2 (3 policies, 8 occurrences)` | 1.12, 2.02 (×5), 3.07 (×2) | `cross-cutting`, `format` |
| **E (#488)** | D5 | `[§2 audit] §2 Out of Scope compound-reference split per 1.04 §6.4 strict singular form (7 policies, 8 → 16 items)` | 1.10, 1.11, 3.04, 3.08, 3.13 (×2), 5.03, 5.07 | `cross-cutting`, `format`, `1.04` |
| **F (#489)** | D6 | `[§2 audit] §2 In Scope policy-pointer strip per 1.04 §6.4 (2 policies, 3 items)` | 3.17, 5.06 (×2) | `cross-cutting`, `format`, `1.04` |
| **G (#490)** | D7 + D8 | `[§2 audit] §2 narrative prose blocks (Exclusion, Clarification) and non-Policy routing strip — 3.08, 3.09` | 3.08, 3.09 | `cross-cutting`, `substantive`, `1.04` |
| **H (#491)** | D9 + D10 | `[§2 audit] §2 structure additions — In/Out Scope where missing or asymmetric (D9 + D10, 8 policies)` | 1.02, 1.06, 1.08, 1.09, 1.14, 2.08, 3.03, 3.07 | `cross-cutting`, `substantive`, `1.04` |

**Filing dependency:** None of C–H is gated. Coupled-policy execution at Phase 5F (single touch absorbs multiple tickets):
- **3.07:** D + H (Rule #2 strip + In Scope addition)
- **3.08:** E + G (compound split + Exclusion strip + EPP→InS)
- **2.08:** C + H (sentence-2 migrate + structure creation; H creates the In Scope target, C migrates the content)
- **5.06:** C + F (parenthetical strip + In Scope pointer strip; state stays D until normal Phase 6 entry 45 tightening)

### Existing tickets absorbed (no new filings)

§2 audit produces no absorption into existing tickets.

---

## Plan / README updates (post-adjudication)

- **TIGHTENING_PLAN.md Phase 5F section.** §2 audit close note recorded (commit `f2cc5241`) with floor summary, defect classes D1–D10, ticket C–H filings (#486–#491), Q1 + Q2 ruling dispositions.
- **TIGHTENING_PLAN.md Phase 5F intake count.** 2 → 8 tickets.
- **README.md per-policy ticket assignments.** 28 policy rows updated (commit `25753471`). State transitions T → T+ for 17 policies; ticket additions on 11 already-T+ or D-state policies.

---

## Audit Conclusion

§2 mechanical floor varies more than §1 — §2's structural surface (single applicability + In Scope subsection + Out of Scope subsection + routing pointer format) creates more failure modes than §1's single-paragraph form. 22 unique policies (37% of in-scope manual) carry at least one §2 defect.

Variance distributes across applicability-statement defects (D1–D3, 10 policies), routing-pointer compliance (D4–D6, 12 policies), and narrative/structure violations (D7–D10, 10 policies).

Locked rulings (May 1, 2026): **Q1** per-content-class disposition for D2 multi-sentence applicability; **Q2** simple-policy exemption test ruling — operational mechanics + specific obligations test; preserves 1.01 / 1.03; revokes 1.02 / 1.08 / 1.09 / 2.08.

Filing scope locked May 1, 2026: **C (#486)** (10 policies), **D (#487)** (3 policies / 8 occurrences), **E (#488)** (7 policies, 8→16 items), **F (#489)** (2 policies / 3 items), **G (#490)** (2 policies), **H (#491)** (8 policies — heaviest §2 ticket; per-policy authorship).

§2 audit is the second of six Phase 5F section audits. Sections 3–6 follow.
