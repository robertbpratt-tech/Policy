# ECIO Policy Manual — Repository Index

Authoritative index of the Elko County Information Operations (ECIO) Policy Manual, status of each policy, and reference materials used in tightening and verification.

**Operational sequencing, standing declines, and session protocols** are in [`TIGHTENING_PLAN.md`](TIGHTENING_PLAN.md). This file is the frontend status view; the plan is the backend.

## Status Key

| Code | Meaning |
| --- | --- |
| **L** | Locked — PRISTINE state; full ticket-list walked and applied; no changes without explicit authorization |
| **T** | Tightened, clean |
| **T+** | Tightened with open ripples |
| **D** | Drafted, untightened |
| **A** | Appendix |

## Compiled Manual

| File | Title | Status | Version | Tickets |
| --- | --- | --- | --- | --- |
| `Policy_Manual.lyx` | Master LyX Source (includes all child policy files) | | | |
| `Policy_Manual.pdf` | ECIO Policy Manual, Compiled | | | |

## Manual-Wide Open Roots

Cross-cutting tickets that do not belong to a single policy. These are absorbed during per-policy tightening (sweep-style) or held for a dedicated phase. See `TIGHTENING_PLAN.md` §3 for status of each root.

| Ticket | Scope |
| --- | --- |
| #6 | Product-name removal (Redmine) — multi-policy sweep |
| #208 | Standardize "All IT Personnel" → "All Information Operations Personnel" |
| #211 | Verify "Supervisors" matches Policy 1.07 §3 |
| #235 | Prohibited language sweep per Policy 1.04 §6.9 |
| #245 | Replace "business hours" with end-of-business-day convention |
| #264 | Role obligation redistribution (L3 prep, L1 clerical, L2 inputs, AID synthesis) |
| #353 | Uniform header: `Effective: July 01, 2026 | Version: 1.0` (Phase 10) |
| #355 | Manual-wide reference verification sweep — body-cite test + citation accuracy (all categories) (Phase 9) |
| #375 | Universal §6.X-strip sweep — strip section-specific depth from cross-policy body references |
| #456 | Manual-wide LyX CommandInset trailing-whitespace defects (children: #457, #458) |
| #464 | PDF publication quality — metadata, accessibility, ligatures (Phase 10) |
| #469 | Manual-wide `shall not` → positive `shall` directive sweep |
| #480 | Retention block architectural uniformity — three patterns across tightened policies (Phase 9-deferred) |

## Chapter 0 — Front Matter

| File | Title | Status | Version | Tickets |
| --- | --- | --- | --- | --- |
| `00/000.lyx` | Front Matter | L | v3.1 |  |

## Chapter 1 — Governance

| File | Title | Status | Version | Tickets |
| --- | --- | --- | --- | --- |
| `01/101.lyx` | Department Mission and Strategic Objectives | L | v1.1 |  |
| `01/102.lyx` | Code of Ethics and Professional Conduct | L | v2.4 |  |
| `01/103.lyx` | Standard Operating Ethos | L | v2.2 |  |
| `01/104.lyx` | Policy and Documentation Formatting Standards | L | v2.0 |  |
| `01/105.lyx` | Policy Review and Update Procedures | L | v2.4 |  |
| `01/106.lyx` | IT Governance and Oversight Structure | T+ | v2.2 | #491, #497, #502, #509, #535 |
| `01/107.lyx` | Workforce Roles, Responsibilities, and Competency Framework | T+ | v1.4 | #354, #495, #509, #513, #526 |
| `01/108.lyx` | Delegation of Authority and Decision Rights | T+ | v1.6 | #491, #495, #497, #503, #509 |
| `01/109.lyx` | Risk Management Policy | T+ | v2.2 | #491, #497, #502, #510, #513, #523, #526 |
| `01/110.lyx` | IT Financial Management and Procurement Policy | T+ | v2.3 | #488, #508, #512, #513 |
| `01/111.lyx` | Data Governance and Classification Policy | T+ | v2.5 | #482, #484, #488, #495, #502, #509, #510, #513, #526 |
| `01/112.lyx` | IT Asset Management Policy | T+ | v2.7 | #329, #426, #487, #509, #516, #537 |
| `01/113.lyx` | Supply Chain Risk Management (SCRM) and Vendor Governance | T+ | v2.4 | #484, #486, #492, #495, #509, #513, #521 |
| `01/114.lyx` | Stakeholder Engagement and Communications Policy | T+ | v2.4 | #491, #495, #499, #500, #510, #523, #526 |

## Chapter 2 — Security

| File | Title | Status | Version | Tickets |
| --- | --- | --- | --- | --- |
| `02/201.lyx` | Acceptable Use of Information Technology Resources Policy | T+ | v2.6 | #356, #486, #495, #507, #509, #526 |
| `02/202.lyx` | Personnel Security and Background Screening Policy | T+ | v2.8 | #487, #495, #502, #509 |
| `02/203.lyx` | Security Awareness and Training Policy | T+ | v2.2 | #502 |
| `02/204.lyx` | Access Control Policy | T+ | v2.8 | #453, #476, #495, #502, #509 |
| `02/205.lyx` | Identification and Authentication Policy | T+ | v2.3 | #495, #507, #510, #538 |
| `02/206.lyx` | Privacy and Data Protection Policy | T+ | v2.8 | #486, #495, #510 |
| `02/207.lyx` | System and Communications Protection Policy | T+ | v2.3 | #495, #507 |
| `02/208.lyx` | System Integrity and Malware Protection Policy | T+ | v2.1 | #486, #491 |
| `02/209.lyx` | Vulnerability and Patch Management Policy | T+ | v2.0 | #497 |
| `02/210.lyx` | Secure Configuration Baselines and Hardening Policy | T+ | v2.3 | #511 |
| `02/211.lyx` | Audit Logging and Monitoring Policy | T+ | v2.5 | #495, #497, #500, #502, #503, #507, #509, #526 |
| `02/212.lyx` | Media Protection and Sanitization Policy | T+ | v2.5 | #449, #497, #500, #503, #507, #516, #526 |
| `02/213.lyx` | Physical Security and Environmental Controls Policy | T+ | v2.4 | #497, #500, #502, #505, #509 |
| `02/214.lyx` | Mobile Device and Remote Access Policy | T+ | v2.0 | #513 |
| `02/215.lyx` | System Development and Secure Software Lifecycle Policy | T+ | v2.0 | #517, #524 |

## Chapter 3 — Service Management

| File | Title | Status | Version | Tickets |
| --- | --- | --- | --- | --- |
| `03/301.lyx` | Service Catalog and SLA Policy | T+ | v2.5 | #463, #495, #497, #500 |
| `03/302.lyx` | Service Level Management and Metrics Reporting | T+ | v2.6 | #309, #463, #486, #500, #509, #526 |
| `03/303.lyx` | Service Communications Policy | T+ | v2.1 | #491, #492, #500, #509 |
| `03/304.lyx` | Service Delivery Feedback and Grievance Policy | T+ | v2.2 | #484, #488, #495, #497, #523 |
| `03/305.lyx` | Service Request Fulfillment Policy | T+ | v2.2 | #463, #492, #500, #509 |
| `03/306.lyx` | Operational Incident Management Policy | T+ | v2.2 | #450, #463, #492, #498, #500, #527 |
| `03/307.lyx` | Problem Management Policy | T+ | v2.4 | #487, #491, #492, #500, #509, #526 |
| `03/308.lyx` | Service Configuration Management (CMDB) Policy | T+ | v2.3 | #461, #488, #490, #492, #500, #509, #523, #527 |
| `03/309.lyx` | Change Management Policy | T+ | v2.1 | #490, #492, #495, #498, #509, #527 |
| `03/310.lyx` | Release and Deployment Policy | T+ | v2.1 | #377, #486 |
| `03/311.lyx` | Capacity and Availability Management Policy | T+ | v2.1 | #451, #500 |
| `03/312.lyx` | Monitoring and Event Management Policy | T+ | v2.1 | #413, #495, #500, #514 |
| `03/313.lyx` | Knowledge Management Policy | T+ | v2.3 | #485, #488, #492, #495, #500, #509 |
| `03/314.lyx` | IT Project Management Policy | T+ | v2.3 | #478, #484, #492, #495, #509, #518 |
| `03/315.lyx` | Service Continuity and Contingency Planning Policy | T+ | v2.3 | #314, #492, #496, #500 |
| `03/316.lyx` | Service Improvement and Continual Improvement Plan | T+ | v2.1 | #452, #500 |
| `03/317.lyx` | System Maintenance and Vendor Repairs | T+ | v2.2 | #489, #492, #495, #500, #509 |

## Chapter 4 — Incident Response

| File | Title | Status | Version | Tickets |
| --- | --- | --- | --- | --- |
| `04/401.lyx` | Incident Response Policy Overview | T+ | v2.1 | #418, #457, #477, #486, #498, #500, #511, #513 |
| `04/402.lyx` | Identification and Reporting Procedures | T+ | v2.2 | #492, #495, #498, #499, #500, #513 |
| `04/403.lyx` | Containment Strategy and Playbooks | T+ | v2.2 | #495, #498, #500, #501, #504, #509, #513, #519 |
| `04/404.lyx` | Eradication Procedures and Scenario Guides | T+ | v2.4 | #485, #492, #495, #498, #500, #513, #527 |
| `04/405.lyx` | Recovery Operations and Restoration Prioritization | T+ | v2.4 | #458, #477, #485, #492, #495, #497, #498, #500, #504, #513, #520, #526 |
| `04/406.lyx` | Communication Protocols and Partner Integration | T+ | v2.3 | #378, #492, #498, #499, #500, #513, #523, #525 |
| `04/407.lyx` | Postmortem Review and Lessons Learned | T+ | v1.1 | #477, #478, #492, #498, #500, #502, #504, #513 |

## Chapter 5 — Compliance

| File | Title | Status | Version | Tickets |
| --- | --- | --- | --- | --- |
| `05/501.lyx` | Policy Implementation, Enforcement, and Legal Alignment | T+ | v2.0 | #495, #497, #523, #526, #540 |
| `05/502.lyx` | Internal Audits, Self-Assessment, and Control Testing | T+ | v2.0 | #482 |
| `05/503.lyx` | Compliance Monitoring and Corrective Action | T+ | v2.0 | #482, #488 |
| `05/504.lyx` | Performance Metrics and Operational KPIs | T+ | v2.0 | #522, #526 |
| `05/505.lyx` | Security Control Assessment and Authorization | T+ | v2.0 | #513 |
| `05/506.lyx` | Vendor Compliance and Third-Party Assurance | T+ | v2.0 | #523, #524, #526 |
| `05/507.lyx` | Annual Policy Review and Maturity Scoring | T+ | v2.0 | #525 |

## Chapter 6 — Appendices

| File | Title | Status | Version | Tickets |
| --- | --- | --- | --- | --- |
| `06/601.lyx` | Glossary and Definitions | L | v2.1 |  |
| `06/602.lyx` | Policy Matrix | A | — | #196, #197, #198, #459 |
| `06/603.lyx` | Workforce Roles STAK Matrix | A | — | #199, #200, #214 |
| `06/604.lyx` | Revision History and Version Control | A | v1.0 |  |

## Reference Materials

Authoritative sources fetched when verifying citations. Per the "no one-offs, no sneaks" rule, all reference materials live here — there are no out-of-repo staging paths or project attachments.

| File | Title | Status | Version | Tickets |
| --- | --- | --- | --- | --- |
| `Reference/01_CJIS_6.0.pdf` | FBI CJIS Security Policy v6.0 | | | |
| `Reference/03_NIST_800_53_R5.pdf` | NIST SP 800-53 Rev. 5 | | | |
| `Reference/05_COBIT_2019.pdf` | COBIT 2019 Guide | | | |
| `Reference/06_ITIL_v4.pdf` | ITIL v4 Guide | | | |
| `Reference/07_Nevada_Log_Retention.pdf` | Nevada Records Retention Schedules (full) | | | |
| `Reference/Governance_Map.md` | Quick COBIT and ITIL reference map | | | |
| `Reference/NICE Framework Components v2.1.0.xlsx` | NICE Framework Components Database v2.1.0 (machine-readable catalog) | | | |
| `Reference/NIST.CSWP.29-1.pdf` | NIST CSF 2.0 | | | |
| `Reference/NIST.SP.800-37r2-1.pdf` | NIST SP 800-37 Rev. 2 | | | |
| `Reference/NIST.SP.800-61r3-1.pdf` | NIST SP 800-61 Rev. 3 | | | |
| `Reference/NIST.SP.800-181r1.pdf` | NIST SP 800-181 Rev. 1 (NICE Framework — authoritative standard) | | | |
| `Reference/sfia-9_current-standard_en_250129.xlsx` | SFIA 9 Current Standard | | | |

## Repository Layout

```
Policy/
├── Policy_Manual.lyx        — master LyX file (includes all 00/–06/ children)
├── Policy_Manual.pdf        — compiled manual
├── README.md                — this file
├── TIGHTENING_PLAN.md       — operational plan, sequencing, standing declines
├── 00/ … 06/                — policy LyX source files by chapter
├── Audits/                  — section-audit trail artifacts (handoffs + close reports)
└── Reference/               — authoritative framework materials (PDF, xlsx, md)
```
