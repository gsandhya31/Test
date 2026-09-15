# Platform skills: the capability taxonomy for the CSG / EDM BRD

Source: the nine reusable skills of the target platform, as used in the SSG BRD (OTC Allege Pilot) and the skills-marketplace vision. Two of the nine are already registered utilities with NTIs: Unstructured to Structured (TDG1001567) and Compare and Match (TDG1001568).
Every to-be step in the BRD is tagged with exactly one of these nine. The U-numbers were the Session 1 working hypothesis and are kept here only so earlier analysis can be traced.

## The nine skills

| Skill | What it does | Evidence in the CSG flows |
|---|---|---|
| Ingestion | Picks up the request from its source: shared mailbox, EVE workflow or EVERequest queue, webform link. Structural filtering. Identification of which underlying activity the item belongs to (subject line plus body context; never subject alone). Not needed for identification on IP4 items, which already carry their activity | All 27 as-is units; routing signals stated for 7; the only mailbox named is RDM-ORGS2@uk.nomura.com (slide 1) |
| Unstructured to Structured | Extracts fields from email bodies, webform comment fields, Excel, PDF and Word attachments, including password-protected files. Registered utility, reused | 14 units by email body; 7 by Excel attachment; 3.15 multi-format attachments; 2.10 CRUD determination is the hardest case |
| Transform and Enrich | Derives fields the request does not carry: alt codes, sector code from the TACE table, LEI to legal name, the organisation / account parameter for paired configurations | 1.4 to 1.7 complex G-type components; 2.15 / 3.16 LEI; 3.3 alt code |
| Validate and Approve | Rules-based checks with no AI in the path (mandatory fields, permitted values, entity lists, duplicate check), and every human confirmation and approval point: maker confirmation, checker, Legal / FO / POC approvals. Maker-checker is a control pattern inside this skill, not a separate utility | Rule content exists for area 1 only; checker drawn on 18 of 27 units; the single presentation requirement is on the 2.1 slide (approver receives a data comparison table contrasting requested against actual) |
| Calculate and Process | Executes the agreed action in EVE and downstream systems on the analyst's credentials: create, update, close, delete alt code, upload. Idempotent, with rollback and audit. Always after human approval | The most frequently drawn step type in the deck |
| Monitor and Control | Pending states, chasing, ageing, SLA, audit trail, wait states ("Account on hold"). The tracking half of "query and follow-up" | Complete loop drawn on 3 units; 10 units query then dead-end |
| Compare and Match | (a) Match against a reference source: GLEIF portal, PB sheet, F1SA, Totoro, duplicate check against EVE. (b) Cross-system position and linkage check across FO systems (GMI, Totoro, Euclid, Nuvo, Venom, Viper, Loanet) before a closure or deletion; needs Phase 1 read access to systems whose write automation is Phase 2. Registered utility, reused | (a) 2.15, 3.16, 3.17, 3.15, 3.4; (b) 2.7 both regions, 3.8 all regions |
| Report and Notify | Outbound query to the requestor or client, confirmation mails, Outlook tags, notifications. The sending half of "query and follow-up" | Query wording exists for area 1 only (slides 12, 13); 3.17 queries the client, not an internal requestor |
| Route and Distribute | Assignment to analyst (SSG used alphabet mapping), hand-off to checker, escalation to Legal / FO / KYC, region routing | 2.13 Legal ticket; 3.8 FO approval per TA; 3.10 POC approvals; 2.7 and 3.8 regions |

"Query and follow-up" is a composite of Report and Notify plus Monitor and Control. Whether it is named as its own skill is an open point.

## Mapping from the Session 1 hypothesis (U1 to U6 and candidates)

| Session 1 label | Now lands in |
|---|---|
| U1 Email-to-activity routing | Ingestion (identification) |
| U2a IP1 form fetch | Ingestion |
| U2b Excel parsing | Unstructured to Structured |
| U2c Unstructured to Structured | Unstructured to Structured |
| U2d IP4 read from EVE | Ingestion |
| U3 Validation | Validate and Approve (rules) |
| U4a reference-source match | Compare and Match, sub-mode (a) |
| U4b cross-system position and linkage check | Compare and Match, sub-mode (b) |
| U5 query-requestor loop | Report and Notify (send) + Monitor and Control (track) |
| U6 maker-checker presentation | Validate and Approve (HITL control pattern) |
| Candidate 1: system write execution | Calculate and Process |
| Candidate 2: approval orchestration and pending state | Validate and Approve (approval) + Monitor and Control (tracking) |
| Candidate 3: cross-system position check | Compare and Match, sub-mode (b) |
| Candidate 4: uncontrolled external reference lookup | Compare and Match, sub-mode (a), with an external-dependency note |
| Candidate 5: document extraction and outbound signing | Inbound half: Unstructured to Structured. Outbound signing: a control question, not a skill |
| Candidate 6: bulk and batch load | Not admitted; slide 17 kept as an as-is note under chapter 2 |
| Derived fields (alt code, sector code, LEI name, org/account parameter) | Transform and Enrich |
| Analyst assignment, checker hand-off, escalation | Route and Distribute |

## Rules for use in the BRD
- Chapter text uses the nine skill names only; U-numbers do not appear.
- Slide tags (Validation / Compare and Match / Unstructured to Structured) are as-is annotations and inconsistent across areas; skills are derived from the steps drawn.
- Cross-area duplicates (3.2/2.2, 3.16/2.15, 3.6/2.4, 3.11/2.12) are one parameterised configuration each (organisation / account), recorded once in the catalogue.
- Each Phase 1 to-be is written in the wizard configuration shape so that one activity maps to one configuration record on the platform.
