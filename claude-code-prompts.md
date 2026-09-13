# Claude Code prompts for the CSG / EDM BRD

Files expected before Session 1: CLAUDE.md at folder root; decisions/brd-decisions.md (from brd-decisions.md); reference/ populated; brd/ and log/ empty.

## Every session: opening line
```
Read CLAUDE.md, decisions/brd-decisions.md and the latest file in log/. Give me a 5-line summary of where we are and what is open. Do not create or edit anything yet.
```

## Every session: closing line
```
Append today's decisions to decisions/brd-decisions.md (new dated entry, do not touch earlier entries) and write a dated entry in log/ covering what was done, what changed, and open points. Show me both additions.
```

---

## Session 1 (Phase 1): reference conversion, structure validation, scope register

```
Read CLAUDE.md first, then everything in reference/. Do not create or edit anything in brd/ until I say so.

Part A. Convert the activities Excel into reference/edm-activities.md as a plain markdown table, one row per underlying activity, keeping every column. Tell me if any cell is ambiguous or truncated. This is the only file you may create in this session.

Part B. Validate the document structure in CLAUDE.md against the material. For each Level 2 area, list the underlying activities and tag each one with: intake pattern (P1 / P2 / P3 / unknown), has documented as-is flow (yes / no), scope status as per the Excel, and any later business comment in the flow material that contradicts the Excel. Then tell me where the chapter structure breaks, if anywhere.

Part C. Validate the capability hypothesis U1 to U6. For every in-scope activity with an as-is flow, list which utilities it uses. Then report: utilities used by nothing, activities that fit no utility, and anything in the flows that looks like a seventh utility. Do not add utilities yourself; propose and wait.

Part D. Draft the scope register in chat only (not as a file): one row per activity with status, scope decision, reason, intake pattern, HITL yes/no, frequency, and the open question that would unblock any pending row.

Part E. List every fact you needed but could not find in reference/.

Stop after Part E and wait for my comments.
```

After you have reviewed and corrected Parts B to E:
```
Write the agreed scope register to brd/annex-scope-register.md. Write the corrected capability hypothesis to brd/01-capability-catalogue.md with the heading "Status: hypothesis, to be validated per chapter". Create the four chapter files and brd/00-front-section.md with only the template headings from CLAUDE.md and nothing else. Record the structure decisions and the intake-pattern tags per activity in decisions/brd-decisions.md. Show me the tree.
```

---

## Sessions 2 to 5 (Phase 2): one chapter per session

Order: ch-01 (area 1, most flows available), ch-02, ch-03, then ch-04 (short). Replace <N> and <file> each time.

```
Read CLAUDE.md, decisions/brd-decisions.md, brd/01-capability-catalogue.md and brd/annex-scope-register.md. We are working on brd/<file> only. Do not touch any other chapter.

Step 1. Draft sections 1 to 4: area overview with the status table, as-is per activity that has a documented flow (from reference/), pain points, scope decision per activity with reason. Where a fact is missing write [OPEN: what is missing] inline. Where the Excel and the flow material disagree, show both and tag [CONFLICT]. Stop and show me.
```
After review:
```
Step 2. Draft section 5, to-be, only for activities that have an as-is in section 2. Tag every step with U1 to U6 and mark every point where the human decides. Respect the intake pattern of each activity: never propose changing how requests arrive. For each activity, state whether it uses a utility as-is, extends it, or needs something not in the catalogue. Stop and show me.
```
After review:
```
Step 3. Draft sections 6 to 10. Requirements numbered FR-<N>-01 onwards, each testable. Map controls to NTI, ORMF and AI Governance Standard articles with verbatim quotes and article numbers. Carry the P1 form-access prerequisite into section 9 for every P1 activity. Collect every [OPEN] and [CONFLICT] tag from the chapter into section 10. Stop and show me.
```
Then the closing line, plus:
```
Update brd/01-capability-catalogue.md with anything this chapter extended or added, marked with the chapter number. Do not rewrite the file, append only.
```

### Extra session after ch-01 and ch-02: front section outline
```
Read brd/ch-01 and brd/ch-02 and the SSG BRD in reference/. Identify content common to both chapters that belongs in the front section. Using the SSG BRD's process-agnostic sections as the base, propose an outline for brd/00-front-section.md including a prerequisites section (P1 form-access confirmation first). Do not write it until I confirm the outline.
```
After confirming:
```
Write brd/00-front-section.md per the agreed outline. Reuse SSG wording where it is process-agnostic; reword where it refers to OTC alleges. Stop and show me.
```

---

## Sessions 6 to 7 (Phase 3): catalogue clean-up, check, assemble, export

```
Read CLAUDE.md and decisions/brd-decisions.md.

Step 1. Rewrite brd/01-capability-catalogue.md clean: one definition per utility, inputs, outputs, HITL points, controls, and the list of activities (by number) that use it, drawn from the chapters. Remove the "hypothesis" heading. Show me the diff against the current file before saving.
```
After approval:
```
Step 2. Consistency check across brd/*.md, report only, change nothing: em-dashes, external vendor names, "Names and Forms", "v1" or "Phase 1a/1b", any mention of re-engineering intake or asking requesters to use a form, system name spellings, FR numbering gaps, utility tags not in the catalogue, cross-references to sections that do not exist, remaining [OPEN] and [CONFLICT] tags. Table with file, line, issue.
```
After fixing what you approve:
```
Step 3. Assemble in this order: 00-front-section, 01-capability-catalogue, ch-01 to ch-04, annex-scope-register, into brd/CSG_EDM_BRD.md with a table of contents. Generate CSG_EDM_BRD.docx from it (pandoc if installed; otherwise python-docx). Do not edit the .docx. Show me the heading tree of the assembled document.
```
