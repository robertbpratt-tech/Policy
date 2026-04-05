# ECIO Policy Manual — Cleanup Obligation List
## Based on manual state as of April 5, 2026

---

## 1.07 — Add training compliance verification clause

**Status:** Outstanding.

**What:** Add to Section 4 (Compliance and Exceptions) a clause establishing
that certification currency and training completion are verified annually as
part of the competency assessment. This absorbs the oversight function of the
eliminated 5.08.

**Why:** The old 5.08 (Training, Certification, and Role-Based Access
Alignment) was eliminated. Its compliance verification function needs a home.
1.07 already handles role boundaries and competency — add the verification
that required certs/training are current as a compliance checkpoint.

**Suggested language direction:** "The IT Director or designee shall verify
annually that all personnel maintain current certifications and training
completions required by their assigned tier in Appendix 6.03. Lapsed
certifications shall trigger the access eligibility consequences defined in
Section 6 of this policy."

---

1.09 — Rename POA&M to CAP and route lifecycle to 5.03 (rewrite-pass)

Status: Outstanding — queued for global rewrite pass.

What: Policy 1.09 uses "Plan of Action and Milestones (POA&M)" throughout Sections 3, 4, 6.4, and 6.7. The Department has standardized on "Corrective Action Plan (CAP)" as the sole term for remediation tracking instruments. Policy 5.03 defines CAPs as the Department's implementation of NIST SP 800-53 CA-5 and governs the CAP lifecycle.

Action: Replace all instances of "Plan of Action and Milestones (POA&M)" and "POA&M" with "Corrective Action Plan (CAP)" and "CAP" throughout 1.09. Update the Risk Register minimum data field from "POA&M Linkage" to "CAP Linkage" in Section 6.7. Add a sentence in Section 6.4 or 6.7 routing CAP lifecycle governance to Policy 5.03. Update the Section 5 citation title from "Compliance Monitoring and Corrective Action Policy" to "Compliance Monitoring and Corrective Action."

Affects: 1.09 Sections 3, 4, 6.4, 6.7, and Section 5.

---

## 2.03 — Add training-to-access-review linkage

**Status:** Outstanding.

**What:** Add a clause in Section 6 establishing that the annual access review
process (Policy 2.04) shall include verification of current training status,
and that lapsed training constitutes grounds for access suspension.

**Why:** This closes the gap left by eliminating 5.08.

---

## ~~4.01 — Interface map paragraph rewrites~~ ✅

**Status:** Complete.

The Policy Statement in 4.01 contains a fully rewritten interface map. All
paragraphs have correct headings and descriptions:

- "Policy 4.08 — Incident Response Roles and Contact Directory" — correct.
- "Policy 4.06 — Communication Protocols and Partner Integration" — correct,
  reflects partner integration as a dedicated subsection of 4.06.
- "Policy 4.07 — Postmortem Review and Lessons Learned" — correct.
- "Policy 4.05 — Data and System Classification for Recovery" — present and
  correctly described as support infrastructure. Verify content accuracy once
  4.05 is drafted.

---

## 4.05 — Absorb classification content when writing this stub

**Status:** Outstanding — blocked on stub drafting.

**What:** When you write Policy 4.05 (Recovery Operations and Restoration
Prioritization), include the data and system classification for recovery
content that was the old 4.07. This should be a subsection within 4.05's
Policy Statement — the recovery classification tiers, the criteria for
classification, the review cadence.

**Fulfills promises made by:** 4.01 (12 refs), 4.02 (3 refs), 4.03 (1 ref).
Section 5 citations in 4.01 and 4.02 already correctly read "ECIO Policy
4.05: Data and System Classification for Recovery." The 4.01 interface map
already contains two correctly described paragraphs for 4.05 (one for
recovery operations, one for classification).

---

## 4.06 — Absorb partner integration content when writing this stub

**Status:** Outstanding — blocked on stub drafting.

**What:** When you write Policy 4.06 (Communication Protocols and Partner
Integration), include the external partner engagement content that was the
old 4.10. MS-ISAC, FBI, CISA, NV DPS engagement criteria and procedures
should be a subsection.

**Fulfills promises made by:** 4.01 (4 refs), 4.02 (2 refs). All
cross-references now correctly point to 4.06 (Part 1 fix verified).

---

## 1.02 — Consolidate CJIS PS-8 notification detail into 5.01 (rewrite-pass)

**Status:** Outstanding — queued for global rewrite pass.

**What:** Policy 1.02 Section 4 currently contains its own detailed CJIS PS-8
notification language. Policy 5.01 Section 6.5 now also contains this
language. During the rewrite, the detailed CJIS sanctions notification
process should live in one place.

**Action:** Keep 1.02's "Formal Process" bullet as a principle statement and
add a cross-reference to 5.01 for the operational detail. Replace inline
CJIS notification procedure with "in accordance with the formal sanctions
process and CJIS notification requirements defined in Policy 5.01."

**Affects:** 1.02 Section 4 (Sanctions, Formal Process, and CJIS Notification
bullets)

---

## 1.03 — Remove inline enforcement escalation examples (rewrite-pass)

**Status:** Outstanding — queued for global rewrite pass.

**What:** Policy 1.03 Section 4 currently includes "including coaching,
supervisory feedback, or formal performance management" after the 5.01
reference. Now that 5.01 Section 6.3 defines the full governed list, the
inline examples are redundant and constraining.

**Action:** Replace with "corrective action in accordance with Policy 5.01."

**Affects:** 1.03 Section 4 (Enforcement bullet)

---

## 1.03 — Tighten "Documentation as Standard" scope (rewrite-pass)

**Status:** Outstanding — queued for global rewrite pass.

**What:** Policy 1.03 Section 6 currently states "All operational actions,
changes, and decisions shall be documented..." The absolute phrasing may
invite technical non-compliance by volume.

**Action:** Narrow to material operational actions, security-relevant actions,
service-affecting changes, enforcement actions, and decisions that establish
direction or disposition. Once 1.03 is tightened, update 5.01 Section 6.1
to match.

**Affects:** 1.03 Section 6 body text and 5.01 Section 6.1

---

## 1.07 — Verify tier reassignment language consistency with 5.01 (rewrite-pass)

**Status:** Outstanding — queued for global rewrite pass.

**What:** Verify that 1.07's language about tier reassignment consequences,
access suspension triggers, and reinstatement conditions aligns with 5.01
Sections 6.3 and 6.6.

**Affects:** 1.07 Section 6 body text

---

## 3.04 — Verify grievance pathways cover enforcement actions vs. decisions (rewrite-pass)

**Status:** Outstanding — queued for global rewrite pass.

**What:** Verify that 3.04 Section 6.3 explicitly handles the scenario where
a department head disputes an enforcement *action* (e.g., access revocation
already executed) — not just an enforcement *decision*.

**Likely finding:** 3.04 already covers both, but confirm during rewrite.

**Affects:** 3.04 Section 6.3

---

## 5.07 — Audit-the-auditor function (when drafting 5.07)

**Status:** Outstanding — blocked on stub drafting.

**What:** Policy 5.02 cannot reference itself in its own Section 4 Assessment
clause. When drafting 5.07, its scope shall explicitly include evaluating
whether the audit program defined in Policy 5.02 is being executed as
designed.

**Affects:** Policy 5.07 (scope and Policy Statement)

---

## 5.05 — Receive 5.02 test results without parallel testing (when drafting 5.05)

**Status:** Outstanding — blocked on stub drafting.

**What:** Ensure 5.05 explicitly receives 5.02 control test results and audit
findings as inputs to authorization decisions without re-creating a parallel
testing methodology. The boundary: 5.02 owns testing mechanics, 5.05 owns
the authorization decision. If 5.05 requires specialized assessment types
(penetration testing, vulnerability scanning), define them in 5.05 and
cross-reference back to 5.02.

**Affects:** Policy 5.05 (Policy Statement)

---

# PART 4: POST-STUB WORK

Do these after all stubs are written and all references are fixed.

---

- **Appendix 6.02 (Policy Matrix):** Full regeneration. Every Ch4 and Ch5 row
  changes. Dependency matrix (Table 2) also needs updating.

- **Appendix 6.01 (Glossary):** Populate. Tyler will look for this.

- **Purpose section openings:** 31 policies still use "The purpose of this
  policy is to..." which 1.04 Section 6.3 prohibits. Batch fix to "This
  policy [verb]s..." Confirmed policies: 1.01, 1.02, 1.03, 1.05, 1.07, 1.08,
  1.10, 1.12, 2.07, 2.08, 2.09, 2.10, 2.12, 2.13, 2.14, 2.15, 3.01, 3.02,
  3.03, 3.04, 3.05, 3.06, 3.07, 3.08, 3.09, 3.10, 3.11, 3.12, 3.13, 3.14,
  3.16.

- **CJIS reference format:** 17 old-format Section 5.x references remaining
  (up from 12 in previous audit — additional body text references identified).
  Breakdown: "Section 5.1" (7x), "Section 5.1.1.4" (3x — 1 citation + 2 body
  text), "Section 5.1.1.5" (1x), "Section 5.1.1.6" (1x), "Section 5.9" (2x —
  1 citation + 1 body text ref to 5.9.1), "Section 5.12" (1x), "Section
  5.20.7.2" (1x — body text in 2.14, not in previous audit). Standardize to
  NIST control family format.

- **Cross-reference pruning:** Apply the Cited References / Framework
  Alignment split across all policies during tightening pass. Currently 3
  policies implement the split: Policy 1.04 (the style guide itself), Policy
  5.01, and Policy 5.02.

- **Prose tightening:** General cleanup, consistency, terminology
  standardization.

- **Policy 2.01 title verification:** Verify the official h1 title in the LyX
  master. Locked policies and 5.01 cite it as "Acceptable Use Policy," but
  the full title may be "Acceptable Use of Information Technology Resources
  Policy." The TOC and 5.01 currently use the long form.

- **Policy 1.14 title/scope review:** Titled "Stakeholder Engagement and
  Communications Policy" but used in 5.01 Section 6.2 as the anchor for
  contractor/vendor access-acknowledgment conditions. Evaluate whether to
  narrow the title, restructure the 5.01 citation, or keep as-is.

- **Policy 5.01 title standardization:** Authoritative h1: "Policy
  Implementation, Enforcement, and Legal Alignment." 32 cross-references use
  old title "Policy Implementation and Enforcement Framework." Only 4 use the
  correct title (5.01 itself + 5.02 + select others). Affects ~32
  parenthetical title references.

- **Policy 5.02 title standardization:** Authoritative title: "Internal
  Audits, Self-Assessment, and Control Testing." 15 citations use old title
  "Internal Audits and Self-Assessment Procedures." Only 4 use the correct
  title. Affected policies: 1.04, 1.14, 3.05, 3.06, 3.08, 3.09, 3.10, 3.11,
  3.12, 3.13, 3.14, 3.15, 3.16, 3.17, 4.01.

- **Section 4 enforcement clause standardization:** ~27 instances use "under
  Policy 5.01" or variants; ~4 use "in accordance with Policy 5.01." Target
  standard: "corrective action in accordance with Policy 5.01."

- **Section 4 exception clause standardization:** Append "in accordance with
  the exception management framework established in Policy 5.01" to each
  policy's exception clause. Currently 1 policy uses this construction.

---

# PART 5: PRE-OPERATIONAL ITEMS

Items to resolve before the manual is operationally activated, but which do
not require changes to policy text.

---

## Acknowledgment lapse rule — CBA sensitivity review

**What:** Policy 5.01 Section 6.2 establishes a thirty (30) day acknowledgment
lapse rule that triggers access suspension.

**Action:** Discuss with the County Attorney before the manual goes live.

---

## County Manager enforcement — Operational SOP

**What:** Build a separate internal operational SOP in Redmine capturing the
County Manager-specific procedural detail from the County Attorney's opinion
(Rand, 08/04/2023).

---

## Dependency 4.02-A — Chapter 4 checklist template

**What:** Chapter 4 checklist template must be drafted and staged in the
Redmine Knowledge Base before Policy 4.02 can be operationally activated.
Queue for Policy 3.13 build-out.

---

# QUICK REFERENCE: THE FULL RENUMBERING MAP

## Policies
| Old # | Old Title | New # | What Happened | Ref Fix Status |
|-------|-----------|-------|---------------|----------------|
| 4.07 | Data/System Classification for Recovery | — | Merged into 4.05 | ✅ Done |
| 4.08 | Postmortem Review and Lessons Learned | 4.07 | Renumbered | ✅ Done |
| 4.09 | Incident Response Roles and Contact Directory | 4.08 | Renumbered | ✅ Done (was misrouted to 4.07 — fixed) |
| 4.10 | Integration with Local, State, and Federal Partners | — | Merged into 4.06 | ✅ Done (was misrouted to 4.07 — fixed) |
| 5.03 | Control Testing and Validation Schedule | — | Merged into 5.02 | ✅ Done |
| 5.04 | Compliance Monitoring and Corrective Action | 5.03 | Renumbered | ✅ Done |
| 5.05 | Performance Metrics and Operational KPIs | 5.04 | Renumbered | ✅ Done |
| 5.06 | Security Control Assessment and Authorization | 5.05 | Renumbered | ✅ Done |
| 5.07 | Vendor Compliance and Third-Party Assurance | 5.06 | Renumbered | ✅ Done |
| 5.08 | Training, Certification, and RBAC Alignment | — | Eliminated (absorbed into 1.07 + 2.03) | N/A |
| 5.09 | Legal and Regulatory Alignment | — | Merged into 5.01 | ✅ Done |
| 5.10 | Annual Policy Review and Maturity Scoring | 5.07 | Renumbered | ✅ Done (was misrouted as 5.06 — fixed) |
| 5.11 | Breach and Incident Reporting Compliance | — | Merged into 5.03 | N/A |

## Appendices
| Old # | Old Title | New # | What Happened | Ref Fix Status |
|-------|-----------|-------|---------------|----------------|
| 6.02 | Framework Reference Links | — | Killed | ✅ Done |
| 6.03 | Policy Matrix | 6.02 | Renumbered | ✅ Done |
| 6.04 | Revision History and Version Control | 6.05 | Renumbered | ✅ Done |
| 6.05 | Workforce Roles STAK Matrix | 6.03 | Renumbered | ✅ Done |
| 6.06 | Work Order Structure and Standards | 6.04 | Renumbered | ✅ Done |
| 6.07 | Risk Assessment Matrix | — | Killed (scoring methodology → 1.09 body or Redmine) | Decision pending |
| 6.08 | Supporting Documentation | — | Killed (templates → Redmine) | ✅ Done (was hardcoded in 2.01 — fixed) |
