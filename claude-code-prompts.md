# Claude Code prompts for the CSG / EDM BRD

Before Session 0: CLAUDE.md at folder root; decisions/brd-decisions.md; reference/ with SSG BRD (md), edm-activities-status.xlsx, activity flow slides; brd/ and log/ empty.

Suggested day split for the USD 50 cap (adjust from /cost; Opus is used for all content steps, so expect 4 days):
- Day 1: Session 0, Session 1
- Day 2: chapters 1 and 2
- Day 3: chapter 3, chapter 4, front section
- Day 4: Phase 3

## Every session: opening line (run after starting Claude Code in the CSG/EDM folder)
```
Read CLAUDE.md, decisions/brd-decisions.md and the latest file in log/. Give me a 5-line summary of where we are and what is open. Do not create or edit anything yet.
```

## Every session: closing line
```
Append today's decisions to decisions/brd-decisions.md (new dated entry, do not touch earlier entries) and write a dated entry in log/ covering what was done, what changed, and open points. Show me both additions.
```

=====================================================================
START NEW SESSION 0        model: /model opus
=====================================================================

## Session 0: convert flow slides to text (Opus: every chapter is built on this)

Run the opening line, then:
```
Read CLAUDE.md. Then read the activity flow slides in reference/ one Level 2 area at a time and write reference/flows-area-1.md, flows-area-2.md, flows-area-3.md, flows-area-4.md. For each activity: the steps in order, decision points and their branches, systems touched, input format if shown, checker / HITL points if shown, volumes or frequency if shown, and every note or question written on the slide. Transcribe, do not interpret. Where a slide is unclear, write [UNCLEAR: what]. Do not touch brd/. Show me area 1 first and wait before doing the rest.
```
Check area 1 against the slides yourself before letting it continue. Then the closing line.

=====================================================================
END SESSION 0: run the closing line, then /exit. Check /cost.
START NEW SESSION 1        model: /model sonnet for Part A only, then /model opus
=====================================================================

## Session 1 (Phase 1): activity table, structure validation, scope register

Run the opening line, then (Sonnet):
```
Read CLAUDE.md. Part A. Convert reference/edm-activities-status.xlsx into reference/edm-activities.md as a plain markdown table, one row per underlying activity, keeping every column. Tell me if any cell is ambiguous or truncated. This is the only file you may create until I say otherwise.
```
Switch: /model opus. Then:
```
Read reference/edm-activities.md and reference/flows-area-1.md to flows-area-4.md. Do not read the slides again.

Part B. Validate the document structure in CLAUDE.md. For each Level 2 area, list the underlying activities and tag each with: intake pattern (P1 / P2 / P3 / unknown), has documented as-is flow (yes / no), scope decision from the status sheet (Phase 1 / Phase 2 / out of scope / pending / covered elsewhere), input format, HITL and frequency if the flows state them (else "business to populate"), and any flow note that contradicts the status sheet. Then tell me where the chapter structure breaks, if anywhere.

Part C. Validate the capability hypothesis U1 to U6. For every Phase 1 activity with an as-is flow, list which utilities it uses. Report: utilities used by nothing, activities that fit no utility, and anything in the flows that looks like a seventh utility. Do not add utilities yourself; propose and wait.

Part D. Draft the scope register in chat only (not as a file): one row per activity (one row per system where an activity is split), with status, scope decision, reason, intake pattern, HITL yes/no, frequency, and the open question that would unblock any pending row.

Part E. List every fact you needed but could not find in reference/.

Stop after Part E and wait for my comments.
```
After you have reviewed and corrected Parts B to E (still Opus):
```
Write the agreed scope register to brd/annex-scope-register.md. Write the corrected capability hypothesis to brd/01-capability-catalogue.md with the heading "Status: hypothesis, to be validated per chapter". Create the four chapter files and brd/00-front-section.md with only the template headings from CLAUDE.md and nothing else. Show me the tree.
```
Switch: /model sonnet. Run the closing line.

=====================================================================
END SESSION 1: closing line, /exit, check /cost. If near 40 USD today, stop here.
START NEW SESSION per chapter        model: /model opus for Steps 1 to 3 and the catalogue update
=====================================================================

## Sessions 2 to 5 (Phase 2): one chapter per session

Order: ch-01 (area 1), ch-02, ch-03, then ch-04 (short). Replace <N> and <file> each time.

Run the opening line, then switch /model opus. Then:
```
Read brd/01-capability-catalogue.md, brd/annex-scope-register.md, reference/edm-activities.md and reference/flows-area-<N>.md only. We are working on brd/<file>. Do not touch any other chapter.

Step 1. Draft sections 1 to 4: area overview with the status table (and a [BUSINESS INPUT] table for any activity whose input format, HITL or frequency is not in the flows), as-is per Phase 1 activity that has a documented flow, pain points, scope decision per activity with reason. Where a fact is missing write [OPEN: what is missing]. Where the status sheet and the flow material disagree, show both and tag [CONFLICT]. Stop and show me.
```
Review. Then (Opus):
```
Step 2. Draft section 5, to-be, only for Phase 1 activities that have an as-is in section 2. Write each in the wizard configuration shape from CLAUDE.md (intake, extraction, checks, decision points, outputs). Tag every step with U1 to U6 and mark every point where the human decides. Respect the intake pattern of each activity: never propose changing how requests arrive. For each activity, state whether it uses a utility as-is, extends it, or needs something not in the catalogue. Stop and show me.
```
Review. Then (Opus):
```
Step 3. Draft sections 6 to 10. Requirements numbered FR-<N>-01 onwards, each testable. Map controls to NTI, ORMF and AI Governance Standard articles with verbatim quotes and article numbers. Carry the P1 form-access prerequisite into section 9 for every P1 activity. Collect every [OPEN], [CONFLICT] and [BUSINESS INPUT] tag from the chapter into section 10. Stop and show me.
```
Review. Then (Opus):
```
Update brd/01-capability-catalogue.md with anything this chapter extended or added, marked with the chapter number. Append only, do not rewrite the file.
```
Switch: /model sonnet. Run the closing line.

=====================================================================
END CHAPTER SESSION: closing line, /exit, check /cost. Start the next chapter in a NEW session, never continue in the same one.
=====================================================================

## Extra session after ch-01 and ch-02: front section

=====================================================================
START NEW SESSION        model: /model opus for outline and writing
=====================================================================
Run the opening line, then (Opus):
```
Read brd/ch-01, brd/ch-02 and the SSG BRD in reference/. Identify content common to both chapters that belongs in the front section. Using the SSG BRD's process-agnostic sections as the base, propose an outline for brd/00-front-section.md including a prerequisites section (P1 form-access confirmation first), a Phase 2 candidates summary, and a one-paragraph note that each Phase 1 activity is intended to map to one wizard configuration on the target platform. Do not write it until I confirm the outline.
```
Confirm. Then (Opus):
```
Write brd/00-front-section.md per the agreed outline. Reuse SSG wording where it is process-agnostic; reword where it refers to OTC alleges. Stop and show me.
```
Switch: /model sonnet. Run the closing line.
=====================================================================
END SESSION: closing line, /exit, check /cost.
=====================================================================

## Sessions 6 to 7 (Phase 3): catalogue clean-up, check, assemble, export

=====================================================================
START NEW SESSION        model: /model opus for Step 1 only, /model sonnet after
=====================================================================
Run the opening line, then (Opus):
```
Read brd/01-capability-catalogue.md and brd/ch-01 to ch-04. Step 1. Rewrite the catalogue clean: one definition per utility, inputs, outputs, HITL points, controls, and the list of activities (by number) that use it, drawn from the chapters. Remove the "hypothesis" heading. Show me the diff against the current file before saving.
```
Approve. Switch: /model sonnet. Then:
```
Step 2. Consistency check across brd/*.md, report only, change nothing: em-dashes, external vendor names, "Names and Forms", "v1" or "Phase 1a/1b", any mention of re-engineering intake or asking requesters to use a form, SPOC names outside the stakeholder table, system name spellings, FR numbering gaps, utility tags not in the catalogue, cross-references to sections that do not exist, remaining [OPEN], [CONFLICT] and [BUSINESS INPUT] tags. Table with file, line, issue.
```
Fix what you approve. Then (Sonnet):
```
Step 3. Assemble in this order: 00-front-section, 01-capability-catalogue, ch-01 to ch-04, annex-scope-register, into brd/CSG_EDM_BRD.md with a table of contents. Generate CSG_EDM_BRD.docx from it (pandoc if installed; otherwise python-docx). Do not edit the .docx. Show me the heading tree of the assembled document.
```
Run the closing line.
=====================================================================
END: closing line, /exit. Done.
=====================================================================
