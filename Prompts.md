# Claude Code prompts for the CSG / EDM BRD (revised 16 Sep: code as maker, human as checker)

State: Session 0 done (flows-area-1 to 4 written). Session 1: Part A done, Parts B to E corrected. Remaining: Message A, skeleton, closing.
reference/ now also holds: platform-skills.md, the AI Governance Standard, the NTI process document, the ORMF document, the governance v8 deck.

Day plan (Opus for all content steps; check /cost at every boundary, stop near 40 USD):
- Today: finish Session 1; chapter 1; front section.
- 16 Sep: chapters 2 and 3 in two parallel windows (only the closing routines must not overlap); chapter 4.
- 17 to 18 Sep: Phase 3, draft v0.1 out on 18 Sep.

=====================================================================
## Every session
=====================================================================

Opening line (first message of every session):
```
Read CLAUDE.md, decisions/brd-decisions.md and the latest file in log/. Give me a 5-line summary of where we are and what is open. Do not create or edit anything yet.
```

Closing line (last message of every session):
```
Append today's decisions to decisions/brd-decisions.md (new dated entry, do not touch earlier entries) and write a dated entry in log/ covering what was done, what changed, open points, session name and /cost. Show me both additions.
```

Change intake (any correction: a flow fix, rule content arriving, a status change, a scope call, a governance requirement). Send after the opening line, before the session's own work:
```
Change intake. <what changed>, from <who> on <date>.
1. Append it to decisions/brd-decisions.md as a new dated entry, superseding any earlier entry it contradicts.
2. List every place it lands: rows in brd/annex-scope-register.md, entries in brd/01-capability-catalogue.md, sections in any chapter, the front section, and any [UNCLEAR] or [OPEN] tag it closes. For each, say what would change in one line.
3. Do not edit anything yet; wait for my confirmation of the list.
```

Open points per owner (any session, Sonnet is fine):
```
List every [UNCLEAR], [OPEN], [CONFLICT] and [BUSINESS INPUT] tag across reference/flows-area-*.md and brd/*.md, grouped by owner, with file, section or slide, and the question, as a plain list I can paste into an email.
```

=====================================================================
## Session 1, remainder (current session, Opus)
=====================================================================

Message A:
```
Three things before the skeleton.

1. Catalogue taxonomy. The capability catalogue uses the nine platform skills defined in reference/platform-skills.md, not U1 to U6. Rewrite log/session-1/partC-utility-validation.md so every finding, evidence table and candidate is regrouped under the nine skills, following the mapping table in that file, keeping the U-number in brackets for traceability only. Mark Unstructured to Structured and Compare and Match as registered utilities reused from the SSG BRD. Keep the per-activity evidence intact.

2. Part E reclassification. Under the to-be rule, an activity with a drawn as-is gets a to-be; missing rule content becomes a named configurable check in the chapter with "content: to be supplied by <owner>" plus a section 10 open point. Re-tag every [BLOCKER] in partE-missing-facts.md as [SECTION 10], except where no to-be can exist at all: 3.15 (account selection rule) and 3.12 (no flow). Items 56, 60 and 61: the AI Governance Standard, NTI process, ORMF and the governance deck are now in reference/; mark them "source in reference/, to be read in the front section and chapter sessions".

3. Two design decisions, log them:
- Webform (IP1): as-is is a manual click-through from the email link; the to-be reads the form via API under Ingestion. Prerequisite: API availability confirmed by the EVE / webform owners. Chapter 1 writes the to-be this way with the prerequisite in section 9.
- Duplicate check (1.3, 2.1, 3.1, 2.9): designed as tiered, exact rules first then a fuzzy tier, same shape as the SSG matcher, so AI is in the path with human confirmation. The fuzzy tier is removed if the business rule proves deterministic.

Log all three as a dated entry. Do not print file contents. Then stop.
```

Message B, skeleton:
```
Re-read CLAUDE.md and reference/platform-skills.md; both are current. Then:
- Write the agreed scope register from log/session-1/partD-scope-register-draft.md to brd/annex-scope-register.md (status-sheet activity names, alias column, rows ordered area 1 to 4, 3.4 as two rows, regions as separate rows, "as-is checker drawn" column, frequency, unblocking question).
- Write the capability catalogue from the regrouped log/session-1/partC-utility-validation.md to brd/01-capability-catalogue.md, structured by the nine skills per reference/platform-skills.md, with the heading "Status: draft, to be validated per chapter".
- Create brd/00-front-section.md, brd/ch-01-confirmation-contacts-gtype.md, brd/ch-02-org-creation-maintenance.md and brd/ch-03-account-creation-maintenance.md with only the ten template headings from CLAUDE.md and nothing else.
- Create brd/ch-04-commission-fees.md with a title only.
Do not print file contents; show me the tree.
```
Then /model sonnet, closing line, /exit, /cost. Replace CLAUDE.md on disk after this session.

=====================================================================
## Chapter sessions (one per chapter, NEW session each, Opus throughout)
=====================================================================
Order: ch-01 (restructure of the existing draft), ch-02, ch-03 (parallel windows allowed), ch-04. Replace <file>, <area file>, <groups>.

Opening line, any Change intake messages, then:
```
Re-read CLAUDE.md. Read reference/platform-skills.md and reference/<area file> in full; from brd/annex-scope-register.md read only this area's table; from brd/01-capability-catalogue.md read only the nine skill headings, their one-line definitions and sub-modes. We are working on brd/<file> only.

Write the chapter to the template in CLAUDE.md in two stops.
Stop 1: section 1 (three-sentence overview and one activity table) and section 2, one sub-section per flow group (<groups>), each with As-is (input, frequency, checker today, numbered steps of 6 to 10 lines), To-be (configuration shape with skill and sub-mode tags, the checker's extraction gate and commit approval marked, rejection paths, configurable checks with "content: to be supplied by <owner>"), What changes for the team, Open points for this activity. Where this area duplicates an earlier chapter's flow, cross-reference instead of rewriting. Tell me when ready; I will review in the editor.
Stop 2: sections 3 to 6 at chapter level: FR table traced to to-be steps; controls and governance once, with governance mappings quoted verbatim with article numbers; data, systems and prerequisites; open points roll-up by owner. Tell me when ready.
Language: plain, present tense, no narration of sources in body text; every source conflict, pending sign-off note, slide or journal reference inside a [CAVEAT: ...] tag; every fact once.
```
Groups: ch-01: G1 {1.1, 1.2}, G2 {1.3}, G3 {1.4 to 1.7}. ch-02: 2.1, 2.2 (carries 3.2), 2.4 (carries 3.6), 2.6 (referent for 3.7), 2.7 EMEA and AEJ, 2.9, 2.10, 2.12 (carries 3.11), 2.13, 2.15 (carries 3.16); 2.3 and 2.14 covered elsewhere, slide 17 as a note under the activity that uses the bulk loader. ch-03: 3.1, 3.3, 3.4 Totoro, 3.8 US / EMEA / AEJ, 3.10, 3.17, 3.15 (as-is only, build blocker); 3.2, 3.6, 3.11, 3.16 cross-reference chapter 2; 3.7 covered by 2.6; 3.12 out of scope.
After Stop 2 review:
```
Update brd/01-capability-catalogue.md with anything this chapter extended or added, marked with the chapter number. Append only.
```
Closing line (Sonnet), /exit, /cost.

Chapter 4 (short session):
```
Read brd/annex-scope-register.md. Write brd/ch-04-commission-fees.md: title, one paragraph stating that all nine activities are Phase 2 because they depend on third-party application integration, and a table of 4.1 to 4.9 with status-sheet names and the Phase 2 reason. Nothing else. Stop and tell me it is ready.
```

=====================================================================
## Front section (NEW session after ch-01, Opus)
=====================================================================
Opening line, then:
```
Read brd/ch-01, brd/annex-scope-register.md, brd/01-capability-catalogue.md, the SSG BRD in reference/, and the governance v8 deck in reference/.
Part 1. From the governance deck and the AI Governance Standard in reference/, list what a BRD under this framework must contain (registration, risk tiering, evaluation and monitoring, human oversight, data handling, model inventory, anything else it names), and propose where each item lands in this document: front section, chapter section 7, or Phase 3 check.
Part 2. Using the SSG BRD's process-agnostic sections as the base, propose an outline for brd/00-front-section.md: background, objectives, scope summary with the Phase 1 / Phase 2 / out-of-scope counts, stakeholders (from the SSG stakeholder table plus the EDM SPOCs), input patterns IP1 to IP4, the nine skills as the solution shape with one paragraph on one activity to one wizard configuration, the control model (code as maker, human as checker) in one paragraph, governance and NTI per Part 1 including the NTI plan table (skill, existing NTI or new NTI), prerequisites (ORM and AI Governance acceptance of the control model, per-system write mechanism and pending state, webform API, IP4 intake mechanism, mailbox inventory), Phase 2 candidates summary, and the governance checklist from Part 1 as a table.
Do not write the file until I confirm the outline.
```
Confirm. Then:
```
Write brd/00-front-section.md per the agreed outline. Reuse SSG wording where process-agnostic; reword where it refers to OTC alleges. Stop and tell me it is ready.
```
Closing line (Sonnet), /exit, /cost.

=====================================================================
## Phase 3 (NEW session, Opus for Step 1, Sonnet after)
=====================================================================
Opening line, then (Opus):
```
Read brd/01-capability-catalogue.md and brd/ch-01 to ch-03. Step 1. Rewrite the catalogue clean by the nine skills: one definition per skill, sub-modes, inputs, outputs, the checker decision point and what it is shown, controls, and the list of activities (by number) that use it, drawn from the chapters. Remove the "draft" heading. Save it and tell me which skills changed.
```
Approve. /model sonnet. Then:
```
Step 2. Consistency check across brd/*.md, report only, change nothing: em-dashes; external vendor names; "Names and Forms"; "v1" or "Phase 1a/1b"; U-numbers in chapter text; any mention of re-engineering intake or asking requesters to use a form; SPOC names outside the stakeholder table; system name spellings; FR numbering gaps; skill tags not in the nine; cross-references to sections that do not exist; any to-be with more than one human decision point or any wording of writes "on the analyst's credentials"; remaining [OPEN], [CONFLICT], [BUSINESS INPUT] and [UNCLEAR] tags; status-report phrasing ("sign off provided", "flow created", "as recorded") outside [CAVEAT] tags; any source narration outside [CAVEAT] tags; any table repeated from the register; and every item on the governance checklist in the front section with the section that satisfies it or "not covered". Table with file, line, issue.
```
Fix what you approve. Then:
```
Step 3. Assemble in this order: 00-front-section, 01-capability-catalogue, ch-01 to ch-04, annex-scope-register, into brd/CSG_EDM_BRD_internal.md (all [CAVEAT] tags kept) and brd/CSG_EDM_BRD.md (every [CAVEAT: ...] tag and its contents removed, sentences repaired), each with a table of contents and the label "Draft v0.1 for business review; open points in section 6 of each chapter". Generate CSG_EDM_BRD.docx from the business version (pandoc if installed; otherwise python-docx). Do not edit the .docx. Show me the heading tree and the count of caveats removed.
```
Closing line, /exit.
