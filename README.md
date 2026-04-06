# ECIO Policy Manual — Cleanup Tracking

> **Private internal tracking** · Target: Board adoption **July 1, 2026**
>
> Status: 🔴 Needs work · 🟡 Partially complete · 🟢 Substantially complete

---

## Progress Summary

| Scope | 🔴 | 🟡 | 🟢 |
|---|---|---|---|
| Cross-Cutting (GLOBAL) | 4 | 0 | 0 |
| Chapter 1 — Governance | 12 | 1 | 0 |
| Chapter 2 — Information Security | 15 | 0 | 0 |
| Chapter 3 — Service Management | 17 | 0 | 0 |
| Chapter 4 — Incident Response | 7 | 0 | 0 |
| Chapter 5 — Compliance & Oversight | 0 | 5 | 2 |
| Chapter 6 — Appendices | 3 | 1 | 0 |
| **Total** | **57** | **7** | **2** |

---

## Cross-Cutting Prerequisites

These three tasks span nearly every policy and act as prerequisites for the individual policy passes. Track completion by working through each affected policy's checklist below.

### GLOBAL-A — Prohibited Purpose Construction 🔴

**Rule:** Every Purpose section must open with `This policy [verb]s...` not `The purpose of this policy is to...` (Policy 1.04 §6.3)

**Confirmed affected:** 1.01, 1.02, 1.03, 1.05, 1.10, 1.12, 2.03, 2.07, 2.09, 2.10, 2.13, 2.15, and all of Ch. 3 except 3.15 and 3.17
**Already compliant:** 1.06, 1.11, 1.13, 2.01, 2.02, 2.04, 2.05, 2.11, 3.15, 3.17, all of Ch. 4 and Ch. 5

*Track completion under each individual policy below.*

---

### GLOBAL-B — Section 5 Cited/Framework Split 🔴

**Rule:** Every policy's References section must be divided into **Cited References** and **Framework Alignment** subsections (Policy 1.04 §6.7)

**Already completed:** 1.04, 5.01, 5.03, 5.04, 5.05, 5.06
**All other policies require the split** — near-universal obligation

*Track completion under each individual policy below.*

---

### GLOBAL-C — 5.01 and 5.02 Title Normalization Sweep 🔴

**Rule:** All in-body cross-references and Section 5 citations must use current titles.
- Old 5.01 title: `Policy Implementation and Enforcement Framework` → **`Policy Implementation, Enforcement, and Legal Alignment`**
- Old 5.02 title: `Internal Audits and Self-Assessment Procedures` → **`Internal Audits, Self-Assessment, and Control Testing`**

**Confirmed old-title instances:** 1.01 §4, 1.02 §5, 1.03 §4, 1.07 §4, 1.12 §4, 2.06 §5, and all Ch. 3 policies

*Track completion under each individual policy below.*

---

### GLOBAL-D — Vendor and Product Name Removal 🔴

**Policy 1.04 §6.10 has been amended.** The previous rule required governance label first, product name in parentheses — e.g., `System of Engagement (Redmine)`. That still couples the policy to a specific product: switch platforms and you're immediately out of compliance with your own manual. The amended rule prohibits product names in policy text entirely.

> **Official Systems Terminology (amended):** Software and platforms referenced in policy documents shall be cited by their governance function label only (e.g., "System of Engagement," "Authoritative System of Record," "Endpoint Protection Platform," "Productivity Suite"). Vendor and product names shall not appear in policy text. Product-specific names, configurations, and implementation details belong in operational documentation maintained in the System of Engagement.

Product names belong in SOPs and Knowledge Base entries — not in governance documents. A platform migration should require zero policy edits.

| Vendor / Product to Remove | Current Location(s) | Replace With |
|---|---|---|
| Redmine | 1.04, 1.08, 1.14, 3.01–3.17, 6.04 | `System of Engagement` |
| Office 365 | 2.14 §2 | `Productivity Suite` |
| Comodo / XCitium | 3.08 §6.2 | `Endpoint Protection Platform` |
| Justware | 6.04 (Report Building category; Vendor Resolved description) | `Case Management System` |
| HID DigitalPersona | 2.05 §6.10 | `Public Key-Based Authentication Hardware` |
| Xerox | 6.04 (Vendor Resolved status description) | `Managed Print Services` |

> **Note on Xerox / 2.12:** The 2.12 decouple item traces to 6.04, not to 2.12 body text. Close the 2.12 item once 6.04 is updated.

- [ ] **[1.04]** Apply amended §6.10 language to the source document
- [ ] **[Redmine]** Remove all `Redmine` product-name references across 1.04, 1.08, 1.14, 3.01–3.17, and 6.04 — replace with `System of Engagement`
- [ ] **[Office 365]** Remove `Office 365` from 2.14 §2 — replace with `Productivity Suite`
- [ ] **[Comodo / XCitium]** Remove `Comodo/XCitium` from 3.08 §6.2 — replace with `Endpoint Protection Platform`
- [ ] **[Justware]** Remove `Justware` from 6.04 Report Building and Vendor Resolved descriptions — replace with `Case Management System`; verify whether any 1.04 snippet also needs updating
- [ ] **[HID DigitalPersona]** Remove `HID DigitalPersona` from 2.05 §6.10 — replace with `Public Key-Based Authentication Hardware`
- [ ] **[Xerox]** Remove `Xerox` from 6.04 Vendor Resolved description — replace with `Managed Print Services`; confirm 2.12 body text is clean and close that item

---

## Chapter 1 — Governance and Strategic Framework

<details>
<summary>Click to expand Chapter 1</summary>

### 000 — Abstract / Executive Summary 🔴

> **Dependency:** 5.01

- [ ] **[Logic]** Exception/deviation routing in Authority and Scope still points to Policy 1.04 and Policy 1.08 — update to Policy 5.01 (Policy Implementation, Enforcement, and Legal Alignment)
- [ ] **[Standard]** Verify Compliance Alignment & Order of Precedence hierarchy exactly matches the resolution hierarchy stated in Policy 5.01 §6.7
- [ ] **[QC]** Framework titles in the Compliance Alignment list are not bolded — apply bold treatment per 1.04 §6.11
- [ ] **[Decouple]** Confirm no bare `Redmine` references remain — `System of Engagement (Redmine)` format found in Authority and Scope is correct ✓

---

### 1.01 — Mission & Objectives 🔴

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[Format]** §4 Exceptions: routes to 1.04 and 1.08 only — add routing to 5.01 exception framework and add "Oral exceptions are not valid"
- [ ] **[GLOBAL-C]** §4 Enforcement: update 5.01 title
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 1.02 — Code of Ethics and Professional Conduct 🔴

> **Dependency:** 5.01

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[Central]** §4 CJIS PS-8 sanctions detail duplicates 5.01 §6.5 verbatim — reduce to a single cross-reference to Policy 5.01; remove the duplicated procedural language
- [ ] **[Format]** Sanctions and CJIS Notification bullets in §4 are outside the standard labeled-bullet structure defined in 1.04 §6.6 — reconcile
- [ ] **[GLOBAL-C]** §5: Update old 5.01 title
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 1.03 — Standard Operating Ethos 🔴

> **Dependency:** 5.01

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[Logic]** §6.4 "Document as Standard" mandates documentation of "all operational actions, changes, and decisions" — evaluate narrowing to "material actions only" for audit proportionality; must be consistent with 5.01 §6.1 (same language, same decision)
- [ ] **[Format]** §4 Exceptions: routes to 1.04 and 1.08 — add 5.01 routing and oral-exception prohibition
- [ ] **[GLOBAL-C]** §4 Enforcement: update 5.01 title
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 1.04 — Policy and Documentation Formatting Standards 🟡

- [ ] **[Decouple]** Add "System of Engagement" and "Case Management System" governance labels to Glossary 6.01 once that appendix is populated; update first-use in 1.04 to cite the Glossary entry
- [ ] **[Logic]** Finalize LyX environment names for Procedure and Playbook formatting (§6.15/6.16) so the distinction is explicit in source markup, not just narrative
- [ ] **[Standard]** Verify §5 citation ordering follows the sub-ordering rules defined in §6.11 of this same policy

*Cited/Framework split already implemented ✓*

---

### 1.05 — Policy Review and Update Procedures 🔴

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 1.06 — IT Governance and Oversight Structure 🔴

- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split
- [ ] **[Logic]** Verify §6 contains governance trigger criteria compatible with 5.07 §6.6 Board reporting determination — 5.07 references 1.06 governance triggers as the basis for County Manager's decision on whether Board presentation of the Annual Policy Review Report is warranted

*Purpose construction is compliant ✓*

---

### 1.07 — Workforce Roles, Responsibilities, and Competency Framework 🔴

> **Dependency:** 5.01, 6.03

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[Logic]** §4: Add explicit annual training and certification verification language as a Compliance condition — current Assessment bullet references performance reviews but does not name the certification verification mechanism
- [ ] **[Logic]** §6.1 privileged access suspension language cross-references 5.01 in narrative but must use a bolded LyX cross-reference inset per 1.04 §6.11
- [ ] **[GLOBAL-C]** §4 Enforcement: update 5.01 title
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 1.08 — Delegation of Authority and Decision Rights 🔴

> **Dependency:** 5.01

- [ ] **[GLOBAL-D]** §4: bare `Redmine` reference — remove product name; replace with `System of Engagement`
- [ ] **[Logic]** §4 exception bullets (Operational and Governance) do not route to the 5.01 exception framework — add explicit routing and oral-exception prohibition
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 1.09 — Risk Management Policy 🔴

> **Dependency:** 5.03

- [ ] **[Logic]** Global replace: `Plans of Action and Milestones (POA&Ms)` / `POA&M` → `Corrective Action Plans (CAPs)` / `CAP` throughout, consistent with 5.03; add explicit routing of CAP lifecycle to Policy 5.03
- [ ] **[Ref]** Broken reference: §4 Exceptions reads "...documented using the standard Risk Acceptance Memo Template located in." — cross-reference target is empty/missing; locate and insert the correct LyX inset
- [ ] **[Format]** §4 structure uses non-standard labels (Mandatory Compliance, Acknowledgment, Records Retention, Exceptions) — does not follow 1.04 §6.6 three-bullet template; reconcile or document the deliberate deviation
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 1.10 — IT Financial Management and Procurement Policy 🔴

- [ ] **[Ref]** Typographic error in §4: `inPolicy5.07` (missing space before policy number) — fix. Same error in §5 References: `ECIO Policy5.07`
- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 1.11 — Data Governance and Classification Policy 🔴

- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

*Purpose construction is compliant ✓*

---

### 1.12 — IT Asset Management Policy 🔴

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[GLOBAL-C]** §4 Enforcement: update 5.01 title
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 1.13 — Supply Chain Risk Management (SCRM) and Vendor Governance 🔴

- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

*Purpose construction is compliant ✓*

---

### 1.14 — Stakeholder Engagement and Communications Policy 🔴

> **Dependency:** 5.01

- [ ] **[Logic]** Verify §4 contractor acknowledgment language is consistent with 5.01 §6.2 (30-day lapse threshold and access-suspension mechanism)
- [ ] **[GLOBAL-D]** Scan for any remaining product-name references — remove per GLOBAL-D sweep and replace with `System of Engagement`
- [ ] **[Format]** §4 Exceptions routes to 1.08 only — add 5.01 routing
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

</details>

---

## Chapter 2 — Information Security

<details>
<summary>Click to expand Chapter 2</summary>

### 2.01 — Acceptable Use of Information Technology Resources Policy 🔴

- [ ] **[Format]** §4 is missing the standard Assessment / Enforcement / Exceptions labeled-bullet structure per 1.04 §6.6 — current §4 uses narrative sentences; restructure
- [ ] **[Format]** §4 Enforcement does not name 5.01 explicitly — add pointer with current title
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

*H1 title verified consistent with ToC ✓ · `System of Engagement (Redmine)` in §6.6 correctly formatted ✓*

---

### 2.02 — Personnel Security and Background Screening Policy 🔴

- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

*Purpose construction is compliant ✓*

---

### 2.03 — Security Awareness and Training Policy 🔴

> **Dependency:** 2.04

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[Logic]** §6: Add explicit tie between training completion and the access recertification cycle in Policy 2.04 — a training lapse should trigger suspension consistent with 2.04 §6.9
- [ ] **[Format]** §4 non-standard labels (Mandatory Condition of Access, Account Suspension, Exceptions) — reconcile with 1.04 §6.6 template
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 2.04 — Access Control Policy 🔴

- [ ] **[Format]** §4 uses custom labels — verify all three mandatory bullets (Assessment, Enforcement, Exceptions) are present and properly labeled per 1.04 §6.6
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

*Purpose construction is compliant ✓*

---

### 2.05 — Identification and Authentication Policy 🔴

- [ ] **[GLOBAL-D]** §6.10: remove `HID DigitalPersona` — replace with `Public Key-Based Authentication Hardware`
- [ ] **[Format]** §4 non-standard labels (Mandatory Enforcement, Sanctions, CJIS Floor, Exception Process) — reconcile with 1.04 §6.6 template
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 2.06 — Privacy and Data Protection Policy 🔴

> **Dependency:** 5.01

- [ ] **[Logic]** §4 Exceptions clause requires approval from "the IT Director and the District Attorney's Office" — DA's Office is not part of the standard exception approval chain defined in 5.01 §6.6; either document the rationale or align with the standard framework
- [ ] **[Format]** §4 is a single narrative sentence rather than the labeled-bullet structure — restructure per 1.04 §6.6
- [ ] **[GLOBAL-C]** §5: Update old 5.02 title
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 2.07 — System and Communications Protection Policy 🔴

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[Format]** §4 "Mandatory Enforcement" is a non-standard label — restructure per 1.04 §6.6
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 2.08 — System Integrity and Malware Protection Policy 🔴

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[GLOBAL-D]** Verify whether any EPP product name appears in 2.08 body text — `XCitium/Comodo` is named in 3.08 as the endpoint SOE; if 2.08 refers to it by name apply governance label per GLOBAL-D sweep. Current 2.08 text uses generic "endpoint protection" language, which appears compliant ✓
- [ ] **[Format]** §4 "Mandatory Enforcement" is a non-standard label — restructure per 1.04 §6.6
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 2.09 — Vulnerability and Patch Management Policy 🔴

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[Format]** §4 "Mandatory Compliance" is a non-standard label — restructure per 1.04 §6.6
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 2.10 — Secure Configuration Baselines and Hardening Policy 🔴

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[Format]** §4 is a single paragraph rather than labeled-bullet structure — restructure per 1.04 §6.6
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 2.11 — Audit Logging and Monitoring Policy 🔴

- [ ] **[Format]** §4: Assessment bullet is missing entirely; Mandatory Enforcement and Exceptions are present as separate paragraphs rather than labeled bullets — restructure per 1.04 §6.6
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

*Purpose construction is compliant ✓*

---

### 2.12 — Media Protection and Sanitization Policy 🔴

- [ ] **[GLOBAL-D]** Confirm no bare Xerox reference in 2.12 body text — 2.12 uses generic "MFPs" and "multifunction printers/copiers" language throughout ✓. The Xerox product-name issue originates in 6.04 (Vendor Resolved description) — close this item once the GLOBAL-D 6.04 sweep is complete
- [ ] **[GLOBAL-C]** §4: Verify 5.01 title currency
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 2.13 — Physical Security and Environmental Controls Policy 🔴

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[Format]** §4 is a single narrative paragraph rather than labeled-bullet structure — restructure per 1.04 §6.6
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 2.14 — Mobile Device and Remote Access Policy 🔴

- [ ] **[GLOBAL-D]** §2 Scope: remove `Office 365` — replace with `Productivity Suite`
- [ ] **[Standard]** §6.9 body text cites "CJIS Section 5.20.7.2" without a parenthetical topic; that section number does not appear in §5 Cited References — add properly formatted citation entry per 1.04 §6.11
- [ ] **[Format]** §4: Verify all three mandatory bullets (Assessment, Enforcement, Exceptions) are present and properly labeled
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 2.15 — System Development and Secure Software Lifecycle Policy 🔴

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[Format]** §4 "Mandatory Adherence" and "Exception Handling" are non-standard labels — restructure per 1.04 §6.6
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

</details>

---

## Chapter 3 — Service Management and Operations

<details>
<summary>Click to expand Chapter 3</summary>

> **Common issues across all Ch. 3 policies** (track individually below):
> - GLOBAL-A: All except 3.15 and 3.17 have prohibited Purpose constructions
> - GLOBAL-C: All policies reference 5.01 and/or 5.02 by old titles
> - GLOBAL-B: All policies need the Cited/Framework split in §5

### 3.01 — Service Catalog and SLA Policy 🔴

> **Dependency:** 5.01, 5.02

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[Ref]** §5 References: `ECIO Policy5.07` — missing space before policy number (same typographic error as 1.10)
- [ ] **[GLOBAL-D]** Redmine referenced in §6.1 and §6.5 — verify governance-label format used consistently throughout as part of GLOBAL-D sweep
- [ ] **[GLOBAL-C]** §4 Enforcement: update 5.01/5.06 titles
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 3.02 — Service Level Management and Metrics Reporting 🔴

> **Dependency:** 5.01, 5.02

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[Ref]** §5 References: `ECIO Policy5.07` — missing space (same typographic error)
- [ ] **[GLOBAL-C]** §4 Enforcement: update 5.01 title
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 3.03 — End-User Communication Standards 🔴

> **Dependency:** 5.01, 5.02

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[Ref]** §5 References: NRS 239.125 and NAC 239.155 each appear twice — remove duplicate entries
- [ ] **[GLOBAL-C]** §4 Enforcement: update 5.01 title
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 3.04 — Service Delivery Feedback and Grievance Policy 🔴

> **Dependency:** 5.01, 5.02

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[GLOBAL-C]** §4 Enforcement: update 5.01 title
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 3.05 — Service Request Fulfillment Policy 🔴

> **Dependency:** 5.01, 5.02

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[GLOBAL-C]** §4 Enforcement: update 5.01 title
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 3.06 — Operational Incident Management Policy 🔴

> **Dependency:** 5.01, 5.02

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[GLOBAL-C]** §4 Enforcement: update 5.01 title
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 3.07 — Problem Management Policy 🔴

> **Dependency:** 5.01, 5.02

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[GLOBAL-C]** §4 Enforcement: update 5.01 title
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 3.08 — Service Configuration Management (CMDB) Policy 🔴

> **Dependency:** 1.12

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[GLOBAL-D]** §6.2: remove `Comodo/XCitium` — replace with `Endpoint Protection Platform`
- [ ] **[GLOBAL-C]** §5: Update old 5.01/5.02 titles
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 3.09 — Change Management Policy 🔴

> **Dependency:** 5.01, 5.02

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[GLOBAL-C]** §4 Enforcement: update 5.01 title
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 3.10 — Release and Deployment Policy 🔴

> **Dependency:** 5.01, 5.02

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[GLOBAL-C]** §4 Enforcement: verify and update 5.01 title
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 3.11 — Capacity and Availability Management Policy 🔴

> **Dependency:** 5.01, 5.02

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[GLOBAL-C]** §4 Enforcement: update 5.01 title
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 3.12 — Monitoring and Event Management Policy 🔴

> **Dependency:** 5.01, 5.02

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[GLOBAL-C]** §4 Enforcement: update 5.01 title
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 3.13 — Knowledge Management Policy 🔴

> **Dependency:** 5.01, 5.02

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[GLOBAL-C]** §4 Enforcement: update 5.01 title
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 3.14 — IT Project Management Policy 🔴

> **Dependency:** 5.01, 5.02

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[GLOBAL-C]** §4 Enforcement: update 5.01 title
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 3.15 — Service Continuity and Contingency Planning Policy 🔴

> **Dependency:** 5.01, 5.02

- [ ] **[GLOBAL-C]** §4 Enforcement: update 5.01 title
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

*Purpose construction is compliant ✓*

---

### 3.16 — Service Improvement and Continual Improvement Plan 🔴

> **Dependency:** 5.01, 5.02, 5.07

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[Logic]** §3/§6: Annual improvement summary is produced "in accordance with the Policy 5.07 review cycle" but no submission deadline is specified — evaluate whether a concrete deadline is needed to ensure the summary is available before the 5.07 input compilation begins (5.07 imposes a 90-day post-fiscal-year report deadline)
- [ ] **[GLOBAL-C]** §4 Enforcement: update 5.01 title
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 3.17 — System Maintenance and Vendor Repairs 🔴

> **Dependency:** 5.01, 5.02

- [ ] **[Ref]** §4: `inPolicy5.07` — missing space before policy number (same typographic error as 1.10, 3.01, 3.02)
- [ ] **[GLOBAL-C]** §4 Enforcement: update 5.01 title
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

*Purpose construction is compliant ✓*

</details>

---

## Chapter 4 — Incident Response

<details>
<summary>Click to expand Chapter 4</summary>

> ⚠️ **Resolve the 4.01 dual-identity issue before drafting any stubs.** Policy 4.05 is currently referenced as two different things ("Recovery Operations and Restoration Prioritization" and "Data and System Classification for Recovery"). Assign the correct number to each before forward references get baked into new content.

### 4.01 — Incident Response Policy Overview 🔴

- [ ] **[Ref]** §5 References lists Policy 4.05 twice under two different descriptions: "Recovery Operations and Restoration Prioritization" and "Data and System Classification for Recovery" — decide whether Data/System Classification is a standalone policy needing its own number (e.g., 4.09) or a formally named subsection of 4.05; resolve before drafting remaining stubs
- [ ] **[Ref]** Body text cross-references `Policy4.06` and `Policy4.08` — missing spaces, indicating broken LyX cross-reference insets; fix insets
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 4.02 — Identification and Reporting Procedures 🔴

- [ ] **[Ref]** Out of Scope list references "Policy 4.05: Data and System Classification for Recovery" — will resolve with 4.01 numbering fix
- [ ] **[Ref]** §5 References: `ECIO Policy4.08` and `ECIO Policy4.06` — missing spaces; fix LyX insets
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 4.03 — Containment Strategy and Playbooks 🔴

- [ ] **[GLOBAL-A]** Fix prohibited Purpose construction
- [ ] **[Ref]** §5 References: cites "ECIO Policy 2.10: Security Configuration and Baseline Management Policy" — incorrect title; actual title is "Secure Configuration Baselines and Hardening Policy"
- [ ] **[GLOBAL-B]** §5: Implement Cited/Framework split

---

### 4.04 — Eradication Procedures and Scenario Guides 🔴

> ⚠️ Resolve 4.01 dual-identity issue before drafting

- [ ] **[Draft]** Full content development required — stub only (six section headers, no content)
- [ ] **[Standard]** §4/5 boilerplate and split pass when drafted

---

### 4.05 — Recovery Operations and Restoration Prioritization 🔴

> ⚠️ Resolve 4.01 dual-identity issue before drafting

- [ ] **[Draft]** Full content development required — stub only
- [ ] **[Logic]** Resolve dual-identity issue: if "Data and System Classification for Recovery" is a distinct governance artifact it needs its own policy number; if it is a subsection of 4.05 it must be formally named as such and referenced consistently throughout
- [ ] **[Standard]** §4/5 boilerplate and split pass when drafted

---

### 4.06 — Communication Protocols and Partner Integration 🔴

- [ ] **[Draft]** Full content development required — stub only
- [ ] **[Standard]** §4/5 boilerplate and split pass when drafted

---

### 4.07 — Postmortem Review and Lessons Learned 🔴

- [ ] **[Draft]** Full content development required — stub only
- [ ] **[Standard]** §4/5 boilerplate and split pass when drafted

---

### 4.08 — Incident Response Roles and Contact Directory 🔴

> *Note: Original cleanup list ran stubs through 4.07; 4.08 is also a stub.*

- [ ] **[Draft]** Full content development required — stub only
- [ ] **[Standard]** §4/5 boilerplate and split pass when drafted

</details>

---

## Chapter 5 — Compliance and Oversight

<details>
<summary>Click to expand Chapter 5</summary>

### 5.01 — Policy Implementation, Enforcement, and Legal Alignment 🟡

> **Dependency:** 1.03

- [ ] **[Logic]** §6.1 Documentation Standard mandates documentation of "all operational actions, changes, and decisions" — evaluate whether "material actions only" is the intended scope; 1.03 §6.4 has identical language and both must reflect the same final decision

*Title normalized ✓ · Cited/Framework split implemented ✓*

---

### 5.02 — Internal Audits, Self-Assessment, and Control Testing 🟡

> **Dependency:** 5.07

- [ ] **[Standard]** Sweep any remaining in-manual citations pointing to old 5.07 short-form title — current title "Annual Policy Review and Maturity Scoring" appears consistently in policies reviewed; confirm no stragglers
- [ ] **[Logic]** §6.6 retention trigger misalignment: states "three (3) years from the date of the assessment" — LRDA 20071256 (Quality Assurance Review Audits and Reports) specifies "from the end of the calendar year to which they pertain"; Policy 1.11 already uses the correct construction for LRDA 20071728 — align 5.02 §6.6 to match
- [ ] **[Logic]** §6.5 Annual Audit Summary Report has no submission deadline — 5.07 requires this report as an input and imposes a 90-day post-fiscal-year deadline; evaluate whether 5.02 needs an explicit deadline to ensure the report is available in time
- [ ] **[Ref]** §5: Add LRDA 20071256 (Quality Assurance Review Audits and Reports) to Cited References if not already present — this is the governing retention schedule for QA review records

*Title normalized ✓ · Triennial assessment independence language verified ✓*

---

### 5.03 — Compliance Monitoring and Corrective Action 🟢

- [ ] **[Logic]** Confirm all upstream policies (particularly 1.09 post-POA&M→CAP replacement) correctly route to 5.03

*CAP workflow finalized ✓ · 5.01/5.02 references use current titles ✓*

---

### 5.04 — Performance Metrics and Operational KPIs 🟢

No action required. Purpose construction compliant, Cited/Framework split implemented, no title errors found.

---

### 5.05 — Security Control Assessment and Authorization 🟡

> **Dependency:** 5.02

- [ ] **[Standard]** Verify all internal cross-references to operational sub-processes are accurate after the 4.05 dual-identity numbering issue (see 4.01) is resolved — any pointer to 4.05 in this policy should reference the correct policy number once that decision is made

*Explicitly receives 5.02 results as inputs ✓ · Cited/Framework split present ✓*

---

### 5.06 — Vendor Compliance and Third-Party Assurance 🟡

> **Dependency:** 6.01

- [ ] **[Central]** "Vendor Compliance Record" is a coined ECIO term used extensively in 5.06 — must be added to Glossary 6.01 per 1.04 §6.14

*`System of Engagement (Redmine)` correctly formatted throughout ✓ · Cited/Framework split implemented ✓*

---

### 5.07 — Annual Policy Review and Maturity Scoring 🟡

> **Dependency:** 5.02, 1.05, 1.06

- [x] **[Draft]** Full content development — v2 draft complete, pending final review
- [x] **[Logic]** Scoring rubric uses NIST CSF 2.0 Tier criteria as an internal per-policy derivative — explicit disclaimer added in §6.3 that this is an operational analog, not a claim that NIST defines Tiers at individual-policy granularity
- [x] **[Logic]** Audit-the-Auditor function implemented in §6.4 — independently evaluates whether 5.02 audit program is executed as designed, including CJIS assessment cadences, objectivity safeguards, and findings routing
- [x] **[Logic]** §6 opening paragraphs explicitly subordinate 5.07 to 1.05: "operationalizes the annual internal review referenced in Policy 1.05 Section 6.1 and does not alter the review cadence, approval chain, or change control workflow established there"
- [x] **[Logic]** §4 Exceptions mirror 5.02 governance pattern: exceptions materially affecting the annual review require County Manager approval under 1.08 and 5.01
- [x] **[Logic]** §6.6 Board reporting triggers objectified with four (4) specific conditions — eliminates subjective "systemic deficiencies" / "governance-level awareness" language
- [x] **[Logic]** §6.8 retention trigger aligned with LRDA 20071256: "from the end of the calendar year to which they pertain"
- [x] **[Standard]** §5 Cited/Framework split implemented — NIST CSF/SP entries correctly placed in Framework Alignment (not cited by identifier in body); LRDA 20071256 added to Cited References
- [ ] **[Standard]** Title confirmed as "Annual Policy Review and Maturity Scoring" — all other policies cite consistently; no stragglers found
- [ ] **[QC]** Final 1.04 compliance pass: verify all quantity syntax, cross-reference parenthetical-title first-use-only rule, and contextual clarifier tags are clean across the full draft

*Cited/Framework split implemented ✓ · Audit-the-auditor obligation closed ✓ · 1.05 boundary explicitly defined ✓ · Board reporting triggers objectified ✓*

</details>

---

## Chapter 6 — Appendices

<details>
<summary>Click to expand Chapter 6</summary>

### 6.01 — Glossary and Definitions 🔴

> **Dependency:** Manual (all policies must be finalized first)

- [ ] **[Draft]** Mechanical harvest: extract all bolded first-use terms from Ch. 1–5 that meet inclusion criteria in 1.04 §6.14
- [ ] **[Logic]** De-duplicate harvested terms and verify each against inclusion/exclusion criteria in 1.04 §6.14
- [ ] **[Logic]** Add "Vendor Compliance Record" (flagged by 5.06) and the "System of Engagement" / "Case Management System" governance labels (flagged by 1.04)
- [ ] **[Logic]** Confirm capitalization of all governed terms is consistent with body-text usage across the manual

---

### 6.02 — Policy Matrix 🔴

> **Dependency:** Manual (all policies must be finalized first)

- [ ] **[Draft]** Policy Matrix (Table 1 — framework mapping) is **entirely empty**: all chapter rows are present but zero content in NIST 800-53, NIST CSF, CJIS, COBIT, and Statutory columns — full regeneration required
- [ ] **[Draft]** Policy Dependency and Integration Matrix (Table 2 — Feeds / Defers To / Receives From) is also **entirely empty** — full regeneration required
- [ ] **[Standard]** Ch. 4 and Ch. 5 rows are highest-priority additions per original task intent

---

### 6.03 — Workforce Roles STAK Matrix 🟡

> **Dependency:** 1.07

- [ ] **[QC]** Verify Tier L0–L5 role definitions are consistent with 1.07 §6.1 tier definitions and advancement criteria
- [ ] **[QC]** Confirm mandatory certification requirements listed (CompTIA A+ and Network+ within 12 months for Trainee) exactly match 1.07 §6.2

*STAK Matrix has content ✓*

---

### 6.04 — Work Order Structure and Standards 🔴

> **Dependency:** Manual (awaiting system configuration decision)

- [ ] **[GLOBAL-D]** Remove `JAVS`, `CentralSquare`, `Xerox` from Vendor Resolved status description — replace with `Case Management System` and `Managed Print Services` respectively; closes the 2.12 Xerox item
- [ ] **[GLOBAL-D]** Remove `Redmine` product-name references throughout — replace with `System of Engagement`; defer if pending system configuration decision (GLPI vs. Redmine)
- [ ] **[Operational]** Sync all field definitions and status workflow with final production system configuration before this appendix can be considered stable

---

### 6.05 — Revision History and Version Control 🔴

> **Dependency:** Git

- [ ] **[Draft]** Empty appendix — populate from Git commit history
- [ ] **[Draft]** Establish a consistent entry format (version, date, summary of changes, author/approver) defined either here or in 1.04

</details>

---

*Last updated: see Git commit history*
