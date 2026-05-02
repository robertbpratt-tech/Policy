# Section 5 Audit Report

**Status:** Audit closed — Q1–Q6 + bonus title verification adjudicated May 01, 2026; ticket scope finalized
**Date:** May 01, 2026
**Auditor:** Claude Opus 4.7
**Scope:** 60 numbered policies (Ch 1–5), §5 (References) — checked against 1.04 §6.7 + §6.11 (v1.5, locked April 23, 2026)
**Spec authority:** `01/104.lyx` fetched live at session start
**Audit class:** Observation-only, single-session — no source modifications

---

## Executive Summary

§5 is the policy's references section — Cited References (citations directly invoked in body §1–§4 + §6) and Framework Alignment (governance-landscape positioning regardless of body citation). Mechanical compliance is **uniform on the structural floor** (every policy has §5 Subsection*, both subsection labels present, no narrative prose anywhere in §5, no terminal periods on citation lines, no bolding within §5 Itemize bullets, all ECIO Policy/Appendix references use CommandInset ref, no citation outside a labeled subsection, cross-category ordering uniform compliant). ~1,700 citations across the manual.

**Three defect classes (D28–D30) span 23 unique policies (38% of T-state corpus).** Variance breaks into three layers:

1. **Within-category sub-ordering (D28) — 11 occurrences across 7 policies.** Three sub-classes: CJIS heterogeneous-form ordering (legacy "Section 5.X.Y.Z" mixed with v6.0 control-family form — 5 policies); NIST CSF function order in 4.01 (RS subcategories appearing after RC entries — 5 occurrences); ITIL alphabetical in 2.10.
2. **Default-placement anomalies (D29) — 5 occurrences across 4 policies.** ECIO Policy refs in Framework Alignment (2.15, 4.03, 4.05); COBIT 2019 ref in Cited References (3.14). Each requires body-cite test verification before resolution; per IT Director ruling, filed as four individual tickets (#517–#520) rather than folded into broader #355 sweep — belt-and-suspenders against being missed.
3. **Citation syntax compliance (D30) — 34 occurrences across 21 policies.** Five sub-classes: CJIS dropped-"Section" word in recent Phase 6 canonicals (D30.1); publication-level NIST SP references with no control ID (D30.2 — 12 occurrences across 8 policies); CJIS Appendix references unaccommodated by spec (D30.3 — 4 occurrences); NIST CSF Category-level reference without Subcategory `-NN` suffix (D30.4 — 3.12 only); NIST SP RMF-step reference (D30.5 — 5.05 only).

**Two surprises surfaced at audit:**

- **Recent Phase 6 canonicals depart from §6.11 spec.** 5.02 v2.0 (Apr 29), 5.03 v2.0 (Apr 30), 5.05 v2.0 (May 1), 5.07 D-state all drop the "Section" word from CJIS citations: spec form is `CJIS Security Policy v6.0: Section AC-1 (Topic)`, recent canonical is `CJIS Security Policy v6.0: AC-1 (Topic)`. 12 entries. Per Q4 ruling, the recent canonical wins via §6.11 amendment.
- **§6.11 has spec gaps the corpus is already filling.** Publication-level NIST SP references (12 occurrences across 8 policies) and CJIS Appendix references (4 occurrences) don't match any §6.11 format string. These aren't incorrect citations; they're legitimate references the spec's per-category format strings don't accommodate. The 4.01–4.07 IR pipeline all cite NIST SP 800-61 Rev. 3 at publication level (since IR is the whole publication's domain, not a single control). The CJIS Appendix H (Security Addendum) and Appendix G.X (technical guidance) are substantive normative material in CJIS v6.0 with no Section-level equivalent.

**One architectural amendment locked May 01, 2026:**

- **§6.11 amendment (#515).** Five sub-changes (E1–E5): **(E1)** CJIS citation form drops "Section" word + specifies v6.0 control-family identifier (legacy section numbering prohibited); **(E2)** CJIS Appendix references permitted; **(E3)** publication-level NIST SP references permitted (parenthesized form, hybrid forms prohibited); **(E4)** NIST SP 800-37 RMF-step references permitted; **(E5)** NIST CSF Subcategory `-NN` suffix required.

§6.11 amendment couples into 1.04 v1.5 → v1.6 release alongside #494, #498, #506, #509 — **five-amendment v1.6 single-release** at §5 audit close.

**One existing ticket scope-amended:**

- **#355** (Manual-wide LRDA citation verification sweep) **→** Manual-wide reference verification sweep — body-cite test + citation accuracy (all categories). Per Q1 ruling, scope expanded from LRDA-only to all-categories + body-cite test compliance with 1.04 §6.7. Title and body amended.

**Bonus title verification surfaced one withdrawn-document remediation:**

- **NIST SP 800-88 Rev. 1** was withdrawn September 26, 2025 and superseded by Rev. 2. Manual cites Rev. 1 in 1.12 §5 and 2.12 §5 — both load-bearing references for media sanitization governance. Ticket JJ (#516) covers the substitution + execution-time alignment spot-check.
- **NIST SP 800-181 Rev. 1** citation in 1.07 has title and parenthetical inverted ("NICE Workforce Framework for Cybersecurity" vs. official "Workforce Framework for Cybersecurity (NICE Framework)"). Per IT Director option (i) ruling, canonical form preserves nested parens: `NIST SP 800-181 Rev. 1 (Workforce Framework for Cybersecurity (NICE Framework))`.
- Three other publications carry truncated titles (800-37 r2, 800-61 r3, 800-137); 800-30 r1 verified accurate.

This is the fifth of six Phase 5F section audits. Defect IDs use **D28–D30** (continuing from §4's D27). Ticket letter codes **AA, BB, CC, DD, EE, II, JJ, KK, LL, MM, NN** (continuing from §4's O–Z; double-letter convention adopted at §5; FF / GG / HH skipped at filing time).

---

## Mechanical Floor

| # | Floor item | Spec authority | Result |
|---|------------|---------------|--------|
| F33 | §5 section label = "References" | 1.04 §6.7 | **60/60** ✓ |
| F34 | Both Cited References + Framework Alignment subsection labels present | 1.04 §6.7 | **60/60** ✓ |
| F35 | No narrative prose in §5 (Itemize-only beyond labels) | 1.04 §6.7 | **60/60** ✓ |
| F36 | All citations placed under a labeled subsection | 1.04 §6.7 | **60/60** ✓ |
| F37 | No terminal periods on citation lines | 1.04 §6.7 | **60/60** ✓ |
| F38 | No bolding within §5 Itemize bullets | 1.04 §6.7 | **60/60** ✓ |
| F39 | ECIO Policy/Appendix references use CommandInset ref | 1.04 §6.7 | **all instances** ✓ |
| F40 | Cross-category ordering compliant within each subsection | 1.04 §6.11 | **60/60** ✓ |

§5 mechanical floor is the cleanest of any audited section across the manual. The §6.7 structural skeleton holds tight at all eight tested layers; cross-category ordering (the categorical-sequence rule from §6.11) is uniformly honored within both Cited and Framework subsections. Defect surface concentrates at the **citation-syntax layer** (§6.11 format string compliance — D30) and the **within-category sub-ordering layer** (D28), with a small placement surface (D29) flagged for body-cite-test resolution.

---

## Defect Catalog

§5 audit defect classes use **D28–D30** (continuing from §4's last defect D27).

### D28 — Within-category sub-ordering violations (§6.11)

**Surface:** 11 occurrences across 7 policies. Three sub-classes.

#### D28.1 — CJIS heterogeneous-form ordering (5 occurrences across 5 policies)

Five policies mix legacy "Section 5.X.Y.Z" CJIS citations with v6.0 control-family citations ("AC-1", "IR-6", etc.) within a single CJIS group. The two forms do not sort coherently — Section-numbering and control-family-IDs are different identifier schemes.

| Policy | Subsection | Trailing entry (out of order) | Preceding entry |
|--------|-----------|-------------------------------|-----------------|
| 1.09 | Framework | Section RA-1 | Section 5.X.Y.Z |
| 1.11 | Framework | Section SC-13 | (MP-prefix entry) |
| 1.14 | Cited | Section IR-6 | Section 5.X |
| 2.05 | Cited | Section IA-2 | Section 5.20.7.3 |
| 2.06 | Cited | Section IR-6 | Section 4 |

**Per Q2 ruling (May 01, 2026):** Migrate to v6.0 control-family form. Architectural codification via §6.11 amendment E1 (CJIS form drops "Section" + specifies v6.0; legacy section numbering prohibited). Substantive — per-citation body-content review per ticket AA.

#### D28.2 — NIST CSF function order in 4.01 (5 occurrences)

4.01 §5 Framework Alignment NIST CSF entries: five RS-function subcategories (RS.CO-02, RS.MA-01, RS.MA-02, RS.MA-03, RS.MA-04) appear AFTER an RC-function entry, violating the GV → ID → PR → DE → RS → RC function order.

**Disposition:** Mechanical fix — relocate RS block before RC block.

#### D28.3 — ITIL alphabetical in 2.10 (1 occurrence)

"ITIL v4: Change Enablement Practice" appears after "ITIL v4: Service Configuration Management Practice." Alphabetical: change < service.

**Disposition:** Mechanical fix — swap.

### D29 — Default-placement anomalies (§6.7)

**Surface:** 5 occurrences across 4 policies.

| Policy | Citation | Subsection | Default | Anomaly |
|--------|----------|-----------|---------|---------|
| 2.15 | ECIO Policy 1.07 | Framework | Cited | ECIO Policy in Framework |
| 3.14 | COBIT 2019: BAI02 | Cited | Framework | COBIT in Cited |
| 4.03 | ECIO Policy 1.09 | Framework | Cited | ECIO Policy in Framework |
| 4.05 | ECIO Policy 1.09 | Framework | Cited | ECIO Policy in Framework |
| 4.05 | ECIO Policy 1.12 | Framework | Cited | ECIO Policy in Framework |

Each anomaly is structurally valid only if the body-cite test confirms the placement:

- ECIO Policy in Framework is correct only if the policy is NOT body-cited.
- COBIT in Cited is correct only if COBIT BAI02 is body-cited by identifier.

**Per IT Director ruling May 01, 2026:** Filed as **four individual tickets** (#517–#520) rather than folded into broader #355 sweep. Belt-and-suspenders disposition. If #355 catches and resolves at Phase 9, the four individual tickets close as duplicates.

### D30 — Citation syntax compliance with §6.11 format strings

**Surface:** 34 occurrences across 21 policies. Five sub-classes.

#### D30.1 — CJIS dropped-"Section" word (12 occurrences across 5 policies)

Spec form: `CJIS Security Policy v[Version]: Section [ID] ([Topic])`. Recently-tightened policies use a dropped form: `CJIS Security Policy v6.0: AC-1 (Topic)` without the "Section " word.

| Policy | Source | Affected entries |
|--------|--------|------------------|
| 5.02 | Phase 6 Entry 40 (April 29) | 6 entries (CA-1, CA-2, CA-2(1), CA-7, CA-7(1), AU-9) |
| 5.03 | Phase 6 Entry 42 (April 30) | 3 entries (CA-5, CA-7, IR-6) |
| 5.05 | Phase 6 Entry 44 (May 1) | 3 entries (CA-1, CA-6, CA-7) |
| 5.07 | D-state | 1 entry (CA-1) |
| 1.10 | older legacy | 1 entry (SA-9) |

**Per Q4 ruling (May 01, 2026):** Recent canonical wins. Amend §6.11 to drop the "Section " requirement (codified via §6.11 amendment E1). Post-amendment, 5.02 / 5.03 / 5.05 / 5.07 entries are automatically spec-compliant. Residual 1.10 instance covered by ticket CC.

#### D30.2 — Publication-level NIST SP references with no control ID (12 occurrences across 8 policies)

Spec format requires a control ID. 12 citations reference the publication as a whole rather than a specific control:

| Policy | Citation |
|--------|----------|
| 1.07 | NIST SP 800-181 Rev. 1 (NICE Workforce Framework for Cybersecurity) — title also inverted; see bonus verification |
| 1.09 | NIST SP 800-30 Rev. 1: (Guide for Conducting Risk Assessments) |
| 1.09 | NIST SP 800-37 Rev. 2: (Risk Management Framework for Information Systems and Organizations) |
| 1.09 | NIST SP 800-137: (Information Security Continuous Monitoring) |
| 1.12 | NIST SP 800-88 Rev. 1 (Guidelines for Media Sanitization) — also withdrawn-document remediation; see bonus verification |
| 2.12 | NIST SP 800-88 Rev. 1 (Guidelines for Media Sanitization) — same |
| 4.01–4.07 | NIST SP 800-61 Rev. 3 (5 instances; "Cyber" vs "Cybersecurity" wording inconsistency between 4.01/4.06 and 4.03/4.04/4.05/4.07) |
| 5.06 | NIST SP 800-37 Rev. 2: (Risk Management Framework for Information Systems and Organizations) |

Three forms in active use: parenthesized clean (`NIST SP 800-88 Rev. 1 (Title)`), colon-no-parens (`NIST SP 800-61 Rev. 3: Title`), hybrid colon-then-parens (`NIST SP 800-37 Rev. 2: (Title)`). Hybrid form is awkward.

**Per Q5 ruling (May 01, 2026):** Mixed approach — amend §6.11 to permit `NIST SP [Number] Rev. [Revision] ([Full Publication Title])` form for foundational documents (parenthesized canonical; hybrid forms prohibited). Codified via §6.11 amendment E3.

**Embedded sub-issue (D30.2.a):** "Cyber Risk Management" vs "Cybersecurity Risk Management" inconsistency across 4.01–4.07. NIST SP 800-61 Rev. 3 official subtitle is "…for Cybersecurity Risk Management." 4.01 and 4.06 use truncated "Cyber"; 4.03 / 4.04 / 4.05 / 4.07 use spec-correct "Cybersecurity". Per Q6 ruling: standardize on "Cybersecurity" mechanically.

#### D30.3 — CJIS Appendix references (4 occurrences across 4 policies)

Spec format requires "Section [ID]" but does not accommodate "Appendix" references:

| Policy | Citation |
|--------|----------|
| 1.10 | CJIS Security Policy v6.0: Appendix H (CJIS Security Addendum and Certification) |
| 1.11 | CJIS Security Policy v6.0: Appendix G.3 (Cloud Computing) |
| 1.13 | CJIS Security Policy v6.0: Appendix H (CJIS Security Addendum and Certification) |
| 2.14 | CJIS Security Policy v6.0: Appendix G.4 (Mobile Device Guidance — Cellular Service Abroad) |

CJIS v6.0 has appendix-level normative material — Appendix H = Security Addendum, Appendix G.X = various technical guidance areas. These are legitimate citation targets.

**Per Q5 ruling (May 01, 2026):** Amend §6.11 to permit `CJIS Security Policy v[Version]: Appendix [ID] ([Topic])`. Codified via §6.11 amendment E2.

#### D30.4 — NIST CSF Category-level reference (1 occurrence in 3.12)

3.12 §5 Framework Alignment: "NIST CSF 2.0: DE.CM (Continuous Monitoring)" references the Category (DE.CM) rather than a specific Subcategory (DE.CM-NN).

**Per Q5 ruling (May 01, 2026):** Restructure (not amend). Replace with the specific Subcategory the policy maps to (DE.CM-01, -02, -03, -06, or -09). Substantive — needs body content review to identify the right subcategory. §6.11 amendment E5 tightens the spec to make the `-NN` suffix explicitly required.

#### D30.5 — NIST SP RMF-step pointer (1 occurrence in 5.05)

5.05 v2.0 §5: "NIST SP 800-37 Rev. 2: Authorize step". Phase 6 Entry 44 entry note (May 1) records this as an intentional R3 tightening: *"NIST SP 800-37 Rev. 2 entry tightened from generic publication parenthetical to specific 'Authorize step' pointer (R3)."*

The intent is clear (point to the specific RMF step relevant to 5.05's authorization architecture) but the format doesn't match §6.11's required `[Control ID] ([Control Title])` syntax. RMF steps are not controls; they're framework lifecycle stages.

**Per Q5 ruling (May 01, 2026):** Amend §6.11 to permit `NIST SP 800-37 Rev. [Revision]: [Step Name] step` form for RMF lifecycle pointers. Codified via §6.11 amendment E4.

---

## Adjudication Queue — RESOLVED

### Q1 — Body-cite test execution scope, locked May 01, 2026

**Question:** The 1.04 §6.7 body-cite rule is structural ("Cited References shall be body-cited; Framework Alignment shall not appear by identifier in body"). It overlaps the framework-verification work that #355 (LRDA citation verification sweep) was filed to handle. Where does the test land?

**Ruling:** **Expand #355 to verify EACH reference, not just LRDA.** All citation categories + body-cite test compliance with 1.04 §6.7.

**Disposition:** #355 scope amended (title and body). Title becomes "Manual-wide reference verification sweep — body-cite test + citation accuracy (all categories)." Body extended with scope amendment section detailing each citation category (NRS, NAC, LRDA, CJIS, NIST CSF, NIST SP, COBIT, ITIL) plus body-cite test rules and default-placement rules.

### Q2 — D28.1 CJIS heterogeneous-form, locked May 01, 2026

**Question:** Five policies carry CJIS citations in two different identifier schemes within a single category — legacy "Section 5.X.Y.Z" and v6.0 control-family ("AC-1"). What's the architecturally-correct resolution?

**Ruling:** **Use new format (v6.0 control-family form), not legacy Section 5.X.Y.Z.** Architectural codification via §6.11 amendment E1 (legacy section numbering prohibited).

**Disposition:** Filed under ticket AA (#510). Per-citation substantive review — CJIS v6.0 reorganized older policy sections into NIST SP 800-53-style control families; most legacy section content maps to one or more specific v6.0 controls. Gated on §6.11 amendment landing.

### Q3 — D28.2 / D28.3 mechanical sub-ordering fixes, locked May 01, 2026

**Question:** 4.01 NIST CSF function order (relocate RS block before RC block); 2.10 ITIL alphabetical (swap Change Enablement and Service Configuration Management). Mechanical fixes?

**Ruling:** **OK — absorb to Phase 5F.**

**Disposition:** Filed under ticket BB (#511).

### Q4 — D30.1 CJIS dropped-"Section" word, locked May 01, 2026

**Question:** 12 entries in recently-tightened policies (5.02 v2.0, 5.03 v2.0, 5.05 v2.0, 5.07 D-state, 1.10) drop the "Section" word from CJIS citations. Sweep canon to spec, or amend spec to canon?

**Ruling:** **Amend 1.04 first, then sweep residual older instances.** §6.11 amendment makes recent Phase 6 canonical (no "Section" prefix) the new spec.

**Auditor rationale (accepted):** The Phase 6 entries 40–44 represent the most-considered current canonical; "Section AC-1" reads as scaffolded redundancy where "AC-1" is unambiguous; aligns with the NIST SP citation form which doesn't carry a "Section" prefix either.

**Disposition:** Codified via §6.11 amendment E1 (Ticket II / #515). Residual 1.10 instance filed under ticket CC (#512).

### Q5 — D30.2 / D30.3 / D30.5 spec-gap accommodation, locked May 01, 2026

**Question:** Three citation forms in active use across the manual don't fit §6.11 format strings: publication-level NIST SP references (12); CJIS Appendix references (4); NIST SP 800-37 RMF-step pointer (1). Amend §6.11, restructure citations, or mixed?

**Ruling:** **OK — mixed approach.** Amend §6.11 to permit publication-level NIST SP, CJIS Appendix, NIST SP 800-37 RMF-step forms; restructure D30.4 NIST CSF Category-level via content review.

**Disposition:** Codified via §6.11 amendment E2 (CJIS Appendix), E3 (publication-level NIST SP), E4 (NIST SP RMF-step), E5 (NIST CSF Subcategory required). Tickets DD (#513, citation reformatting) and EE (#514, NIST CSF Category-level → Subcategory restructure for 3.12). Both gated on §6.11 amendment landing.

### Q6 — "Cyber" → "Cybersecurity" Risk Management standardization, locked May 01, 2026

**Question:** 4.01 and 4.06 use truncated "Cyber Risk Management"; 4.03 / 4.04 / 4.05 / 4.07 use spec-correct "Cybersecurity Risk Management." NIST SP 800-61 Rev. 3 official subtitle is "…for Cybersecurity Risk Management." Mechanical fix?

**Ruling:** **Yes, fix them mechanically.**

**Disposition:** Subsumed into ticket DD (#513). Two-policy patch (4.01, 4.06).

### Bonus title verification (locked May 01, 2026)

IT Director authorized verification of full and official titles for all publication-level NIST SP references at audit close.

| Publication | Manual citation | Official title (verified) | Status |
|-------------|-----------------|---------------------------|--------|
| 800-30 Rev. 1 | "Guide for Conducting Risk Assessments" | Same | ✓ accurate |
| 800-37 Rev. 2 | "Risk Management Framework for Information Systems and Organizations" | "…Organizations: **A System Life Cycle Approach for Security and Privacy**" | ⚠ missing subtitle |
| 800-61 Rev. 3 | "…for [Cyber/Cybersecurity] Risk Management" | "…for Cybersecurity Risk Management: **A CSF 2.0 Community Profile**" | ⚠ missing subtitle + "Cyber"→"Cybersecurity" |
| 800-88 Rev. 1 | "Guidelines for Media Sanitization" | Same | ⚠⚠ **Rev. 1 WITHDRAWN Sep 26, 2025; superseded by Rev. 2** |
| 800-137 | "Information Security Continuous Monitoring" | "Information Security Continuous Monitoring **(ISCM) for Federal Information Systems and Organizations**" | ⚠ truncated |
| 800-181 Rev. 1 | "NICE Workforce Framework for Cybersecurity" | "Workforce Framework for Cybersecurity **(NICE Framework)**" | ⚠ title and parenthetical inverted |

**Two findings beyond simple title fixes:**

- **NIST SP 800-88 Rev. 1 is withdrawn.** NIST withdrew Rev. 1 on September 26, 2025 and replaced with Rev. 2 the same day. Manual cites Rev. 1 in 1.12 §5 and 2.12 §5 — both load-bearing references for media sanitization governance. **Per IT Director ruling:** correct to latest supported version (Rev. 2). Spot-check during execution to verify body-content alignment with Rev. 2's structure. Filed under ticket JJ (#516).
- **NIST SP 800-181 Rev. 1 citation in 1.07 is structurally wrong.** "NICE Workforce Framework for Cybersecurity" is neither the title (*"Workforce Framework for Cybersecurity"*) nor the parenthetical (*"(NICE Framework)"*) — it's a hybrid reconstruction. **Per IT Director option (i) ruling:** preserve nested parens despite awkwardness — accuracy wins. Final form: `NIST SP 800-181 Rev. 1 (Workforce Framework for Cybersecurity (NICE Framework))`. Filed under ticket DD (#513).

---

## Out-of-Scope (deferred)

- **#355 expanded scope execution.** Phase-9-deferred per existing #355 scope. Body-cite test compliance + citation accuracy verification across all categories runs at Phase 9, not Phase 5F.
- **D29 placement-anomaly absorption into #355.** Although #355 covers the architectural surface, IT Director ruled D29 cases filed individually (#517–#520) rather than folded into #355 — belt-and-suspenders against being missed. If #355 catches and resolves at Phase 9, the four individual tickets close as duplicates.

---

## Ticket Package (locked)

§5 audit uses ticket letter codes **AA, BB, CC, DD, EE, II, JJ, KK, LL, MM, NN** (continuing from §4's O–Z; double-letter convention adopted at §5; FF / GG / HH skipped at filing time).

| Code | Class | Title | Scope | Labels |
|------|-------|-------|-------|--------|
| **AA (#510)** | D28.1 | `[§5 audit] D28.1 — Migrate CJIS legacy Section 5.X.Y.Z citations to v6.0 control-family form (5 policies)` | 1.09, 1.11, 1.14, 2.05, 2.06 | `substantive`, `ch1-governance`, `ch2-security` (gated on #515) |
| **BB (#511)** | D28.2 + D28.3 | `[§5 audit] D28.2 + D28.3 — Mechanical sub-ordering fixes (4.01, 2.10)` | 4.01 (NIST CSF function order), 2.10 (ITIL alphabetical) | `format`, `ch2-security`, `ch4-incident-response` |
| **CC (#512)** | D30.1 | `[§5 audit] D30.1 — Sweep CJIS dropped-Section sweep on 1.10 (1 policy)` | 1.10 | `format`, `ch1-governance` (gated on #515) |
| **DD (#513)** | D30.2 + D30.3 + D30.5 + Q6 + titles | `[§5 audit] D30.2 + D30.3 + D30.5 + title corrections — Reformat publication-level / Appendix / RMF-step citations + verify titles (~15 policies)` | 1.07, 1.09, 1.10, 1.11, 1.13, 2.14, 4.01, 4.02, 4.03, 4.04, 4.05, 4.06, 4.07, 5.05, 5.06 | `substantive`, `1.04`, `global`, `cross-cutting` (gated on #515; **heaviest §5 ticket**) |
| **EE (#514)** | D30.4 | `[§5 audit] D30.4 — Restructure NIST CSF Category-level reference to specific Subcategory (3.12)` | 3.12 | `substantive`, `1.04`, `ch3-service-management` (gated on #515) |
| **II (#515)** | §6.11 amendment | `[1.04] §6.11 amendment to v1.6 — CJIS Section-drop + v6.0 form lock; CJIS Appendix permission; publication-level NIST SP permission; NIST SP RMF-step permission; NIST CSF Subcategory required` | 1.04 | `1.04`, `central`, `substantive`, `cross-cutting` |
| **JJ (#516)** | Withdrawn-document | `[§5 audit] NIST SP 800-88 Rev. 1 → Rev. 2 citation update + execution-time alignment spot-check (1.12, 2.12)` | 1.12, 2.12 | `substantive`, `ch1-governance`, `ch2-security` |
| **KK (#517)** | D29 | `[§5 audit] D29 placement verification — 2.15 Framework: ECIO Policy 1.07` | 2.15 | `substantive`, `ch2-security` |
| **LL (#518)** | D29 | `[§5 audit] D29 placement verification — 3.14 Cited: COBIT 2019 BAI02` | 3.14 | `substantive`, `ch3-service-management` |
| **MM (#519)** | D29 | `[§5 audit] D29 placement verification — 4.03 Framework: ECIO Policy 1.09` | 4.03 | `substantive`, `ch4-incident-response` |
| **NN (#520)** | D29 | `[§5 audit] D29 placement verification — 4.05 Framework: ECIO Policy 1.09 + ECIO Policy 1.12` | 4.05 | `substantive`, `ch4-incident-response` |

**Filing dependencies:**
- **AA (#510)**, **CC (#512)**, **DD (#513)**, **EE (#514)** all gate on **II (#515)** landing (§6.11 amendment must be in 1.04 before per-policy citation reformatting begins).
- **II (#515)** couples into v1.6 release alongside #494 (§6.5), #498 (§9.1), #506 (§6.6), #509 (§6.12) — **five-amendment v1.6 single-release** at §5 audit close.

### Existing tickets scope-amended (no new filings)

| Existing ticket | §5-audit-driven amendment |
|-----------------|---------------------------|
| **#355** (Manual-wide LRDA citation verification sweep) | **Title and body amended May 01, 2026** to expand scope from "Manual-wide LRDA citation verification" to "Manual-wide reference verification sweep — body-cite test + citation accuracy (all categories)." Per Q1 ruling. |

### Architectural Codification (no separate ticket — folded into #515)

| Item | Disposition |
|------|-------------|
| **§6.11 amendment** (#515) | Five sub-changes (E1–E5): CJIS Section-drop + v6.0 form lock; CJIS Appendix permission; publication-level NIST SP permission; NIST SP 800-37 RMF-step permission; NIST CSF Subcategory `-NN` suffix required. |

---

## Plan / README updates (post-adjudication)

- **TIGHTENING_PLAN.md Phase 5F section.** §5 audit close note recorded (commit `3f2f6687`, May 1, 2026) with floor summary, defect classes D28–D30, ticket AA–NN filings (#510–#520), Q1–Q6 + bonus title verification ruling dispositions, #355 scope amendment.
- **TIGHTENING_PLAN.md v1.6 amendment list.** Added #515 (§6.11) — package size 4 → 5 amendments at §5 audit close.
- **TIGHTENING_PLAN.md Phase 5F intake count.** 25 → 36 tickets.
- **TIGHTENING_PLAN.md §3 root table + §7 Open Questions narrative.** Updated post-§5-close (commit `b5e7027c`, May 1, 2026) to reflect #355 expanded scope. Sync drift caught during full sync verification across plan / README / live tickets after audit close.
- **README.md per-policy ticket assignments.** 25 policy rows updated (commit `df92134e`, May 1, 2026): 1.04 (#515); 1.07 (#513); 1.09 (#510, #513); 1.10 (#512, #513); 1.11 (#510, #513); 1.12 (#516); 1.13 (#513); 1.14 (#510); 2.05 (#510); 2.06 (#510); 2.10 (#511); 2.12 (#516); 2.14 (#513); 2.15 (#517); 3.12 (#514); 3.14 (#518); 4.01 (#511, #513); 4.02 (#513); 4.03 (#513, #519); 4.04 (#513); 4.05 (#513, #520); 4.06 (#513); 4.07 (#513); 5.05 (#513); 5.06 (#513).
- **README.md Manual-Wide Open Roots table.** Updated post-§5-close (commit `0020777e`, May 1, 2026) to reflect #355 expanded scope.

---

## Audit Conclusion

§5 mechanical floor is uniform across all eight floor items (F33–F40) — the §6.7 structural skeleton holds tight at every tested layer (subsection labels, flat-list-no-prose, no terminal periods, no §5 bolding, ECIO CommandInset refs, no unknown-subsection citations, cross-category ordering). The defect surface is concentrated at the **citation-syntax layer** (§6.11 format string compliance — D30) and the **within-category sub-ordering layer** (D28), with a small placement surface (D29) flagged for body-cite-test resolution.

Locked rulings (May 01, 2026): **Q1** expand #355 to verify each reference (all categories + body-cite test); **Q2** migrate CJIS legacy to v6.0 control-family form; **Q3** mechanical sub-ordering fixes; **Q4** amend §6.11 to drop "Section" prefix from CJIS canonical; **Q5** mixed approach for spec-gap accommodation (publication-level NIST SP, CJIS Appendix, NIST SP RMF-step amendments); **Q6** "Cyber" → "Cybersecurity" mechanical sweep; **bonus title verification** with IT Director ruling on 800-88 Rev. 1 → Rev. 2 substitution and 800-181 Rev. 1 nested-parens preservation.

Architectural codification: **§6.11 amendment** (#515) — five sub-changes E1–E5 — queued for 1.04 v1.5 → v1.6 release.

Filing scope locked May 01, 2026: **AA (#510)** (5 policies; gated on #515), **BB (#511)** (2 policies — mechanical), **CC (#512)** (1 policy; gated on #515), **DD (#513)** (15 policies — heaviest §5 ticket; gated on #515), **EE (#514)** (1 policy; gated on #515), **II (#515)** (constitutional), **JJ (#516)** (2 policies — withdrawn-document remediation), **KK (#517)** / **LL (#518)** / **MM (#519)** / **NN (#520)** (4 individual D29 placement-verification tickets, 4 policies). Plus **#355 scope amendment** (manual-wide reference verification sweep). No new standing decline patterns inscribed; §5 audit absorbs into existing pattern stack and produces architectural amendment via §6.11.

§5 audit is the fifth of six Phase 5F section audits. §6 audit follows.
