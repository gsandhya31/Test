# CSG / EDM Automation BRD

## What this folder is
Business Requirements Document for automation opportunities in the Client Service Group (CSG), Entity Data Management (EDM) team, Nomura Wholesale Operations.
Precedent: the SSG BRD (OTC Allege Pilot) in reference/. Reuse its process-agnostic sections and its two utilities (Unstructured to Structured, Compare and Match).
Markdown is the source of truth; .docx is generated from it, never hand-edited.

## Folder layout
- reference/   Read-only inputs: SSG BRD (md), EDM activities Excel and its md conversion, EDM activity flow material, business comments on flows.
- brd/         The document, one file per part (see Document structure).
- decisions/   brd-decisions.md = append-only journal of decisions. Read at the start of every session. Append at the end of every session.
- log/         One dated entry per session.

## Document structure (agreed)
- brd/00-front-section.md          Background, objectives, scope summary, stakeholders, governance and NTI, AI principles, prerequisites. Written AFTER chapters 1 and 2.
- brd/01-capability-catalogue.md   Reusable utilities, each defined once. Drafted as a hypothesis in Phase 1, corrected by every chapter, rewritten clean in Phase 3.
- brd/ch-01-confirmation-contacts-gtype.md      Level 2 area 1 (activities 1.1 to 1.10)
- brd/ch-02-org-creation-maintenance.md         Level 2 area 2 (activities 2.1 to 2.15)
- brd/ch-03-account-creation-maintenance.md     Level 2 area 3 (activities 3.1 to 3.17)
- brd/ch-04-commission-fees.md                  Level 2 area 4 (activities 4.1 to 4.9): short, out of scope with reasons
- brd/annex-scope-register.md      Every underlying activity as one row: status, scope decision, reason, intake pattern, HITL, frequency, open question
- brd/CSG_EDM_BRD.md               Assembled document (generated in Phase 3, never edited directly)

One chapter per Level 2 area, NOT per underlying activity. Activities are sections inside a chapter.

## Chapter template (per Level 2 area)
1. Area overview: activities, volumes, intake patterns, status table
2. As-is process, one sub-section per in-scope activity that has a documented flow
3. Pain points and root causes
4. Scope decision per activity: in / out / pending, with reason
5. To-be process, one sub-section per activity that has an as-is; each step tagged with the utility it uses (U1 to U6) and where the human decides
6. Functional requirements, numbered FR-<chapter>-<nn>, testable
7. Controls and governance: maker-checker, logging, mapping to NTI, ORMF and AI Governance Standard articles
8. Data and system touchpoints (EVE, ServiceNow, webform, mailbox, others named in reference/)
9. Risks, assumptions, dependencies, prerequisites
10. Open points, kept visible

## Scope rules (locked)
- A to-be is written ONLY where a documented as-is flow exists and the activity is in scope. Never invent a to-be.
- Activities marked out of scope because of third-party systems (GMI/Consensys, FIA Tech, LIMA external fetch) are out of scope. Final. State the reason, do not reopen.
- "Biz to confirm", "SOP pending", "steps unclear": one row in the scope register saying what would unblock it. No to-be.
- Environment or IT actions (e.g. pre-refresh backup, activity 1.8) are out of scope for automation; register them and recommend to the owning tech team.
- The activities Excel is partially updated. Later business comments in the flow material take precedence over the Excel. Flag every conflict as an open point rather than picking one silently.

## Intake reality (locked)
- Requesters cannot be asked to change behaviour. Intake stays as it is today. "Re-engineer into a request workflow" is retired; never propose it.
- Three intake patterns exist and every activity must be tagged with one:
  - P1: email with a link to a form / screen. Structured fields plus an unstructured comments column. Some activities in Confirmation, Contacts and G-Type only.
  - P2: email with an Excel attachment carrying the request data.
  - P3: free-text email.
- Automation starts at email receipt: identify the activity, extract or fetch the request data, run checks, present to the analyst, checker.
- Prerequisite, to be confirmed before build: whether P1 form data is reachable via API or query (EVE / ServiceNow) or only by opening the screen. Carry this in the front section prerequisites and in every P1 activity.

## Capability catalogue (hypothesis, to be validated in Phase 1)
- U1 Email-to-activity routing: identify which underlying activity a mailbox email belongs to. Same shape as the SSG classifier.
- U2 Intake extraction: P1 form fetch; P2 Excel parsing; Unstructured to Structured for P3 email bodies and P1 comments. Reuses the SSG utility.
- U3 Validation, rules-based, no AI: mandatory-entity list, public-domain email rejection, fax tone format, route code and email combination, mandatory fields.
- U4 Compare and Match: domain vs client name, BIC vs name, LEI vs name, duplicate check against EVE. Reuses the SSG utility.
- U5 Query-requestor loop: draft the query when a check fails, track the pending response, close on cancel.
- U6 Maker-checker presentation: show results and evidence to the maker; checker flow mirrors the maker flow; confirmation required wherever a human decides.
Excluded by decision: structured intake workflow (retired), environment backup (IT).

## Session protocol
1. Start: read this file, decisions/brd-decisions.md, and the latest entry in log/. Give a 5-line state summary before doing anything.
2. Agree logic and structure BEFORE creating or editing any file. If asked to discuss, discuss only.
3. One change at a time. Do not combine unrelated edits.
4. Work on one file per session unless told otherwise. Do not touch other chapters.
5. End: append decisions to decisions/brd-decisions.md and a dated entry to log/, with open points listed.
6. After roughly every 10 sections drafted, produce a consolidated list of all edits made so far.

## Locked wording rules (every file in brd/)
- No em-dashes anywhere. Use commas, semicolons, colons, parentheses, or "i.e." / "e.g.".
- Do not name external vendors or external AI providers. The AI execution stack is always "Chinou API".
- Always "Name and Form" (singular Name), never "Names and Forms".
- Top-level labels are "Phase 1", "Phase 2"; never "v1"; avoid "Phase 1a/1b" unless detail is needed.
- Internal system names, spelled exactly: EVE (reference data, workflow), ServiceNow (existing prod instance), NEWS, PCM (Phoenix Cash Manager), Takara (not Talara). Other systems only as they appear in reference/.
- Cite the AI Governance Standard by article (Article 9: Responsible and Trustworthy AI Principles; Article 2-1: AI Business Owner as 1LOD role). Quote verbatim with article number; never present a paraphrase as a quote.

## Design principles (every chapter)
- AI only suggests; humans always decide. No auto-finalise without sign-off.
- All writes execute on the analyst's own credentials.
- Every action logged with a case / request ID.
- Prefer dropping an unverifiable claim over hedging it. Use "aligned to" industry definitions, not "based on". Remove any source that cannot be independently verified.

## How to work with me
- Concise, direct, no preamble, no praise.
- If a fact is not in reference/, write [OPEN: what is missing] inline. Do not invent it.
- When I flag an inaccuracy, correct exactly that, nothing else.
- Separate layout changes from content changes.
