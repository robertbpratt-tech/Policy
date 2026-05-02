# ECIO Section Audit — Handoff for Sections 4, 5, 6

**Prepared:** May 1, 2026
**For:** Incoming session, Sections 4–6 audit work
**From:** Outgoing session (Sections 1, 2, 3 audits closed)
**Repository:** `robertbpratt-tech/Policy`
**IT Director:** Robert Pratt

---

## 1. What you're walking into

The IT Director ran a section-by-section consistency audit of the ECIO Policy Manual. Sections 1, 2, 3 are **closed** with 15 cleanup tickets filed (#484 through #498). Sections 4, 5, 6 are pending — your job.

The audit is not policy tightening. It is structural / formatting / role-label consistency work against 1.04's section templates. Tickets file at section close; execution is **deferred to Phase 5F** (a unified per-policy patch-bump cleanup pass that runs after Phase 6 closes and all six section audits complete).

You are **not** executing the cleanups. You are **finding and filing** them.

---

## 2. Repository state at handoff

**Phase 6 progress:** 44 of 49 entries closed. Remaining: E45 (5.06), E46 (5.07).

**Most recent commits** (top of the stack as of May 1, 2026 19:12 UTC):

```
681f5146 | 2026-05-01T19:12:50Z | README: Ticket N (#498) — 10 rows updated
a5aba818 | 2026-05-01T19:12:49Z | Plan: D20.6 IC arch resolved — Option B; Ticket N filed
d9550082 | 2026-05-01T18:57:38Z | README: §3 audit ticket assignments (#492-#497) — 41 rows
6c0abfef | 2026-05-01T18:57:37Z | Plan: §3 audit close — Phase 5F intake +6 (#492-#497)
25753471 | 2026-05-01T16:01:47Z | README: §2 audit ticket assignments (#486-#491) — 28 rows
f2cc5241 | 2026-05-01T16:01:46Z | Plan: §2 audit close — Phase 5F intake +6 (#486-#491)
2fbd74e7 | 2026-05-01T15:12:46Z | README: §1 audit ticket assignments (#484, #485) — 7 rows
100c5574 | 2026-05-01T15:12:45Z | Plan: Rule #3 + Phase 5F section — §1 audit close
fdd70dc5 | 2026-05-01T16:12:03Z | Plan: Phase 6 Entry 44 (5.05) closed at v2.0
74cbfd91 | 2026-05-01T16:09:28Z | Tighten 5.05 — D v1.0 → T v2.0
```

**Phase 5F intake (15 open tickets):**

| # | Title (truncated) | Source |
|---|---|---|
| 484 | §1 Purpose rationale leakage strip (4 policies) | §1 audit |
| 485 | §1 cross-policy references / bold strip per Rule #3 (3 policies) | §1 audit |
| 486 | §2 applicability statement cleanup (10 policies) | §2 audit |
| 487 | §2 OoS parenthetical-title strip per Rule #2 (3 policies / 8 occurrences) | §2 audit |
| 488 | §2 OoS compound-reference split (7 policies, 8→16 items) | §2 audit |
| 489 | §2 InS policy-pointer strip (2 policies) | §2 audit |
| 490 | §2 narrative prose strip + EPP→InS (3.08, 3.09) | §2 audit |
| 491 | §2 structure additions (8 policies) | §2 audit |
| 492 | §3 chained obligation decomposition (18 policies / 23 instances) | §3 audit |
| 493 | §3 Constraint strip + May reframe (6 policies / 10 obligations) | §3 audit |
| 494 | [1.04] §6.5 amendment — locked authority sequence | §3 audit (gates #495) |
| 495 | §3 authority-order corrections per amended 1.04 §6.5 (25 policies) | §3 audit |
| 496 | §3 Standard prose strip in 3.15 | §3 audit |
| 497 | §3 role label normalization (D20.1/.2/.3/.4/.5/.8) | §3 audit |
| 498 | §3 IC architecture sweep — Option B (9 policies + 1.04 §9.1) | §3 audit |

**5.05 was tightened May 1, 2026 (Phase 6 Entry 44).** Re-fetch `05/505.lyx` if your local copy predates 16:09 UTC May 1.

---

## 3. Project Instructions (verbatim, must read first)

The IT Director's project instructions are a separate document the user provides at session start. Re-paste them or have the user re-supply them. They're load-bearing — set tone, define the Auditor's Pen posture, lock the authority hierarchy, establish the Locked Inputs principle. Don't operate without them in context.

Key principles from the instructions to keep top-of-mind:

- **The manual is a re-founding of the institution.** Every "shall" is a fence post. Every locked architectural decision is ground that has already been fought for. Default starting point on any IT-authority question: unitary IT authority.
- **The manual is a succession instrument.** The IT Director has absorbed 15 years of social cost for boundaries the organization needed; the manual converts that personal legacy to written standards. Every defect closed = one less seam a successor needs to hold by force of personality.
- **Auditor's Pen.** Every sentence reviewed by hostile auditor or used in litigation. Eliminate ambiguity, close loopholes, define terms precisely.
- **Locked Inputs.** When Robert answers a question, the answer is locked. Build on it. Don't re-propose alternatives or synthesize mediating framings that quietly rewrite locked decisions.
- **Option-Setting Discipline.** When proposing options under a locked architectural decision: state the architectural frame first, offer only architecturally-compliant options. Don't generate false "tensions" that Robert has to resolve by re-stating principles he's already stated.

---

## 4. Audit method (used in §1, §2, §3 — repeat for §4, §5, §6)

For each section:

1. **Pull the spec.** 1.04 has section templates: §6.3 (Purpose), §6.4 (Scope), §6.5 (Roles), §6.6 (Compliance and Exceptions / §4), §6.7 (Cited References / §5), §6.11 + §6.12 (body / §6 governance).
2. **Build extractor.** Python script reads every `.lyx` in `policies/`, parses the target section by `\begin_layout Subsection*` matching the section header, captures body content and structure.
3. **Build analyzer.** Compare each policy's section against the spec; surface defects.
4. **Write audit report.** Markdown file in `/mnt/user-data/outputs/Section{N}_Audit_Report.md`. Structure: Method, Spec Anchor, Compliance Summary, Findings (with defect IDs), Voice/Structure Variances, Synthesis, Adjudication items, Per-policy summary.
5. **Walk the IT Director through findings.** Ask for rulings on adjudication-required items. Don't assume default disposition — surface the question, give your recommendation, await confirmation.
6. **File tickets at audit close.** Split-by-defect-class is the established precedent. Each defect class gets its own ticket; coupling notes call out where multiple tickets land on the same policy in single Phase 5F touch.
7. **Update plan + README** with audit close.
8. **Commit.** Two sequential per-file PUT commits — plan first, then README.

**Audit is observation-only.** No content changes during audit. All execution deferred to Phase 5F.

---

## 5. Locked architectural decisions you must respect

These came out of Sections 1–3 audits and are non-negotiable inputs to Sections 4–6.

### Locked authority sequence (from §3 audit, Ticket K1 #494)

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

**Flat rule:** named institutional titles always precede Department Heads catch-all, regardless of which holds policy-specific authority. No "if this, then that, except when, unless..." Robert explicitly chose flat over context-dependent.

### Role label canonicals (from §3 audit, Ticket M #497)

- "Support Specialist" (singular).
- Combined role labels always split (e.g., "System and Network Administrators" → Systems Administrator + Network Administrator).
- "Human Resources" canonical (no "(HR)" parenthetical in role label).
- "Department Heads" canonical (drop "County," "(Non-IT...)", "Requesting").
- "Office of Fiscal Affairs" canonical (drop bare "Fiscal Affairs").
- Activity-derivative role labels prohibited; activity-scoping moves to obligation text.

### Incident Commander architecture (from §3 audit, Ticket N #498)

Locked Option B — **accountability/execution split**:

- IT Director holds IC function by policy mandate.
- IT Director may delegate IC execution to any IO Personnel for a specific incident, in writing.
- Accountability stays with IT Director regardless of execution delegation.
- Non-transferable authorities (do not pass through IC delegation): CCA review, exception approval, incident severity classification, law enforcement referral, postmortem report approval, external communications under One Voice Rule.
- Standalone "Incident Commander" §3 role bullets dissolve manual-wide.
- §3 obligations attach to "IT Director (as Incident Commander)" with the role-clarifier parenthetical.
- §6 body prose may use "the Incident Commander" — function speaks regardless of who holds it.

This parallels the LASO architecture (#220, #285, #249, 1.11 v2.2, 1.14 v2.3, 4.06 v2.1) and the Authorizing Official architecture (5.05 v2.0). Three role-clarifiers in the family.

### Plan §9.1 Rules (codified during §1 audit)

- **Rule #1** (locked April 20): No section-specific cross-references in body prose (§6.X depth prohibited). Cross-references use "Policy X.XX (Policy Title)" on first use within a policy, "Policy X.XX" thereafter.
- **Rule #2** (locked April 20): Out of Scope routing pointers end at `Policy [X.XX].` — no parenthetical title, no section depth.
- **Rule #3** (locked May 1): §1 Purpose is plain prose. No cross-policy references and no typographical emphasis in §1.

### Constitutional amendments queued

Both land in 1.04 v1.6 at Phase 5F execution start (gated, not yet executed):

- **§6.5 amendment (#494):** new locked authority sequence + flat institutional-title-before-Department-Heads sub-rule. Updates the example sequence.
- **§9.1 amendment (#498):** add `(as Incident Commander)` to the role-clarifier convention alongside `(as LASO)` and `(as Authorizing Official)`.

---

## 6. What Sections 4, 5, 6 will look like

### Section 4 — Compliance and Exceptions (governed by 1.04 §6.6)

This is the section that defines:
- Sanctions for non-compliance.
- Exception request and approval routing (typically points to Policy 5.01 by reference).
- Compliance enforcement framework.

**What to expect from the §4 audit:** Standing decline pattern #20 (inline §6.6 exception language prohibition) and pattern #41 (open-ended exception inline drift) are highly relevant — many policies likely have inline exception drafts that should be by-reference to 5.01. Pattern #29 (locked-architecture re-push) is the pattern Robert uses to hold this line; you'll likely see cross-validators try to re-push inline exception language. Decline.

Sanctions restatement was already swept manual-wide April 25 (#445–#448 closed). Expect §4 audit to find any residual.

### Section 5 — References (governed by 1.04 §6.7)

This is the section that lists framework citations. Two parts:
- **Cited References** — items the policy body actually cites (per 1.04 §6.7 body-citation test).
- **Framework Alignment** — items the policy aligns with but does not directly cite.

**What to expect:** the §6.7 body-citation test is the structural rule. Cross-validator hallucinations on framework citations (especially CSF 2.0 subcategories — see §7 below) are recurring. Verify every framework citation against the authoritative source in `Reference/`.

LRDA citation verification sweep (#355) is the manual-wide framework-citation-verification ticket; §5 audit may surface candidates to fold into #355's scope.

### Section 6 — Body Governance (governed by 1.04 §6.11 + §6.12)

This is the substantive policy body. The largest section, with the most variance.

**What to expect:** Cross-reference syntax (Rule #1), governed clarifier tags (Constraint, Clarification, Note, Exception per §6.12), named-construct introduction with bold (Glossary terms first-use), passive-voice obligations, role anchor verification on every directive.

This will be the heaviest of the three remaining audits.

---

## 7. Files of out-of-scope across all section audits

Same 5 files for every section — no §1, §2, §3, §4, §5 by design:

- `00/000.lyx` — Front Matter
- `06/601.lyx` — Glossary
- `06/602.lyx` — Policy Matrix
- `06/603.lyx` — Workforce Roles STAK Matrix
- `06/604.lyx` — Revision History and Version Control

In-scope: 60 numbered policies, Chapters 1–5.

---

## 8. Useful tooling patterns from §1–§3 audits

### Repository access
PAT in project instructions; raw content endpoint pattern:
```
curl -H "Accept: application/vnd.github.raw+json" \
  -H "Authorization: Bearer $TOKEN" \
  "https://api.github.com/repos/robertbpratt-tech/Policy/contents/<path>"
```

### LyX parsing
```python
# Subsection headers identify §1 ("1. Purpose"), §2 ("2. Scope"), etc.
headers = list(re.finditer(r'\\begin_layout Subsection\*\n(.*?)\\end_layout', c, re.DOTALL))

# Strip insets when extracting visible content
def strip_lyx_to_visible(text):
    text = re.sub(r'\\begin_inset CommandInset[^\n]*\n.*?\\end_inset', replace_inset, text, flags=re.DOTALL)
    text = re.sub(r'\\begin_inset[^\n]*\n.*?\\end_inset', '', text, flags=re.DOTALL)
    text = re.sub(r'\\lang\s+\w+', '', text)
    text = re.sub(r'\\series\s+bold\b', '<<BOLD>>', text)
    text = re.sub(r'\\series\s+default\b', '<</BOLD>>', text)
    text = re.sub(r'\\[A-Za-z_]+(?:\s+\S+)?(?=\s|$)', '', text)
    text = re.sub(r'\s+', ' ', text).strip()
    return text

# Track depth via begin_deeper / end_deeper for nested itemize
```

### Commit pattern
```python
# Sequential per-file PUT (plan first, then README)
def commit_file(local_path, repo_path, message):
    sha = get_sha(repo_path)  # re-fetch immediately before PUT to avoid 409
    content_b64 = base64.b64encode(open(local_path, 'rb').read()).decode('ascii')
    payload = {"message": message, "content": content_b64, "sha": sha}
    # Write payload to /tmp file; pass via -d @file (avoid heredoc truncation on large base64)
```

### Path builder (use for README updates)
```python
def policy_path(p):  # '1.13' → '01/113.lyx'
    chap, num = p.split('.')
    return f"0{chap}/{chap}{num}.lyx"
```

### Ticket filing
```python
# POST /repos/{owner}/{repo}/issues
# Labels available: cross-cutting, substantive, format, 1.04, central, ch1-governance,
# ch2-security, ch3-service-management, ch4-incident-response, ch5-compliance,
# needs-work, global, operational
```

---

## 9. Standing decline patterns to watch for (from cross-validator history)

- **#1** — merge §5 flat list (1.04 §6.7).
- **#2** — reorder NIST SP before CSF (1.04 §6.11).
- **#3** — LyX CommandInset false positive.
- **#6** — Redmine product-name strip (manual-wide).
- **#20** — inline §6.6 exception language prohibition.
- **#29** — locked-architecture re-push (third-recurrence rule).
- **#32** — "All County Personnel" universal label substitution.
- **#36, #37, #39** — exception-handling pattern pushbacks.
- **#40** — "responsible for" non-transfer pattern (5D.2 origin).
- **#41** — open-ended exception inline drift.

Plan §4 has 30 active patterns total. Always check before accepting validator findings.

**Cross-validator caveat:** ChatGPT, Gemini, Grok do not have access to tightened source files or plan §4. Their feedback often reflects stale or pre-tightening versions. Adjudicate every finding against current source + plan §4 before acceptance.

---

## 10. Session start checklist for the incoming session

1. **Receive project instructions from user.** Re-paste required.
2. **Re-fetch authoritative files:**
   - `01/104.lyx` (constitutional standard — fetch fresh; should be v1.5 still locked, with #494 + #498 amendments queued).
   - `TIGHTENING_PLAN.md` (always fresh at session start).
   - `README.md` (current state of every policy).
3. **Confirm session scope with Robert.** This handoff says "Sections 4, 5, 6," but Robert may pivot — ask which audit to run first or whether anything else is active.
4. **If running an audit:** build extractor → analyzer → report → adjudicate with Robert → file tickets → commit. Same flow as §1, §2, §3.
5. **Tooling reuse:** the §3 extractor (`/home/claude/session/extract_section3.py` from prior session) is a working template — adapt the section header regex and the structural element parsers (e.g., for §4: detect Sanctions block, Exception Routing block, Compliance Mechanisms block; for §5: detect Cited References list, Framework Alignment list).

---

## 11. Open items that crossed sessions and may surface again

- **§5 Per-Policy Defect Inventory** in plan was last refreshed at April 30 watermark. As of May 1 close it's 5+ entries stale. Per established convention, refreshes at post-E46 recalc — do not refresh during section audits.
- **Phase 9I (Architectural Function Ownership)** is queued for Wave 2 audit structure; check for duplicated sanctions and governance-function claims across policies. §4 audit is likely upstream surfacing for this.
- **#264** (role obligation redistribution L1/L2/L3) — manual-wide root for operational tier work; may overlap with §3-audit role label findings if not already absorbed.
- **#356** (2.01 group label) — covered D18 in §3 audit. Still open. May absorb into Phase 5F or close independently.
- **#480** (retention block uniformity) — Phase 9 candidate.
- **#481** (open-ended-exception inline drift sweep) — Phase 9 candidate; relevant to §4 audit findings.
- **#482** (retention opening prose active-voice anchor) — Phase 9 candidate; may surface in §6 audit.

---

## 12. Important behavioral note

When Robert authorizes commit and ripple housekeeping in one message, **execute immediately**. Do not insert a second pre-commit pause. Authorization language ("Make it happen, Captain!", "apply edits", "go ahead and file") covers all standard session-close housekeeping without further confirmation.

This was the source of process friction in earlier sessions. The discipline is: read authorization, execute fully, report results.

---

## 13. Audit reports already produced (working documents)

- `Section1_Audit_Report.md`
- `Section2_Audit_Report.md`
- `Section3_Audit_Report.md`

These exist in the prior session's outputs. If the incoming session needs reference, regenerate from the analyzers — the source of truth is the LyX files plus the filed tickets, not the markdown reports.

---

*End of handoff.*

*Outgoing session: Sections 1, 2, 3 audits complete. Phase 5F intake at 15 tickets. Phase 6 at 44/49 closed. The IT Director has eyes on the work.*
