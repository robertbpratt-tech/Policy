# Section 6 Audit — Session Handoff

**Prepared:** May 1, 2026, end of §5 audit close session.
**Target session:** §6 audit, run after Phase 6 closes (E45 = 5.06, E46 = 5.07 capstone).
**Predecessor audits closed:** §1, §2, §3, §4, §5.
**Audit class:** Observation-only. Same protocol as the five preceding section audits.

---

## 1. Audit objective

**Audit the §6 section of each numbered policy** for structural compliance against Policy 1.04 and for voice / structural consistency across the corpus.

§6 is the **Standards** section in each policy — the substantive directives body. It is the largest and most varied section across the corpus. Where §1 (Purpose), §2 (Scope), §3 (Roles), §4 (Compliance), and §5 (References) each follow tight structural templates, §6 has only loose conventions. That looseness is intentional — the policy does its actual work in §6 — but it makes §6 the section most likely to harbor voice drift, role-anchoring gaps, compliance-verb misuse, sub-architecture variance, and stylistic inconsistencies that have accumulated across forty-odd tightening sessions.

This audit is the **per-policy §6 audit**, on the same model as §1–§5. Not the Chapter 6 Appendices.

---

## 2. Scope

**In scope:**

- The §6 section of each of the 60 numbered policies (Chapters 1–5):
  - `01/101.lyx` through `01/114.lyx` — Chapter 1 Governance.
  - `02/201.lyx` through `02/215.lyx` — Chapter 2 Security.
  - `03/301.lyx` through `03/316.lyx` — Chapter 3 Service Management (subset numbers).
  - `04/401.lyx` through `04/407.lyx` — Chapter 4 Incident Response.
  - `05/501.lyx` through `05/507.lyx` — Chapter 5 Compliance.
- Structural compliance against 1.04 §6.X conventions as they apply to §6 body content.
- Voice and structural consistency across policies.
- In-body cross-reference compliance (1.04 §6.11) and clarifier tag compliance (1.04 §6.12, post-amendment) within §6.

**Out of scope:**

- `00/000.lyx` (Front Matter), `06/601.lyx` through `06/604.lyx` (Appendices), `Policy_Manual.lyx` (master). The Chapter 6 Appendices have a different audit model and are deferred until after Phase 7.
- §1, §2, §3, §4, §5 — already audited.
- Substantive content rewrites of directives. If audit surfaces a structural defect that requires substantive content review (e.g., a directive whose role anchor needs to change because the role doesn't exist in 1.07), file a Phase 9 ticket; do not rewrite content during audit.
- Framework citation accuracy verification — deferred to #355 (manual-wide reference verification sweep — body-cite test + citation accuracy across all categories; expanded May 1, 2026 per IT Director Q1 ruling on §5 audit).

---

## 3. Spec authority — fetch fresh at session start

**Mandatory at session start (same as §1–§5 protocol):**

1. `01/104.lyx` — Policy 1.04 (constitutional). Pull the full text. Particular attention to whichever §6.X subsection(s) define §6 (Standards) section conventions for other policies. **Do not rely on memory or summaries** — three §3-audit false positives traced to memory-driven structural assertions. Source-anchored rulings only.
2. `README.md` — repository layout and per-policy state.
3. `TIGHTENING_PLAN.md` — operational backend; standing declines (§4); locked architectural decisions (§3); session-flow protocols.

**Behavior:** any rule applied during audit shall be sourced to a specific 1.04 §6.X subsection. If a rule's source can't be located in 1.04, the rule is not yet constitutional and the finding becomes a §6.X amendment candidate (parallel to how §4 surfaced §6.6 amendment, §5 surfaced §6.11 amendment).

---

## 4. Likely 1.04 spec anchors (verify at session start; not exhaustive)

These are the 1.04 sections most likely to govern §6 body content. Pull each fresh; do not work from this list as definitive.

- **§6.5 — Language Compliance.** Compliance verb use (shall / must / should / may); prohibited terminology; sentence-form conventions for directives.
- **§6.6 — Section 4 (Compliance) Template.** Locked May 1, 2026 to mandatory-three (Assessment / Enforcement / Exceptions) with Sanctions as the only governed optional. Bears on the §4↔§6 architectural boundary — what content belongs in §6 vs §4.
- **§6.7 — References Section Template.** Governs §5 directly, but the body-cite test (Cited References must appear in §6 body) gives §6 audit a verification surface.
- **§6.9 — Time and Quantity Syntax.** Numerals, spelled-out quantities, time conventions, dates.
- **§6.10 — Prohibited Terminology.** Product names (Redmine sweep #6 ongoing); institutional capitalization conventions; entity-naming conventions.
- **§6.11 — Cross-Reference, Citation, and Bold Standards.** In-body cross-references via `\begin_inset CommandInset ref` insets; first-use parenthetical title rule for ECIO Policy refs; bold usage restrictions; Glossary-defined terms bolded on first use; structural-label bolding. **Note: §6.11 amendment lands in v1.6 (Ticket #515).**
- **§6.12 — Clarifier Tags.** Locked May 1, 2026 to Rationale + Exception only (Constraint / Clarification / Exclusion stripped). **Note: §6.12 amendment lands in v1.6 (Ticket #509). 49 use-sites manual-wide pending Phase 5F strip-and-restructure.**
- **§6.13 (likely) — Appendix Structure Template.** May or may not bear on §6 audit; appendices are out of scope for this audit but §6.13 may also specify cross-cutting structural rules.
- **§6.14 (likely) — Glossary Inclusion Criteria.** Ties to §6.11 bolded-first-use rule. §6 body content's bolded-term first-uses determine Glossary entry candidates; relevant to §6 audit when bolded terms appear in §6 prose.
- **§6.15 (post-v1.4 consolidation) — Procedural and Informational Documentation.** Locked April 23, 2026; may bear on §6 boundary against operational documentation.

Plus any §6.X subsection that explicitly governs the §6 (Standards) section template itself. **Verify directly.**

---

## 5. Method — same protocol as §1–§5

1. Fetch authoritative files from GitHub at session start (TIGHTENING_PLAN.md always fetched fresh).
2. Memory / state sync.
3. Build §6 extractor — locate `\begin_layout Subsection*` containing "Standards" (or whatever the canonical §6 label is — verify; some policies may use "Policy Standards" or similar). Walk §6 body parsing every layout block (Standard, Itemize, Enumerate, Subsubsection*) into typed entries.
4. Build structural-compliance analyzer covering as many §6.X-derived rules as can be tested mechanically:
   - Subsection numbering convention (do §6.X subsections exist? sequential? consistent depth?).
   - Compliance verb distribution (shall / must / should / may — flag prohibited, flag missing in directive sentences).
   - Role-anchoring (every directive sentence anchored to a capitalized role from Policy 1.07's role catalog).
   - Cross-reference inset usage (every "Policy X.XX" body reference uses `CommandInset ref`; first-use parenthetical title present; subsequent uses short-form).
   - Bolding usage (limited to defined-term first-use, structural labels, in-body cross-references; not used for emphasis).
   - Clarifier-tag usage (post-amendment Rationale + Exception only; Constraint / Clarification / Exclusion strip candidates).
   - Time / quantity syntax compliance.
   - Prohibited terminology occurrences.
5. **Voice and structural consistency analyzer** — cross-policy patterns:
   - §6 sub-architecture variance (do similar policies use similar §6.X structures? where do they diverge?).
   - Sentence-opener variance (imperative voice consistency; passive-voice drift).
   - Parallel-construction within enumerated lists.
   - Acronym introduction conventions (first use spelled out with parenthetical acronym; subsequent uses as acronym).
6. Produce **Findings Summary** — defect IDs continue from §5 audit (which ended at D30). §6 audit starts at **D31+**. Class-by-class breakdown with location, current text or condition, issue, proposed revision, GitHub issue numbers for tracked defects.
7. **Adjudication queue** for spec gaps, voice rulings, and architectural questions surfaced. Many §6 findings will need IT Director judgment because §6 has fewer mechanical templates than §1–§5.
8. **Ticket package** filed at session close after IT Director ruling. Letter codes continue from §5 audit (NN was last); §6 audit can use OO, PP, QQ, RR, etc.
9. **Plan + README updates** committed sequentially (plan first, README second, fresh SHA before each PUT, base64 with `-w0`, JSON payload via `-d @file.json`).

---

## 6. Why §6ing audit is "involved"

Three structural reasons it's bigger than §1–§5:

**6.1 No tight template.** §1, §2, §3, §4, §5 each have a 1.04-defined structural template that produces a clean mechanical floor (e.g., §4 mandatory-three bullets, §5 two-subsection split). §6 has only loose conventions. The mechanical floor will be lower (fewer "all 60 pass cleanly" tests) and the variance surface will be larger.

**6.2 Largest section in every policy.** §6 is where the policy does its substantive work. Per-policy line counts in §6 typically dwarf §1–§5 combined. The volume of text under audit is multiples of any prior audit.

**6.3 Voice is qualitative.** Cross-policy voice consistency is harder to audit programmatically than structural compliance. Some findings will require pattern-recognition and human judgment that an extractor + analyzer can flag but not classify. Expect the adjudication queue to be larger than §5's six Qs.

These are reasons for a dedicated session, not reasons to defer. The audit is necessary; it's the last section audit before Phase 5F can execute.

---

## 7. Reference materials in repo

All in `Reference/`. Same set used during §5 audit:

- `01_CJIS_6.0.pdf` — FBI CJIS Security Policy v6.0.
- `03_NIST_800_53_R5.pdf` — NIST SP 800-53 Rev. 5.
- `07_Nevada_Log_Retention.pdf` — Nevada Local Government Records Retention Schedule.
- `NIST.CSWP.29-1.pdf` — NIST Cybersecurity Framework 2.0.
- `NIST.SP.800-37r2-1.pdf` — NIST SP 800-37 Rev. 2.
- `NIST.SP.800-61r3-1.pdf` — NIST SP 800-61 Rev. 3.
- `NIST.SP.800-181r1.pdf` — NIST SP 800-181 Rev. 1 (Workforce Framework for Cybersecurity / NICE Framework).

Framework verification not in scope for §6 audit (deferred to #355). Reference PDFs are present for any spec anchoring that requires them.

---

## 8. Working materials available

Carry-forward from §1–§5 audit closes:

- `Section1_Audit_Report.md` through `Section5_Audit_Report.md` — full audit deliverables.
- `section1_*.json` through `section5_*.json` — per-section extractor / analyzer output JSON.
- `extract_section*.py` — extractor scripts. **§5's extractor is the closest template — it walked layout blocks with depth tracking and parsed typed entries.** §6 extractor will be more complex because §6 contains all layout types (Standard, Itemize, Enumerate, Subsubsection*) with mixed prose and enumeration.
- `analyze_section*.py` — analyzer scripts. The §3 (voice) and §4 (structural) analyzers are the closest templates. §6 analyzer needs both.
- `update_readme*.py` and `commit_section*_close.py` — README update + commit pattern. Reusable templates.

---

## 9. Established conventions (carry-forward)

**GitHub API patterns:**
- Raw content fetch: `curl -sS -H "Accept: application/vnd.github.raw+json" -H "Authorization: Bearer $TOKEN"`.
- Issue filing via `urllib.request`: `POST /repos/{REPO}/issues` with `labels` array (only pre-existing label strings; unrecognized labels silently dropped).
- Cross-reference patching: placeholder pattern `#TICKET_X_NUMBER` in ticket bodies, sweep PATCH after all numbers assigned.
- Sequential commits: plan first, README second, fresh SHA before each PUT, base64 with `-w0` no line wrapping, payload via `-d @/tmp/file.json`.

**Adjudication discipline (from §3 audit lesson):**
- When a finding looks structural, verify against 1.04 source. Memory-driven structural assertions produced false positives.
- Where 1.04 is silent or ambiguous, surface the gap for IT Director adjudication. Do not assume a default.
- Spec gaps that surface during audit produce 1.04 amendments (parallel to §6.6 #506, §6.11 #515, §6.12 #509). The amendment couples into the next available v-release.

**Ticket structure precedent:**
- §1 audit: 2 tickets.
- §2 audit: 6 tickets.
- §3 audit: 6 tickets (plus #493 closed).
- §4 audit: 11 tickets (plus #481, #493 absorbed).
- §5 audit: 11 tickets (plus #355 scope amendment).
- **§6 audit: TBD; likely larger surface.** Expect 12–20 tickets given the larger variance surface.

---

## 10. Authoritative state at handoff

### Phase 6 status

44 / 49 closed at §5 audit close (May 1, 2026). **Two entries remain and must complete before §6 audit begins:**

- **E45 = 5.06** — Service Continuity and Disaster Recovery Policy (state D, 6 open tickets per current README).
- **E46 = 5.07** — Annual Policy Review and Maturity Scoring (capstone; state D).

Sequencing rationale (locked May 1, 2026):
1. **Corpus completeness.** §6 audit benefits from running against a complete T-state corpus. Auditing before 5.06 / 5.07 tighten means audit findings have to be re-evaluated against the post-tightening §6 of those two policies.
2. **Phase 5F intake clean window.** Phase 5F gates on (Phase 6 closed) AND (all section audits closed). Doing 5.06 / 5.07 first means Phase 5F has a single clean intake window after §6 audit closes, with no further tightening churn.
3. **5.07 capstone discipline.** 5.07 (audit-the-auditor) belongs in the corpus before any audit-class work runs against the section that contains its directives.

After E46 closes, Phase 6 marker recalculates in `TIGHTENING_PLAN.md`. §6 audit opens after that recalc.

### Phase 5F intake state

**36 tickets** at §5 audit close (May 1, 2026):

- §1 audit: #484, #485 (2 tickets).
- §2 audit: #486–#491 (6 tickets).
- §3 audit: #492, #494, #495, #496, #497, #498 (6 tickets; #493 closed, absorbed by #509).
- §4 audit: #499–#509 (11 tickets; #481 closed, superseded by #500).
- §5 audit: #510–#520 (11 tickets).
- Plus #355 (manual-wide reference verification sweep; scope expanded May 1, 2026).

§6 audit will add to this intake. Phase 5F gating remains: (Phase 6 closed) AND (all section audits closed) → execute as unified per-policy patch-bump cleanup pass before Phase 7 (Chapter 6 Appendices).

### v1.6 release scope (post-§5)

**Five constitutional amendments** to 1.04, gated for single coupled v1.5 → v1.6 release commit:

- **§6.5 (#494)** — locked authority sequence + flat institutional-title-before-Department-Heads sub-rule.
- **§9.1 (#498)** — `(as Incident Commander)` clarifier convention.
- **§6.6 (#506)** — optional-bullet set narrowed to Sanctions only; mandatory-three contiguity locked.
- **§6.11 (#515)** — CJIS Section-drop + v6.0 form lock; CJIS Appendix permission; publication-level NIST SP permission; NIST SP 800-37 RMF-step permission; NIST CSF Subcategory required.
- **§6.12 (#509)** — governed clarifier-tag set narrowed to Rationale + Exception.

If §6 audit surfaces additional amendment candidates (likely, given the larger variance surface), they couple into v1.6 if the release hasn't shipped, or v1.7 if it has.

### Locked architectural decisions affecting §6 audit

From `TIGHTENING_PLAN.md` §3, key items relevant to §6 body content:

- "IT Director (as LASO)" role anchor convention — fully established in 1.10, 1.11, 1.13, 1.14. Verify §6 body anchoring.
- Sanitization authority consolidated exclusively in Policy 2.12 — flag any §6 body anchoring this elsewhere.
- IC role is not a 1.07 standing role; IC = IT Director + designee with non-transfer clause for CCA / exceptions / classification.
- "All County Personnel" universal §3 group label (not "All Users of County IT Resources"). Pattern #23 standing decline. Watch for §6 body reverting.
- Default-deny posture for subcontractor approval silence.
- 24-calendar-hour non-CJI vendor incident notification threshold.
- §6.X depth not permitted in body cross-references — strip-at-next-touch sweep ongoing per #375.

### Open standing decline patterns (30 active per Plan §4)

Pattern stack relevant to §6 audit includes (not exhaustive): #20 cross-policy dependency citation, #23 "All County Personnel" label substitution, #29 third-recurrence locked-operational-reality rule, #36 / #37 / #39 / #41 inline non-waivable list patterns, plus the new #40 from Phase 5D.2 Option A recovery gate. Adjudicate every cross-validator finding against current source and Plan §4 before acceptance — agreement between ChatGPT and Gemini is not evidence the finding is correct; it may indicate shared access to the same stale version.

---

## 11. Output expectations

At session close, produce:

1. **`Section6_Audit_Report.md`** — full audit deliverable (working document; mirror to `/mnt/user-data/outputs/`).
2. **Ticket package** — filed under continuing letter-code convention (OO, PP, QQ, ...) and assigned GitHub numbers contiguously.
3. **#TICKET_X_NUMBER placeholder sweep** — all internal ticket cross-references patched after numbers assigned.
4. **Plan update** — §6 audit close note inserted parallel to §1–§5 close notes; Phase 5F intake count updated; v1.6 amendment list updated if new amendments surface.
5. **README update** — per-policy ticket assignments added for affected policies.
6. **Sequential commits** — plan first, README second, with descriptive commit messages.
7. **Audit deliverable mirror** in `/mnt/user-data/outputs/Section6_Audit_Report.md` for IT Director access outside the session.

After §6 audit closes, Phase 5F gating clears: (Phase 6 closed ✓) AND (all section audits closed ✓). Phase 5F execution can then open as a unified per-policy patch-bump cleanup pass.

---

## 12. Authority and behavioral discipline

Same as preceding audits, summarized:

- **Auditor's Pen** — assume every sentence reviewed by hostile auditor. Eliminate ambiguity, define terms, anchor directives.
- **Locked Inputs** — IT Director rulings in this session, prior sessions, or Plan-tracked architectural decisions are locked. Build on them. Do not re-propose alternatives or synthesize mediating framings that quietly rewrite locked decisions. If a downstream conflict appears, surface flatly.
- **Option-Setting Discipline** — when proposing options under a locked architectural decision, state the architectural frame first, offer only options compatible with that frame.
- **Behavioral pattern (May 1, 2026 inscription):** When IT Director authorizes commit and ripple housekeeping in one message, EXECUTE immediately. Do not insert a second pre-commit pause. Authorization phrases include "make it happen," "go ahead," "yes, please," and any clear ruling on filed Qs.
- **Cross-validator discipline** — ChatGPT, Gemini do not have access to current tightened source or Plan §4 standing declines. Validator agreement is not evidence the finding is correct. Adjudicate every finding against current source and Plan §4.
- **Robert tells you when the session is complete.** Do not ask.

---

## 13. Pre-session checklist

Before this handoff is consumed, the following must be true:

- [ ] Phase 6 closed (E45 = 5.06 committed; E46 = 5.07 committed; Phase 6 marker recalculated in `TIGHTENING_PLAN.md`).
- [ ] No active Phase 6 entries in flight.
- [ ] §1–§5 audit reports preserved in working materials.
- [ ] Ticket numbers from §5 audit close (#510–#520) confirmed open and accessible.
- [ ] #355 scope amendment confirmed landed (title and body amended May 1, 2026).
- [ ] v1.6 amendment package known: §6.5, §9.1, §6.6, §6.11, §6.12 (five amendments queued).
- [ ] PAT valid for repository access (re-issue if expired before session opens).

When all check, open the §6 audit session and run the protocol above.

---

*End of handoff.*
*Working document. Source of truth is the LyX corpus + `TIGHTENING_PLAN.md` + filed tickets.*
