# Section 6 Audit Report

**Status:** Audit closed — Q1b + Q2c locked May 02, 2026; ticket scope finalized
**Date:** May 02, 2026
**Auditor:** Claude Opus 4.7
**Scope:** 60 numbered policies (Ch 1–5), §6 (Policy Statement) — checked against 1.04 §6.8, §6.9, §6.10, §6.11, §6.12, §6.14 (v1.5, locked April 23, 2026)
**Spec authority:** `01/104.lyx` fetched live at session start
**Audit class:** Observation-only, single-session — no source modifications

---

## Executive Summary

§6 is the operational core of the manual. Mechanical compliance is **uniform on the structural floor** (subsection numbering, section label, directional phrases, plural-policy form, time/quantity syntax, bold-label-period, nesting depth, cross-policy §6.X depth net of pre-tracked cases). Substantive variance concentrates in three layers:

1. **Targeted prohibited-language drift (D31).** 9 occurrences across 8 files of §6.9 prohibited terms (`responsible for` ×3, `attempt to` ×3, `when necessary` ×2, `timely` ×1) plus one 1.04-internal occurrence (§6.15 Owner definition). The "attempt to" surface forms a recurring cluster (3.04, 3.08, 5.01) all in lateral-comms / replication-prevention contexts.
2. **Terminal-period compliance (D37).** 17 missing terminal periods concentrated in **two policies** — 2.15 §6.2 / §6.4 (12 semicolon-enumeration items, legal-style listing) and 5.06 §6.1 (5 fragment items, no terminal punctuation).
3. **Two architectural questions resolved (Q1b, Q2c)** producing locked ticket scope: §6.8 v1.6 carve-out for conjoined-symmetric directives narrows D40 from 51 candidates to 21 sites across 16 policies; self-reference convention (D42) ruled per-instance Q2c — 19 sites across 4 policies.

Two existing open tickets absorb additional scan output without new ticket filing:
- **#375** absorbs cross-policy §6.X depth catalog growth
- **#509** absorbs v1.6-strip clarifier vocabulary catalog (30 use-sites in §6 alone)

Three candidate items deferred to other workstreams:
- §6.10 acronym protocol sweep → Phase 9H universal-style sweep (out of §6 audit scope per handoff §10)
- §6.10 product-name sweep → covered by ongoing #6 manual-wide ticket
- §6 passive-voice "orphan" detection → heuristic too noisy (most permitted impersonal-subject formatting); case-by-case judgment instead

v1.6 amendment package gains two §6-audit-surfaced sub-amendments: §6.15 Owner definition (micro-amendment) and §6.8 conjoined-symmetric carve-out (five-criterion test (a)–(e) per Q1b ruling).

---

## Mechanical Floor

| # | Floor item | Spec authority | Result |
|---|------------|---------------|--------|
| F1 | §6 section label = "Policy Statement" | 1.04 §6.8 | **60/60** ✓ |
| F2 | §6.X subsection numbering — sequential 6.1, 6.2, … | 1.04 §6.8 | **60/60** ✓ |
| F3 | No directional phrases (`see below`, `see above`, `as described later`, hard-coded page numbers) | 1.04 §6.11 | **0 occurrences** (D32 floor) |
| F4 | No plural `Policies X.XX` form | 1.04 §6.11 | **0 occurrences** (D33 floor) |
| F5 | Time/Quantity syntax — `word (digit) unit` | 1.04 §6.10 | **0 violations** (D35 floor) |
| F6 | Bold labels followed by colon (not period) | 1.04 §6.12 | **0 occurrences** (D38 floor) |
| F7 | Nesting depth ≤ 2 levels | 1.04 §6.12 | **0 violations** (D39 floor) |
| F8 | No new cross-policy §6.X depth (D34) | 1.04 §6.11 / Plan Rule #1 (#375) | **0 new findings**. 2 existing instances (3.12 §6.5 → 3.11 §6.3, 4.01 L2688 → 4.05 §6.2) governed by open tickets #413 and #418. |

§6.X subsection counts vary by policy operational sub-domain breadth: 2 (1.01 Mission, 4.01 IR Master) to 15 (1.04 Constitutional Standard). Preamble block counts vary 0–3, consistent with §6.8 Framing Preamble guidance ("when a policy requires contextual framing"). Variance is structural-content driven, not a defect class.

---

## Defect Catalog

Defect IDs continue from §5 audit (last D30). §6 audit defect classes use **D31–D42**.

### D31 — Prohibited Language (§6.9 — 16-phrase list + standalone "timely"/"reasonable")

**Surface:** 9 occurrences across 8 files. Three sub-pattern clusters.

| File | §6.X | Line | Phrase | Context |
|------|------|------|--------|---------|
| 01/104 | 6.15 | L2499 | `responsible for` | `**Owner**: The role responsible for keeping the document current.` (1.04-internal — see §1.04 Amendment Candidate below) |
| 01/109 | 6.8 | L1493 | `responsible for` | `…Department Head or Elected Official responsible for the affected system.` |
| 01/114 | 6.4 | L1375 | `when necessary` | `…service providers, or partners when necessary to resolve an incident…` |
| 03/304 | 6.3 | L1068 | `attempt to` | `…lateral communications that attempt to circumvent these pathways…` |
| 03/308 | 6.2 | L1206 | `attempt to` | `…System of Engagement shall not attempt to replicate Endpoint Protection…` |
| 04/406 | 6.7 | L2522 | `when necessary` | `…or managed service partners when necessary to resolve an active incident…` |
| 05/501 | 6.4 | L1957 | `attempt to` | `…lateral communications that attempt to circumvent them shall be redirected…` |
| 05/506 | 6.5 | L2515 | `timely` | `…Failure to provide timely notification shall be treated…` |
| 05/506 | 6.6 | L2702 | `responsible for` | `…The contract administrator responsible for the vendor relationship.` |

**Cluster observations.**

- **`responsible for` (×3, plus 1.04-internal):** Recurrence of standing decline #40 surface form (Phase 6 E40 close). 1.09 §6.8, 5.06 §6.6, and 1.04 §6.15 use the verbatim pattern.
- **`attempt to` (×3):** All three instances are in lateral-comms / replication-prevention contexts (3.04, 3.08, 5.01). Three rotations of the same surface form across three files satisfies promotion criteria for a manual-wide pattern lock; surface form rewrites uniformly to active prohibition (`shall not circumvent`, `shall not replicate`).
- **`when necessary` (×2):** 1.14 §6.4 and 4.06 §6.7 — both incident-response coordination contexts. Same construct, paired across the IR architecture.
- **`timely` (×1):** 5.06 §6.5 standalone adjective use; canonical replacement is the `word (digit) unit` deadline form bound to the relevant CJIS notification clock.

**Disposition:** New ticket — letter code **OO** below.

### D32 — Directional Phrases (§6.11)

**Surface: 0 occurrences. Floor confirmed.**

Sanity grep across the 60-file corpus (excluding 1.04 spec discussion) returned no instances of `see below`, `see above`, `as described later`, or hard-coded page numbers. §6.11 is universally honored.

### D33 — Plural "Policies X.XX" (§6.11)

**Surface: 0 occurrences. Floor confirmed.**

Sanity grep returned no plural-form policy citations across the 60-file corpus. §6.11 singular-form rule (`Policy X.XX and Policy Y.YY`, never `Policies X.XX and Y.YY`) is universally honored.

### D34 — Cross-Policy §6.X Depth (§6.11 / Plan Rule #1 / #375)

**Surface: 0 new findings. 2 existing instances tracked under open tickets.**

Two pre-existing cross-policy §6.X depth cases were re-confirmed and require no new ticket:
- **3.12 §6.5 → "Section 6.3 of that policy"** referring to Policy 3.11 — covered by **#413** (open, prose-rewrite pending).
- **4.01 L2688 → "Section 6.2 of Policy 4.05"** — covered by **#418** (open, prose-rewrite pending).

The §6.11 spec explicitly permits self-referential `Section 6.X` pointers ("All internal references shall use absolute numerical pointers (e.g., 'Policy 2.04' or 'Section 6.2')"). Initial-pass scans surfaced 16 candidate hits that resolved to self-references upon §6.X-content matching against each policy's own subsection table — confirmed permitted under §6.11 by direct content correspondence (e.g., 1.09 references its own §6.8 "Risk Acceptance Governance"; 1.11 references its own §6.9 "Records Retention and Disposition"; etc.).

**Disposition:** Catalog growth absorbed into existing #375 (manual-wide concept) — no new ticket. Two pre-tracked instances remain at #413 and #418.

### D35 — Time/Quantity Syntax (§6.10)

**Surface: 0 violations. Floor confirmed.**

The canonical `word (digit) unit` form (e.g., `five (5) business days`, `twenty-four (24) hours`) is universally applied across the 60-file corpus. No bare-digit and no spelled-out-only deadline expressions found.

### D36 — v1.6-Amendment Strip-Candidate Clarifier Vocabulary (§6.12 → #509)

**Surface: 30 occurrences across 20 files.** Catalog feeds existing **#509** absorption.

| Strip-candidate label | §6 occurrences |
|---|---|
| `**Clarification**` | 17 |
| `**Constraint**` | 10 |
| `**Exclusion**` | 3 |

**By-file:** 1.05 (×2), 1.06 (×2), 1.07 (×1), 1.08 (×4), 1.11 (×2), 1.12 (×1), 1.13 (×1), 2.01 (×1), 2.02 (×2), 2.04 (×1), 2.11 (×1), 2.13 (×1), 3.02 (×2), 3.03 (×1), 3.05 (×1), 3.07 (×1), 3.09 (×1), 3.13 (×2), 3.14 (×2), 3.17 (×1).

**Disposition:** No new ticket. §6 catalog feeds **#509** ("[1.04] §6.12 amendment to v1.6 + manual-wide strip of Constraint / Clarification / Exclusion"). When v1.6 amendment lands and the strip-and-restructure sweep executes, these 30 use-sites are the §6-bounded subset of the manual-wide #509 footprint.

### D37 — Missing Terminal Period (§6.12)

**Surface: 17 occurrences across 2 files.**

**2.15 §6.2 (Acquisition Process and Contract Requirements) — 8 findings.** Legal-style enumeration with semicolon terminators, e.g.:
- L1364: `(a) Security and privacy functional requirements;`
- L1370: `(b) Strength of mechanism requirements;`
- L1376: `(c) Security and privacy assurance requirements;`
- (continues through (f) and additional items)

**2.15 §6.4 (Developer Configuration Management) — 4 findings.** Same semicolon-enumeration pattern.

**5.06 §6.1 (Vendor Compliance Record) — 5 findings.** Fragment items with no terminal punctuation at all:
- L1811: `The date of the enforcement action`
- L1817: `The non-compliance identified`
- L1823: `The IT-administrative action taken`
- L1829: `The policy basis`
- L1835: `The affected County systems or services`

Per §6.12: "Every bulleted and sub-bulleted list item shall end with a terminal period, regardless of whether the item is a full sentence or a fragment." The semicolon enumeration in 2.15 is a legal-drafting convention but mechanically violates §6.12. The fragment enumeration in 5.06 is uncontroversial.

**Disposition:** New ticket — letter code **PP** below.

### D38 — Bold-Label-Period (§6.12)

**Surface: 0 occurrences. Floor confirmed.**

§6.12 mandates colon (not period) after bold structural labels. Scanned the 60-file corpus for `**Label**.` patterns — none found. Universally honored.

### D39 — Excessive Nesting (§6.12)

**Surface: 0 violations. Floor confirmed.**

§6.12 caps `begin_deeper` nesting at 2 levels. No block in any policy's §6 reaches depth ≥3. Universally honored.

### D40 — Multi-Directive Blend (§6.8 One Directive Per Item)

**Surface: 51 occurrences across 28 files** — substantial but adjudication-pending.

§6.8 Clarification permits multiple atomic single-directive bullets beneath a shared bold-label parent. The detected blends are different: a *single* atomic Itemize/Enumerate bullet containing two `shall` (or `shall not`) directives joined by `and` / `or`.

**Sample patterns:**

| File | §6.X | Bullet |
|------|------|--------|
| 1.01 | 6.2 | `**Decision Support**: The Department shall streamline and automate processes…and shall provide accurate, current, and well-governed data…` |
| 1.03 | 6.3 | `**Accountability**: The IT Director and Assistant IT Director shall acknowledge errors transparently and shall document lessons learned within five (5) business days…` |
| 1.05 | 6.2 | `The County Manager shall approve changes…and shall escalate to the Board of County Commissioners when legal ratification or additional appropriation is required.` |
| 1.07 | 6.1 | `**Documentation**: The IT Director shall document all privilege suspensions, exceptions, and reinstatements…and shall manage non-compliance under Policy 5.01.` |
| 1.13 | 6.3 | `**No Contract, No Access**: The IT Director shall not grant third-party logical access, and shall not authorize vendor hardware installation or connection, until a contract or formal agreement is fully executed.` |
| 1.14 | 6.1 | `**Lawful Supervisory Direction**: All Information Operations Personnel shall comply with lawful verbal direction from their chain of command and shall pursue written confirmation under the Written Confirmation Rule.` |

**Two readings:**

- **Strict §6.8.** "Each atomic bulleted or numbered item within the Policy Statement shall contain exactly one (1) directive or requirement. Blended items that combine multiple obligations in a single atomic bullet using conjunctions are prohibited." Every two-`shall` bullet is a violation; the architectural fix is to split into multiple atomic bullets under a shared bold-label parent (the §6.8 Clarification structural pattern).
- **Pragmatic / conjoined-symmetric.** When the second `shall` clause attaches a conjoined obligation that shares the deadline, role anchor, and conceptual unity of the first (e.g., `shall acknowledge…and shall document…within five (5) business days`), splitting fragments the reader's understanding of the unified obligation. A narrower §6.8 carve-out for "conjoined symmetric directives" with shared anchor + deadline would preserve readability while keeping the atomic-bullet rule intact for genuinely multi-obligation bullets.

**Q1 ruling (May 02, 2026): Q1b — v1.6 carve-out, locked criteria. See Q1 Resolution below.**

### D41 — Manual Policy Reference (§6.11)

**Surface: 3 occurrences across 2 files** (excluding 1.04 spec examples).

| File | §6.X | Line | Manual ref | Form |
|------|------|------|------------|------|
| 04/406 | 6.4 | L2027 | `Handoff from Policy 4.02:` | bold-label header |
| 04/406 | 6.4 | L2168 | `Policy 5.05 CJIS Denial Notifications:` | bold-label header |
| 05/507 | 6.2 | L1547 | `…produced under Policy 3.16.` | prose tail |

In all three cases, the policy number is typed literally rather than via `\begin_inset CommandInset ref`. §6.11 prohibits manually typed policy numbers anywhere in the body.

**Disposition:** New ticket — letter code **QQ** below.

### D42 — Self-Reference Convention

**Surface: 19 occurrences across 4 files** — adjudication-pending.

| File | Self-references in §6 |
|------|----------------------|
| 03/306 | 12 |
| 03/308 | 3 |
| 03/309 | 2 |
| 04/404 | 2 |

These are policies referring to themselves by number using manually typed `Policy 3.06`, `Policy 3.08`, `Policy 3.09`, `Policy 4.04` in §6 bodies. In 3.06 the pattern is rhetorical — `Policy 3.06` is used as a label for the operational incident regime that 3.06 governs (in contrast to Chapter 4 IR regimes). 3.08, 3.09, 4.04 use it for record-flow notation (`Policy 3.08 → Policy 3.09 direction`).

**§6.11 strict reading.** "Manually typed policy numbers are prohibited in the body of any policy." → Self-references must also use `CommandInset ref`. Convert all 19 to insets.

**Architectural alternative.** Self-references using the policy's own number are unusual prose: most policies use `this policy` or implicit reference. Convert all 19 to `this policy` (or contextual rewrites like "this regime" / "the operational regime governed by this policy").

**Mixed.** Where the self-reference is functionally a *named-regime label* (3.06's "Policy 3.06 incident" rhetorical usage), retain the policy-number form via `CommandInset ref`. Where the self-reference is a structural `this policy` substitution, convert to `this policy`. Per-instance judgment.

**Q2 ruling (May 02, 2026): Q2c — mixed per-instance. CommandInset ref where the policy-number functions as a regime label; `this policy` (or contextual rewrite) where the self-reference is structural substitution. Per-instance judgment during ticket execution.**

---

## 1.04-Internal Amendment Candidate

**1.04 §6.15 L2499 — Knowledge Base "Owner" definition uses prohibited "responsible for".**

Current text:
```
**Owner**: The role responsible for keeping the document current.
```

This violates 1.04 §6.9: `responsible for` is on the prohibited-language list, and §6.9 explicitly prohibits these phrases "in Section 6 (Policy Statement) of any policy" — which 1.04's own §6.15 is.

Canonical replacement using §6.9 anchoring + Shall form:
```
**Owner**: The role that shall keep the document current.
```

(Or alternatively: `…that shall maintain the document.` — a tightening review pass.)

**Disposition:** Fold into v1.6 amendment package as a sub-amendment to the existing five (#494, #498, #506, #509, #515). Constitutionally minor — internal consistency between 1.04 §6.9 and 1.04 §6.15.

---

## Adjudication Queue — RESOLVED

### Q1 Resolution (D40) — §6.8 v1.6 carve-out, locked May 02, 2026

**Ruling: Q1b — v1.6 carve-out for conjoined-symmetric directives.** Splitting genuine multi-obligation blends preserves §6.8 atomicity; permitting symmetric conjoined directives preserves the unified-obligation reading where splitting would fragment narrative flow and introduce logic gaps.

#### Carve-out language (proposed for v1.6 amendment to 1.04 §6.8)

The current 1.04 §6.8 "One Directive Per Item" rule reads:

> Each atomic bulleted or numbered item within the Policy Statement shall contain exactly one (1) directive or requirement. Blended items that combine multiple obligations in a single atomic bullet using conjunctions are prohibited.

The v1.6 amendment adds a carve-out exception immediately after the "Clarification" sub-bullet:

> **Exception**: Two directives may appear in a single atomic bullet only when **all** of the following are true:
>
> (a) **Identical role anchor** — both directives bind the same role (or the same role pair acting jointly).
>
> (b) **Identical scope** — both directives apply to the same subject matter, asset class, or set of circumstances.
>
> (c) **Shared trigger or shared deadline** — a single condition, event, or time-bound obligation activates both directives equally; not merely one of the two.
>
> (d) **Parallel prohibitions or parallel prescriptions** — the directives complete a single unified obligation. Sequential or conditional pairs (where the second directive follows from, is triggered by, or applies under different circumstances than the first) shall be split.
>
> (e) **Splitting would change the meaning** — separating the directives into distinct atomic bullets would either change the meaning of either directive or render either directive incomplete.
>
> Where any of the five criteria fail, the bullet shall be split into separate atomic bullets under a shared bold-label parent (the structural pattern defined in this Section).

**Disposition:** Folds into the v1.6 amendment package as a sub-amendment (alongside #494, #498, #506, #509, #515, and the §6.15 Owner-definition micro-amendment). v1.6 amendment package commits as a single 1.04 patch bump.

#### Q1b walk — 51 candidates re-walked against locked criteria

| Verdict | Count | Disposition |
|---------|-------|-------------|
| **PASS** (qualifies under carve-out — no split) | 30 | No action; current text retained |
| **FAIL** (must split — SS ticket scope) | 21 | Filed under ticket SS |

**PASS — 30 sites (qualify under v1.6 carve-out, no split needed):**

1.09 §6.2 CJI Categorization · 1.12 §6.11 Prohibited Removal (sentence 2 only) · 1.13 §6.3 No Contract, No Access · 1.14 §6.1 Informal Communications · 1.14 §6.1 Lawful Supervisory Direction · 1.14 §6.7 Communication Discipline · 1.14 §6.7 Boundary · 2.04 §6.3 Least Privilege · 2.05 §6.10 Private Key Protection · 2.09 §6.2 Noncompliance Notification · 2.12 §6.4 CJI Media Destruction Only · 2.12 §6.8 Inoperable Media (Break/Fix) (sentence 2 only) · 2.12 §6.10 Vendor Data Return · 2.12 §6.10 Verification · 3.02 §6.2 Adherence Tracking · 3.02 §6.4 Report Format and Retention · 3.03 §6.1 Private Notes Use · 3.05 §6.2 Telephone requests · 3.05 §6.5 Assistant IT Director Review · 3.06 §6.6 Problem Record Spawn · 3.07 §6.4 AID Review · 3.07 §6.4 IT Director Review · 3.07 §6.5 Known Error Declaration · 3.09 §6.3 Standard Changes · 3.14 §6.6 Formal acceptance · 5.01 §6.6 Risk Recording · 5.01 §6.6 Active Exception Review · 5.02 §6.5 Conforming · 5.03 §6.2 Root Cause · 5.06 §6.6 Monitoring

**FAIL — 21 sites across 16 unique policies (SS ticket scope):**

| Policy | §6.X site(s) | Failing criterion |
|--------|--------------|-------------------|
| 1.01 | §6.2 Decision Support | (b) different scopes — process automation vs. data quality; (d) not unified |
| 1.03 | §6.3 Accountability | (a) mixed roles within bullet; (c) no shared trigger; (d) sequential |
| 1.03 | §6.3 Crisis Discipline | (a) different roles (IO Personnel vs. IT Director/AID); (d) sequential narrative |
| 1.05 | §6.2 County Manager | (c) different triggers (approve vs. escalate when legal ratification needed); (d) conditional |
| 1.07 | §6.1 Documentation | (b) different scopes (records vs. enforcement); (d) not unified |
| 1.09 | §6.1 Continuous Monitoring | (b) different scopes (CSF alignment vs. Continuous Monitoring program integration); (d) not unified |
| 1.09 | §6.7 Sensitive Security Information | (d) three sequential directives (treat + restrict + protect from FOIA) |
| 1.11 | §6.6 Exception (Confidential storage outside US) | (c) different triggers (at proposal vs. annual review); sequential |
| 1.14 | §6.3 Scheduled Maintenance | (c) conditional — second clause "When 48 hours not feasible" creates different trigger |
| 2.01 | §6.5 Exclusion | (d) compound exclusion definition with downstream pathway directive |
| 2.11 | §6.4 Export Controls | (d) two distinct directives (restrict extraction + classification inheritance) |
| 2.12 | §6.8 Automated Data Removal Limitations | (c) different cadence/mechanism (configure weekly removal + implement alerting) |
| 3.02 | §6.1 Automated Monitoring Tools | (d) sequential integration + reconciliation directives |
| 3.02 | §6.5 Contract Renewal Input | (d) preparation + downstream effect (informs vendor compliance) sequential |
| 3.02 | §6.6 Recurring Ticket Identification | (d) compound definitional + action structure |
| 3.07 | §6.3 Investigation Priority | (d) multi-sentence sequential |
| 3.07 | §6.7 Clarification | (a) different actions (determine + other) |
| 4.05 | §6.4 Audit log integrity | (d) multi-sentence with two distinct review acts |
| 5.01 | §6.4 Emergency Protective Action | (d) long compound conditional sequence |
| 5.04 | §6.6 Single-Period Miss | (d) definitional + AID action mixed |
| 5.06 | §6.3 Contracts Without Defined Renewal Dates | (d) appears compound across context |

### Q2 Resolution (D42) — Self-reference convention, locked May 02, 2026

**Ruling: Q2c — mixed per-instance.** CommandInset ref where the policy-number functions as a regime label (3.06's `Policy 3.06 incident` rhetorical contrast against `Chapter 4 IR incident`; 3.08/3.09 directional flow notation `Policy X.XX → Policy Y.YY`); `this policy` (or contextual rewrite) where the self-reference is purely structural substitution. Per-instance judgment during ticket execution by the executing tightening session.

**Disposition:** Filed under ticket TT. Operationally close to Q2a (CommandInset ref in ~all instances), but Q2c retains `this policy` as an option for the rare case where structural substitution reads more cleanly than the self-naming form.

---

## Out-of-Scope (deferred)

- **§6.10 Acronym Protocol manual-wide sweep.** §6.10 applies to all sections, not just §6 — any §6-only sweep would be premature. Defers to **Phase 9H Editorial Pass** per §1 audit precedent. Per-policy first-use spell-out validation requires full-policy text walks (not §6-only) plus Glossary inclusion criteria — operationalized as a dedicated session.
- **§6.10 product-name sweep.** Covered by **ongoing #6** (manual-wide product-name → governance-function-label rewrite, including the Redmine residual). No new §6 audit ticket.
- **D-class for passive-voice "orphan" detection.** Heuristic produces overwhelming false-positive rate against legitimate impersonal-subject formatting rules permitted by §6.10 ("passive constructions are permitted only when the acting role is genuinely irrelevant or unknown" — many `Content/citations/terms shall be Xed` cases satisfy this). No reliable mechanical test; case-by-case judgment in tightening sessions remains the right method.

---

## Ticket Package (locked)

Filing letter codes continue from §5 audit (last = NN). §6 audit uses **OO, PP, QQ, SS, TT**.

| Code | Class | Title | Scope | Labels |
|------|-------|-------|-------|--------|
| **OO (#523)** | D31 | `[§6 audit] D31 — Strip §6.9 prohibited-language drift across 8 policies` | 1.04 §6.15 (1.04-internal — folds into v1.6); 1.09 §6.8; 1.14 §6.4; 3.04 §6.3; 3.08 §6.2; 4.06 §6.7; 5.01 §6.4; 5.06 §6.5 / §6.6 | `cross-cutting`, `global`, `substantive`, `phase-6` |
| **PP (#524)** | D37 | `[§6 audit] D37 — Restore terminal periods in 2.15 §6.2/§6.4 + 5.06 §6.1` | 2.15 (12 sites) + 5.06 (5 sites) | `format`, `phase-6`, `ch2-security`, `ch5-compliance` |
| **QQ (#525)** | D41 | `[§6 audit] D41 — Replace 3 manually typed Policy refs with CommandInset ref` | 4.06 §6.4 (×2 bold-label headers) + 5.07 §6.2 prose tail | `format`, `phase-6`, `ch4-incident-response`, `ch5-compliance` |
| **SS (#526)** | D40 | `[§6 audit] D40 — Split multi-directive blends per §6.8 (v1.6 carve-out exclusions)` | 21 sites across 16 policies (post-Q1b carve-out): 1.01, 1.03 (×2), 1.05, 1.07, 1.09 (×2), 1.11, 1.14, 2.01, 2.11, 2.12, 3.02 (×3), 3.07 (×2), 4.05, 5.01, 5.04, 5.06 | `cross-cutting`, `format`, `substantive`, `phase-6` |
| **TT (#527)** | D42 | `[§6 audit] D42 — Self-reference convention sweep (Q2c per-instance)` | 19 sites across 4 policies: 3.06 (×12), 3.08 (×3), 3.09 (×2), 4.04 (×2) | `format`, `phase-6`, `ch3-service-management`, `ch4-incident-response` |

**Filing dependency:** SS execution gates on v1.6 amendment package landing (carve-out language must be in 1.04 §6.8 before SS work begins). PP, QQ, OO, TT are not gated.

### Existing tickets absorbed (no new filings)

| Existing ticket | §6-audit catalog growth |
|-----------------|-------------------------|
| **#375** (Universal §6.X-strip sweep) | D34 = 0 new findings; existing #413 (3.12 §6.5) and #418 (4.01 L2688) remain the active strip cases. |
| **#509** (1.04 §6.12 amendment to v1.6 + manual-wide strip of Constraint/Clarification/Exclusion) | D36 = 30 use-sites in §6 across 20 files (catalog noted; absorbed into #509 footprint). |
| **#6** (Manual-wide product-name → governance-function-label) | D41 product-name detection out of §6 audit scope; covered. |

### v1.6 Amendment Package — additions surfaced by §6 audit

| Existing v1.6 amendments | Status |
|---|---|
| #494 §6.5 authority sequence | Queued |
| #498 §9.1 IC clarifier | Queued |
| #506 §6.6 optional-bullet narrowing | Queued |
| #509 §6.12 clarifier-tag narrowing (Rationale + Exception) | Queued |
| #515 §6.11 citation form amendments (E1–E5) | Queued |
| **(NEW) §6.15 L2499 Owner definition** | §6 audit: re-anchor `responsible for` to Shall form (1.04 §6.9 internal consistency) |
| **(NEW) §6.8 conjoined-symmetric carve-out** | §6 audit Q1b ruling May 02, 2026: five-criterion carve-out language (a)–(e) appended to "One Directive Per Item" rule |

---

## Plan / README updates (post-adjudication)

- **TIGHTENING_PLAN.md Phase 5F section.** Append §6 audit close note paralleling §1–§5 close notes: floor summary, defect classes D31–D42, ticket OO/PP/QQ filings (and SS/TT post-adjudication), absorption notes for #375 / #509, v1.6 amendment package additions.
- **TIGHTENING_PLAN.md Phase 5F intake count.** Increment from 36 to (36 + new tickets filed). Recalc after Q1/Q2 close.
- **README.md per-policy ticket assignments.** Add OO/PP/QQ ticket numbers to affected policies' state lines (8 policies for OO, 2 for PP, 2 for QQ).
- **TIGHTENING_PLAN.md Phase 5F gating.** With §6ing audit closed, Phase 5F gating clears (Phase 6 closed ✓ AND all section audits closed ✓). Unified per-policy patch-bump cleanup pass becomes runnable before Phase 7 (Chapter 6 Appendices).

---

## Audit Conclusion

§6 mechanical floor is uniform across all eight floor items (F1–F8). Substantive variance lives in five fileable classes (D31, D37, D40, D41, D42), two architectural absorption-class catalogs (D34 → #375, D36 → #509), and two v1.6 amendment-package additions (§6.15 Owner definition micro-amendment + §6.8 conjoined-symmetric carve-out from Q1b ruling).

Locked rulings (May 02, 2026): **Q1b** v1.6 carve-out for §6.8 with five-criterion test (a)–(e); **Q2c** mixed per-instance for self-reference convention.

Filing scope locked May 02, 2026: **OO (#523)** (8 sites), **PP (#524)** (17 sites), **QQ (#525)** (3 sites), **SS (#526)** (21 sites across 16 policies, gated on v1.6 amendment landing), **TT (#527)** (19 sites across 4 policies). No new standing decline pattern surfaced — §6 drift absorbs into existing pattern stack (#20, #36, #37, #40, #41).

§6 audit is the sixth and final section audit in Phase 5F. With it closed, Phase 5F gating clears: Phase 6 closed ✓ AND all six section audits closed ✓. Unified per-policy patch-bump cleanup pass becomes runnable before Phase 7 (Chapter 6 Appendices).
