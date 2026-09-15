# CSG / EDM Automation BRD

## What this folder is
Business Requirements Document for automation opportunities in the Client Service Group (CSG), Entity Data Management (EDM) team, Nomura Wholesale Operations.
Precedent: the SSG BRD (OTC Allege Pilot) in reference/. Reuse its process-agnostic sections and its two utilities (Unstructured to Structured, Compare and Match).
Markdown is the source of truth; .docx is generated from it, never hand-edited.

## Folder layout
- reference/   Read-only inputs:
  - SSG BRD (md)
  - edm-activities-status.xlsx: activity list with SABRE SPOC, business SPOC, and business review status on as-is flows. Authoritative for scope and status.
  - edm-activity-flows.pptx (single deck, all activities) exported as one JPG per slide in reference/flows-jpg/. Session 0 converts these to flows-area-1.md to flows-area-4.md (one file per Level 2 area). The area files are authoritative for as-is steps, input format, HITL and volumes where stated.
- brd/         The document, one file per part (see Document structure).
- decisions/   brd-decisions.md = append-only journal of decisions. Read at the start of every session. Append at the end of every session.
- log/         One dated entry per session.

## Document structure (agreed)
- brd/00-front-section.md          Background, objectives, scope summary, stakeholders, governance and NTI, AI principles, prerequisites, Phase 2 candidates summary. Written AFTER chapters 1 and 2.
- brd/01-capability-catalogue.md   Reusable utilities, each defined once. Hypothesis in Session 1, corrected by every chapter, rewritten clean in Phase 3.
- brd/ch-01-confirmation-contacts-gtype.md      Level 2 area 1 (activities 1.1 to 1.10)
- brd/ch-02-org-creation-maintenance.md         Level 2 area 2 (activities 2.1 to 2.15)
- brd/ch-03-account-creation-maintenance.md     Level 2 area 3 (activities 3.1 to 3.17)
- brd/ch-04-commission-fees.md                  Level 2 area 4 (activities 4.1 to 4.9): no template sections; one note that all nine are Phase 2 (third-party integration) plus the activity list
- brd/annex-scope-register.md      Every underlying activity as one row (one row per region where flows differ; 3.4 as two rows: Totoro and other FO systems): status, scope decision, reason code, input pattern(s), as-is checker drawn, frequency, unblocking question. Rows ordered area 1, 2, 3, 4. Activity names are the status-sheet names verbatim; slide title as an alias column where it differs.
- brd/CSG_EDM_BRD.md               Assembled document (generated in Phase 3, never edited directly)

One chapter per Level 2 area, NOT per underlying activity. Activities are sections inside a chapter.

## Chapter template (per Level 2 area)
1. Area overview: activities, volumes, input patterns, status table. Where frequency or volume is not stated in the flow material, include a "Business to populate" table (activity, frequency, volume, comment) with blank cells, tagged [BUSINESS INPUT]. Never fill it from guesswork. Input format and HITL are not asked of business: input pattern is read from the flows, HITL points are designed in the to-be.
2. As-is process, one sub-section per FLOW GROUP (activities that share one drawn flow are one sub-section, e.g. {1.1, 1.2}, {1.4 to 1.7}), with a mapping table at the head of the section: activity number to flow group to slide numbers. Regional variants (2.7, 3.8) are sub-sub-sections. Where a later activity duplicates an earlier chapter's flow (3.2 = 2.2, 3.16 = 2.15, 3.6 reuses 2.4, 3.11 twin of 2.12, 3.7 = 2.6), write it once in the earlier chapter and cross-reference from the later one.
3. Pain points and root causes
4. Scope decision per activity: Phase 1 / Phase 2 / out of scope / pending / covered elsewhere, with reason
5. To-be process, one sub-section per flow group that has an as-is (same grouping, regions and cross-references as section 2). Each step tagged with the utility it uses (U1 to U6) and where the human decides. Every to-be is written in the same configuration shape (see Wizard-readiness). Where the as-is is pending business sign-off, the sub-section opens with "To-be drafted on an as-is pending business sign-off".
6. Functional requirements, numbered FR-<chapter>-<nn>, testable
7. Controls and governance: maker-checker, logging, mapping to NTI, ORMF and AI Governance Standard articles
8. Data and system touchpoints (EVE, ServiceNow, webform, mailbox, others named in reference/)
9. Risks, assumptions, dependencies, prerequisites
10. Open points, kept visible

## Wizard-readiness (drafting lens, not a chapter)
The target platform lets business users configure their own process through a no-code wizard, one configuration per activity. So every to-be must be expressible as a configuration record with the same fields for every activity:
- input: pattern (IP1/IP2/IP3), mailbox or source, routing signal
- extraction: fields to capture, from where (form, attachment, body)
- checks: validation rules (U3), compare-and-match pairs (U4), duplicate targets
- decision points: where the maker confirms, where the checker confirms
- outputs: system write, query to requestor, closure, log entry
Write section 5 for each activity in this shape. If an activity cannot be expressed this way, say why in section 10; that is a finding, not a failure.

## Scope rules (locked)
- A to-be is written wherever a documented as-is flow exists and the activity is not Phase 2 or out of scope. Pending business sign-off does not block the to-be; it is marked as drafted on a pending as-is (applies to 2.7 both regions, 2.10, 2.13, 3.2, 3.6, 3.8 all regions, 3.15, 3.17). Never invent a to-be where no as-is is drawn.
- Third-party system activities (GMI/Consensys, FIA Tech, LIMA, Nomura Now, Postedge, FO systems except Totoro) are out of scope for Phase 1 and listed as Phase 2 candidates. Do not design for them. Record the business reason: API access not beneficial from an ROI perspective.
- Activities covered by other activities get no separate to-be: 1.9 (by 1.1 to 1.7), 2.3 and 2.14 (by the other 2.x activities), 3.7 (by 2.6). Note them in the scope register as folded into the activities that cover them. Slide 17 (EVE RDM Bulk Loader) is recorded as an as-is note in chapter 2 section 2, owner Rupesh, not as a 2.3 flow.
- 3.4 is two register rows: Totoro (Phase 1) and other FO systems as named on the status sheet (Phase 2). Where flows differ by region (2.7, 3.8), one register row per region.
- Override / exception activities (2.11, 3.9) are out of scope: performed only when there are exceptions, business confirmed.
- Activities whose volume already flows through EVE workflow (2.5, 2.8) are out of scope, business confirmed.
- "Sign off pending", "SOP pending", "awaiting clarifications", "steps unclear": one row in the scope register saying what would unblock it. No to-be until unblocked.
- Environment or IT actions (1.8, pre-refresh backup) are out of scope for automation; register and recommend to the owning tech team.
- Source precedence: edm-activities-status.xlsx for scope and status until Session 1; after Session 1, brd/annex-scope-register.md supersedes it and the Excel is the 14 Sep snapshot. Flow material for as-is steps, input format, HITL, volumes. Flag every conflict as [CONFLICT] rather than picking one silently.
- Any status change is logged in decisions/brd-decisions.md first, then applied to the scope register, then to chapters, in that order.

## Input reality (locked)
- Requesters cannot be asked to change behaviour. Input stays as it is today. "Re-engineer into a request workflow" is retired; never propose it.
- Three input patterns exist and every activity is tagged with one or more (an activity can have several channels, e.g. 1.1 and 1.2 are IP1 plus IP3):
  - IP1: email with a link to a webform / screen. Structured fields plus an unstructured comments field. Confirmed for 1.1 and 1.2.
  - IP2: email with an Excel attachment carrying the request data.
  - IP3: free-text email.
  - IP4: the request originates as an EVE workflow / EVERequest item, with no email (seen in 3.1, 3.8, 3.10, 3.15). U1 does not apply; U2 reads the request data from EVE. Added 15 Sep.
  - Unknown: tag as [OPEN] until the flow or business confirms.
- Automation starts at request receipt, which is an email (IP1 to IP3) or an EVE work item (IP4): identify the activity, extract or fetch the request data, run checks, present to the analyst, checker.
- Prerequisite, to be confirmed before build: whether IP1 form data is reachable via API or query (EVE / ServiceNow) or only by opening the screen. Carry this in the front section prerequisites and in every IP1 activity.

## Capability catalogue (hypothesis, to be validated in Session 1)
- U1 Email-to-activity routing: identify which underlying activity a mailbox email belongs to, from subject line plus body context (the flows never rely on subject line alone). Email channels only; not used for IP4. Same shape as the SSG classifier.
- U2 Input extraction: IP1 form fetch; IP2 Excel parsing; IP4 read from the EVE work item; Unstructured to Structured for IP3 email bodies, IP1 comments and multi-format attachments (PDF, Excel, Word). Reuses the SSG utility.
- U3 Validation, rules-based, no AI: mandatory-entity list, public-domain email rejection, fax tone format, route code and email combination, mandatory fields.
- U4 Compare and Match: domain vs client name, BIC vs name, LEI vs name, duplicate check against EVE. Reuses the SSG utility.
- U5 Query-requestor loop: draft the query when a check fails, track the pending response, close on cancel.
- U6 Maker-checker presentation: show results and evidence to the maker; checker flow mirrors the maker flow; confirmation required wherever a human decides.
- Slide utility tags (Validation / Compare and Match / Unstructured to Structured) are as-is annotations only and are inconsistent across areas; derive to-be utilities from the steps drawn, not from the tags.
- Cross-area duplicates (3.2/2.2, 3.16/2.15, 3.6/2.4, 3.11/2.12) are one parameterised configuration (organisation / account), recorded once in the catalogue.
Excluded by decision: structured intake workflow (retired), environment backup (IT).

## Model rules (quality first, USD 50 daily cap)
- Opus for every step that produces or shapes BRD content: slide-to-text conversion (Session 0), Session 1 Parts B to E, all chapter Steps 1 to 3, catalogue updates, front section outline and writing, catalogue clean-up. Rework costs more than tokens; do not downgrade these to save spend.
- Sonnet only for steps whose errors are cheap to catch by eye: Excel-to-markdown conversion (Session 1 Part A), the consistency check (report only), assembly and .docx export, decisions/log appends.
- Haiku: not used.
- Switch with /model inside a session. Check /cost at every session boundary. The cap is managed by spreading work over more days, not by using a weaker model: if /cost is near 40 USD, finish the current step, run the closing line, and resume tomorrow.
- Read only what the step needs: a chapter session reads CLAUDE.md, decisions, latest log, the catalogue, the scope register and its own flows-area-N.md. Never re-read all of reference/ after Session 1.
- New session per chapter. Context re-sent every turn is the main cost; a long session costs more per turn than a fresh one.

## Session protocol
1. Start: read this file, decisions/brd-decisions.md, and the latest entry in log/. Give a 5-line state summary before doing anything.
2. Agree logic and structure BEFORE creating or editing any file. If asked to discuss, discuss only.
3. One change at a time. Do not combine unrelated edits.
4. Work on one file per session unless told otherwise. Do not touch other chapters.
5. End: append decisions to decisions/brd-decisions.md and a dated entry to log/, with open points listed.
6. After roughly every 10 sections drafted, produce a consolidated list of all edits made so far.
7. Whenever I approve a step (ok, approved, go ahead, next), ask in one line before proceeding: "Anything from this step to log in decisions/brd-decisions.md?" If I answer no or move on without answering, continue.

## Locked wording rules (every file in brd/)
- No em-dashes anywhere. Use commas, semicolons, colons, parentheses, or "i.e." / "e.g.".
- Do not name external vendors or external AI providers. The AI execution stack is always "Chinou API".
- Always "Name and Form" (singular Name), never "Names and Forms".
- Top-level labels are "Phase 1", "Phase 2"; never "v1"; avoid "Phase 1a/1b" unless detail is needed.
- Internal system names, spelled exactly: EVE (reference data, workflow), ServiceNow (existing prod instance), NEWS, PCM (Phoenix Cash Manager), Takara (not Talara). Other systems only as they appear in reference/.
- Cite the AI Governance Standard by article (Article 9: Responsible and Trustworthy AI Principles; Article 2-1: AI Business Owner as 1LOD role). Quote verbatim with article number; never present a paraphrase as a quote.
- SPOC names from the status sheet may appear in the stakeholder table only, never inside process or requirement text.

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
- After writing or editing a file, do not print its content in chat. Tell me the file path and which sections changed, in five lines or fewer. I review in the editor.
