# Session 1, Part C: capability catalogue validation, U1 to U6

Source: reference/edm-activities.md and reference/flows-area-1.md to flows-area-4.md. No slides were re-read.
Revised 15 Sep to apply the Part B to E decisions. Activity names are the status-sheet values verbatim; see the mapping tables in partB-activity-tags.md. This file keys on activity numbers so that no name is abbreviated.

## Two method rules, applied

1. **Slide utility tags are as-is annotations only. To-be utilities are derived from the steps drawn, not from the tags.** So the absence of a Validation tag on a slide is not evidence that no validation happens; where a step implies a rules check, U3 applies. Derived assignments are marked as derived and separated from drawn ones.
2. **U1 applies to email channels only. For IP4 the request data is read from EVE by U2.** There is no email to classify, so U1 has no work to do on an IP4 intake.

## Scope of the test

The **27 as-is units** that are Phase 1 and have a documented flow. A unit is one drawn flow: activities that share a flow count once, and activities split by region count once per region. 2.3 is excluded because it is now covered elsewhere with no to-be.

| Area | Units | Members |
|---|---|---|
| 1 | 3 | **G1** {1.1, 1.2} slides 4 to 7; **G2** {1.3} slide 8; **G3** {1.4 to 1.7} slide 9 |
| 2 | 11 | 2.1, 2.2, 2.4, 2.6, 2.7-EMEA, 2.7-AEJ, 2.9, 2.10, 2.12, 2.13, 2.15 |
| 3 | 13 | 3.1, 3.2, 3.3, 3.4-Totoro, 3.6, 3.8-US, 3.8-EMEA, 3.8-AEJ, 3.10, 3.11, 3.15, 3.16, 3.17 |

Excluded and why: 1.8, 2.5, 2.8, 2.11, 3.9 out of scope; 1.10, 3.5, 3.13, 3.14, 4.1 to 4.9 Phase 2; 1.9, 2.3, 2.14, 3.7 covered elsewhere with no to-be; 3.12 no flow drawn; 3.4 non-Totoro systems Phase 2.

**From 27 as-is units to the build:** four units collapse into their area 2 twins as one parameterised configuration each (3.2 into 2.2, 3.6 into 2.4, 3.11 into 2.12, 3.16 into 2.15), giving **23 configuration records**, which group into **20 to-be design units** once the extra regional variants of 2.7 and 3.8 are counted as variants of one design.

**No utility in the hypothesis is proposed for removal. Nothing is added to the catalogue in this file; the candidates at the end are proposals awaiting a decision.**

---

## U1: email to activity routing

What it must do: receive an inbound item in a monitored mailbox, decide which underlying activity it is, and hand it to that activity's configuration. **Email channels only.**

**Units where U1 does not apply at all: 2 of 27.** 3.10 (start box "Open EVE Request shared") and 3.15 (start box "Eve Workflow-NSI") are IP4-only intakes. The email that arrives on both is a later data source, not the trigger, so what U1 would have done is replaced by an EVE read (U2d) plus a correlation step, i.e. tying the incoming mail to the EVE item that is already open. **That correlation step is not drawn on either slide and is not in the catalogue.**

**Units with an email channel: 25 of 27.** Of those, a routing signal is stated for **7**:

| Unit | Evidence in the flow material |
|---|---|
| 3.3 | Subject line plus request context (Broker / Comms / Expense), slide 35 |
| 3.4-Totoro | Margin note "Subject line: not from mail, check in EVE". A routing signal that says the subject line is **not** usable, i.e. negative evidence |
| 3.6 | "Email might have in subject line, but attached excel with fields is a mandatory". Subject line alone insufficient |
| 3.8-US | Routing note present on the slide |
| 3.8-EMEA | Routing note present on the slide |
| 3.8-AEJ | Routing note present on the slide |
| 3.11 | "Subject: TradingAlert Counterparty Name/Obligor" |

A signal also appears on slide 46 for 3.12, but that slide is empty and the note is identical to slide 45's, so it may be a duplicate of 3.11's and 3.12 is outside the 27 in any case.

**Units with an email channel and no routing signal stated: 18 of 25.** Every area 1 and area 2 unit is in this group.

Findings:

- The **only mailbox address anywhere in reference/** is `RDM-ORGS2@uk.nomura.com` on slide 1. Whether all 51 activities arrive there, or whether area 3 and area 4 have their own mailboxes, is not stated. U1's design depends on this: one mailbox means one classifier over many classes, several mailboxes means several smaller ones.
- Every stated signal is a **subject line plus context**, never a subject line alone, and two units state explicitly that the subject line is insufficient (3.4, 3.6). A rules-only router is not supportable on the evidence; U1 needs body and attachment content as well as the subject.
- The cross-area duplicates make routing harder, not easier. 2.2 and 3.2 have near-identical sheet names, as do 2.4 and 3.6, 2.12 and 3.11, 2.15 and 3.16, and 2.3 and 3.3 are word for word identical. **U1 must distinguish an organisation request from an account request in five near-identical pairs.** Once the pairs are built as one parameterised configuration, this stops being a routing decision between two activities and becomes a parameter U2 must extract, which is the easier problem. Worth stating in the catalogue as the reason for the parameterisation.

**Verdict: U1 is retained, narrowed to email channels, and is the least evidenced utility in the catalogue.** 18 of its 25 in-scope units give it no signal to work from, and the strongest evidence available is two flows saying the obvious signal does not work.

---

## U2: input extraction

What it must do: four sub-modes. (a) IP1, fetch the structured fields behind the webform link. (b) IP2, parse the Excel attachment. (c) Unstructured to Structured, turn an IP3 email body, or the free-text comment field of an IP1 form, into fields. (d) **New by decision: IP4, read the request data from the EVE workflow or EVERequest item.**

**Units using U2: 21 of 27.**

### U2a, IP1 form fetch

| Unit | Evidence |
|---|---|
| G1 {1.1, 1.2} | Start boxes read "Webform / EVE" and "Webform / EVE / Email (Less Freq)". The only IP1 evidence in the entire deck. The sheet status cell confirms it: "an email which has the link to the webform and the webform has the details of the change, comments field of this webform is free text" |

One unit. How the form is read (screen, database, API) is not stated anywhere.

### U2b, IP2 Excel parsing

| Unit | Evidence |
|---|---|
| G2 {1.3} | "Email Received, Excel Attached and passed the mandatory fields check" |
| G3 {1.4 to 1.7} | "Mandatory fields are filled in the G-Type excel form received via email" |
| 2.2 | "addition/ amendment/delete request in excel attachment" |
| 3.2 | Identical wording to 2.2. Collapses into the 2.2 configuration |
| 3.6 | "attached excel with fields is a mandatory" |
| 3.8-EMEA | "List of org id, account id, extract from Excel" |
| 3.15 | Client mail carrying PDF, Excel and Word attachments, plus a PB sheet marked "(Password Protected)" |

Seven units, the best evidenced sub-mode. **3.15 breaks it**: the attachment set is PDF, Excel or Word, not Excel alone, and one input is password protected. Excel parsing alone does not cover it.

### U2c, Unstructured to Structured

| Unit | Evidence |
|---|---|
| G1 {1.1, 1.2} | The IP3 channel "Email (Less Freq)", plus the free-text comment field on the IP1 form |
| 2.9 | "AGTS creation email request received", no attachment named; seven attributes must be produced |
| 2.10 | "Follow actions mentioned in the email (CRUD)". The action itself is buried in prose |
| 2.12 | "Required flags to be updated will be available in the email" |
| 2.15 | "Request Received / Via Mail", no attachment |
| 3.1 | "Account Creation Request Received Via Mail" |
| 3.3 | "Extract 4 fields", the only explicit extraction step drawn in the deck |
| 3.4-Totoro | "TA Creation Request Received Via Mail" |
| 3.8-US | "Extract list of inactive US trading Accounts based on RDM ID, alt code" |
| 3.8-AEJ | Same extraction wording as US, on a slide titled ASIA |
| 3.10 | "Requestor mail carries details (RDM ID, Name of SSI, EVE ID, FX NIC)". This is the supporting mail, not the trigger |
| 3.11 | "Mail received", flag details in the body. Collapses into the 2.12 configuration |
| 3.16 | "Request Received / Via Mail". Collapses into the 2.15 configuration |
| 3.17 | "Request Received Via Mail" |

Fourteen units, the largest single group in the catalogue.

### U2d, IP4 read from EVE

| Unit | Evidence |
|---|---|
| 3.1 | "Open EVE application / via workflow-EVERequest", a second trigger alongside the email start box |
| 3.8-US | "Request sent through mail/EVE workflow/KYC team" |
| 3.8-EMEA | Same |
| 3.8-AEJ | Same |
| 3.10 | Start box "Open EVE Request shared" |
| 3.15 | Start box "Eve Workflow-NSI" |

Six units. Newly in scope by the IP4 decision. Adjacent evidence: 3.4's margin note "Subject line: not from mail, check in EVE" says that even where the trigger **is** an email, the routing data must be read from EVE, so U2d is needed for at least one non-IP4 unit as well.

Findings:

- **2.10 is the hardest case and should be the design reference.** "Follow actions mentioned in the email (CRUD)" means extraction decides the *operation*, not just the field values. Create, read, update and delete branch to different system actions, and getting it wrong writes the wrong change to an organisation or vendor attribute.
- Only one unit draws an explicit extraction step with a field count (3.3, "Extract 4 fields"), and that count contradicts the later blue box on the same slide, which lists three fields with the alt code added separately. The one well specified extraction has a documented internal inconsistency.
- The field list to be produced is drawn for a handful of units only (2.9 seven attributes but with "Country of Domicile" listed twice, so possibly six; 2.13 eight fields; 3.10 four fields; 3.3 three or four). For the other ten U2c units the output schema is not stated.
- **U2d is where the parameterised configurations pay off.** An IP4 request arrives with structured fields already, so U2c is not needed for it at all. The same configuration therefore needs U2c for its email path and U2d for its EVE path, which is exactly the case for 3.1 and 3.8.

**Verdict: U2 is retained, extended with the U2d sub-mode, and is the most heavily used utility. U2c is the centre of gravity of the whole programme.** Two further extensions are needed on the evidence: non-Excel attachments including PDF and Word, and password-protected files (both 3.15).

---

## U3: validation, rules based, no AI

What it must do: apply a stated rule set to extracted fields and produce pass, fail or query, deterministically and with no model in the path.

Derived from the steps, not from the slide tags. Four tiers:

### Tier A: validation drawn and the rule content exists. 1 of 27

| Unit | Evidence |
|---|---|
| G1 {1.1, 1.2} | The mandatory confirmation entity list (NIP, NFPE, NFRNC, NFPFR, NAIMF), the public-domain email rejection list, the fax tone check, and the route code plus email combination rule. All on slides 4 to 7 and reference notes 12 and 13 |

### Tier B: a validation step is drawn, the rule content is missing. 7 of 27

| Unit | Step drawn | What is missing |
|---|---|---|
| G2 {1.3} | "passed the mandatory fields check" | which fields are mandatory |
| G3 {1.4 to 1.7} | "Mandatory fields are filled in the G-Type excel form" | which fields, and the complex G-type components named in the 1.4 activity name (alt code, sector code, trading scope) |
| 2.1 | "Validate required fields" plus the duplicate check that is the activity itself | which fields; the duplicate-match rule |
| 2.6 | "Validate the requester details" | which fields. The slide asks the question and does not answer it |
| 2.9 | "Duplicate Check(from activity1)" | which activity 1 (1.1 or 2.1), and the duplicate-match rule |
| 3.1 | the duplicate check that is the activity itself, plus the green duplicate-entities diamond | the diamond's last line is unreadable |
| 3.6 | "attached excel with fields is a mandatory" | which fields |

### Tier C: derived from the steps, no validation step drawn. 14 of 27

2.2 and 3.2 (an Excel request must be checked for mandatory fields before it is actioned); 2.10 (the RDM ID search has a failure branch, i.e. an existence check, and the CRUD action must be a permitted value); 2.12 and 3.11 (the flag code must be one of the permitted values); 2.13 (the eight-field list must be present before the Legal ticket is raised); 2.15 and 3.16 (the LEI must be well formed before the external lookup); 3.3 and 3.4-Totoro (the extracted fields must be present and well formed); 3.8-US, 3.8-EMEA, 3.8-AEJ (the account status check, drawn as "Status-Restricted" on the US slide); 3.17 (the document fields must be present before matching).

### Tier D: no U3. 5 of 27

2.4 (field set-up only), 2.7-EMEA, 2.7-AEJ, 3.10 (approval routing only), 3.15 (matching only, and its selection rule is unknown).

Findings:

- **Rule content exists for one unit out of 27.** That is the largest specification gap in the programme, and it is larger than the previous version of this file reported, because deriving U3 from the steps rather than from the slide tags increases the number of units that need rules from 8 to 22 without adding any rules.
- Where validation is drawn outside area 1 it is drawn as a label with no content: "Validate required fields" (2.1), "Validate the requester details" (2.6). Neither names a field. These cannot be configured as written.
- 2.9's "Duplicate Check(from activity1)" is the only reuse of a validation rule across activities that the deck makes explicit, and it is ambiguous about which activity 1 it means. Note that 2.1, 3.1 and 1.3 are all duplicate-check activities by name, so **the duplicate-match rule is needed by at least four units and is stated nowhere**.
- The five permitted flag codes (AFFRM, CRED, COMP, RTCP2, COBLK) are the only value list outside area 1, they are drawn on 2.12 only, and 3.11's identically named activity has the flag types recorded on the sheet as an open query.

**Verdict: U3 is retained and correctly specified as rules based with no AI. It is needed by 22 of 27 units and is buildable for 1.**

---

## U4: Compare and Match

What it must do: read a value from one source and a value from another, decide whether they agree, and branch on the answer.

**Units using U4: 10 of 27.** Two distinct behaviours:

### U4a: match against an authoritative reference source. 5 units

| Unit | Evidence |
|---|---|
| 2.15 | An explicit green "Compare and Match" box on slide 31, comparing the request against GLIEF Portal data. The clearest statement of the utility in the deck |
| 3.16 | The same explicit box, slide 51 being drawn box for box like slide 31. Collapses into the 2.15 configuration |
| 3.17 | Compare the client document against F1SA, then branch: "If match, signed and sent to PB", else query the client |
| 3.15 | Compare the EVE workflow request against the password-protected PB sheet |
| 3.4-Totoro | Check the requested TA against Totoro, subject to the "check in EVE" margin note |

### U4b: check for positions or linkages across front-office systems before a destructive action. 5 units

| Unit | Evidence |
|---|---|
| 2.7-EMEA | Check for positions and for LVCC alt codes in FO systems before closure |
| 2.7-AEJ | The same intent, a different system list |
| 3.8-US | "Check Manager Approvals and OBI report" against the extracted account list |
| 3.8-EMEA | "Check for altcode LVCC in FO systems in Totoro & GMI", drawn twice, once unconnected |
| 3.8-AEJ | The same check, a third system list |

Findings:

- The two behaviours have different connectors, different failure modes and different consequences. U4a is one lookup and a field-level diff. U4b is a read across GMI, Totoro, Euclid, Nuvo, Venom, Viper and Loanet to answer one question before an irreversible action: **is anything still attached to this account or organisation.** A false negative in U4b closes an account with live positions.
- **A tension worth naming now:** U4b requires Phase 1 **read** access to systems whose **write** automation is Phase 2 or out of scope (GMI, Venom-Viper, Loanet, and Global1 / Sphinx via 3.4). Reading them in Phase 1 while writing to them only in Phase 2 is coherent, but it is nowhere stated as a decision.
- The 2.15 and 3.16 green boxes are the only place in reference/ where a capability name from the hypothesis is written on a slide by the business.
- The activity names support the split: 3.13, "Linking alt codes for FO systems e.g. GMI in EVE", is a Phase 2 activity that is essentially U4b's write-side counterpart. So the linkage domain is split across a Phase 1 read and a Phase 2 write in the activity list itself, not only in the catalogue.

**Verdict: U4 is retained and is the best evidenced utility after U2. Recommend splitting it formally into U4a and U4b, or admitting U4b as a separate utility. See candidate 3.**

---

## U5: query the requestor and track the loop

What it must do: when input is missing or fails validation, draft a query to the requestor, send it, hold the request in a pending state, resume on reply, and close the request if the requestor cancels or does not reply.

### Complete loop drawn: 3 of 27

| Unit | Evidence |
|---|---|
| G1 {1.1, 1.2} | The standard query format is given verbatim in the slide 12 reference notes, with five relationship-justification samples on slide 13. The only place in reference/ where the outbound query wording exists |
| 2.15 | A full loop on slide 31: query out, wait, resume, and a close-on-cancel terminal |
| 3.16 | The same full loop, slide 51. Collapses into the 2.15 configuration |

### Query drawn but it dead-ends: 10 of 27

The flow reaches "ask the requestor" and then stops, with no resume path and no terminal: 2.6 ("Contact the requester to confirm the fund"), 2.9, 2.10 (failure branch unlabelled), 2.13, 3.1, 3.3, 3.4-Totoro, 3.6 (the arrow out of "Ask requestor for details" has no target box at all), 3.11, 3.17 ("Send Request to client for confirmation", no return path).

### No query path drawn: 14 of 27

G2 {1.3}, G3 {1.4 to 1.7}, 2.1, 2.2, 2.4, 2.7-EMEA, 2.7-AEJ, 2.12, 3.2, 3.8-US, 3.8-EMEA, 3.8-AEJ, 3.10, 3.15.

Findings:

- **U5 is needed in the to-be by every unit that has a U3 tier A, B or C assignment, i.e. 22 of 27**, because a rules check that can fail must have somewhere to send the failure. It is completely specified for 3.
- **The pending-state behaviour is the part that is almost never drawn.** Ten flows know they need to ask a question; three know what happens next. Without a pending state, a queried request is simply lost from the automation.
- 3.6's dangling arrow and 3.10's "Wait for Approval mail" diamond with an "Account on hold" state are the two places that come closest to drawing a wait state, and only 3.10 names the held condition.
- Outbound query wording exists for area 1 only. For areas 2 and 3 the text of the query the utility must generate does not exist in reference/.
- 3.17's query goes to the **client**, not to an internal requestor. That is the only outbound-to-client query in the deck and it carries a different control question from an internal one.

**Verdict: U5 is retained. It has the widest gap in the catalogue between how often it is needed (22 of 27) and how completely it is specified (3 of 27).**

---

## U6: maker checker presentation

What it must do: present to a human reviewer what was requested against what the automation proposes to do, so the reviewer can approve or reject, and record the decision.

**In the to-be, U6 applies to all 20 to-be design units and all 23 configuration records**, because a human decides in every Phase 1 to-be by design principle. The register column "as-is checker drawn" records where the as-is documents one.

**As-is checker drawn: 18 of 27.**

Drawn as "4 EYE CHECK" or "4 eye": 2.1, 2.2, 2.4, 2.9, 2.12, 3.2.
Drawn as a "Checker" box or label: G3 {1.4 to 1.7} (three separate approval points: regional approval loop, requestor UAT approval, Checker Approval), 3.1, 3.3, 3.4-Totoro, 3.6, 3.11.
Drawn as a named approval rather than a generic checker: 2.4 ("Checker Approval ?" diamond with a Modify details loop, the only checker drawn as a decision with a rejection path), 2.6, 2.13 (Legal approval via a ServiceNow Legal ticket), 3.8-US ("Approval from FO for each TA"), 3.10 (POC approvals plus a wait state), 3.17 (a signature, signer not named).

**As-is checker not drawn: 9 of 27.**
G2 {1.3}, 2.7-EMEA, 2.7-AEJ, 2.10, 2.15, 3.8-EMEA, 3.8-AEJ, 3.15, 3.16.

Findings:

- **Every closure unit is in the not-drawn group** (2.7 both regions, 3.8 EMEA and AEJ). These are the flows that delete LVCC alt codes and close accounts and organisations, i.e. the highest-consequence and least reversible actions in the whole scope. The to-be gives them a checker regardless, so the effect is a documentation gap rather than a design gap, but the gap sits on exactly the wrong activities and the region sub-sections in section 5 will have to state the checkpoint without an as-is to derive it from.
- **The presentation requirement is stated once in the entire deck**, in the 2.1 pink box: "Human-in-the-loop approval is required before finalization. The approver must receive a data comparison table that clearly contrasts the requested information against the information actually added to the system." Every other unit draws a checker box with no statement of what the checker is shown. That single sentence is the whole specification for U6 and should be quoted verbatim in the catalogue.
- **Fifteen of the eighteen checker steps have no rejection path drawn.** Several are drawn as terminals with no outgoing arrow at all (3.1, 3.11). Only 2.4 draws reject and loop back. So the deck specifies approval and almost never specifies what a rejection does.
- Three units carry multi-party approval, not a single checker: G3 {1.4 to 1.7} (three points including a regional loop), 2.13 (Legal, external to EDM), 3.10 (POC approvals held in a spreadsheet outside EVE). A single maker-checker presentation does not cover these. See candidate 2.

**Verdict: U6 is retained. It is specified by one sentence on one slide, and the rejection path is its missing half.**

---

## The three lists

### 1. Utilities used by nothing

**None.** All six utilities are evidenced by at least one Phase 1 as-is unit. The hypothesis contains no dead entries.

Usage over the 27 units, for planning:

| Utility | As-is evidence | To-be need | Assessment |
|---|---|---|---|
| U2 input extraction | 21 of 27 | 21 | Core. U2c (14 units) is the single largest build. U2d added by decision |
| U6 maker checker | 18 drawn | all 23 configurations | Universal by design principle, specified by one sentence |
| U3 validation | 8 drawn, 14 derived | 22 of 27 | Rule content exists for 1 unit |
| U5 query loop | 3 complete, 10 dead-end | 22 of 27 | Widest specification gap |
| U4 Compare and Match | 10 of 27 | 10 | Well evidenced, two distinct behaviours merged into one utility |
| U1 routing | 7 signals of 25 applicable | 25 of 27 | Least evidenced. Does not apply to 3.10 and 3.15 |

### 2. Activities that fit no utility

**No flow, so no utility can be assigned:** 1.9, 2.3, 2.14, 3.7 (covered elsewhere, no to-be, so this is expected), 3.12 (open item), 1.10, 3.5, 3.13, 3.14 and 4.1 to 4.9 (Phase 2).

**A flow exists and still fits no utility: 1.8 only.** Slide 10's three linear steps (environment refresh happens, refresh the data, confirm) involve no request, no extraction, no validation, no comparison, no query and no checker. Consistent with its out-of-scope classification and with the sheet's note that the IT team of today can take it up. **1.8 is the one activity in the deck the catalogue genuinely does not reach, and it is already out of scope. The catalogue's coverage of in-scope work is therefore complete at the utility level.**

**Partially fits: 3.15 slide 50 in isolation.** No trigger box, and its own dark red box states "Logic For selecting account unknown". Read together with slide 49 it uses U2b, U2d and U4a; read alone it cannot be mapped, because the rule that selects the account is the missing piece. Named as a **build blocker**, not a catalogue gap.

**Every step type in every remaining flow maps to U1 to U6 with one exception, which is candidate 1.**

### 3. Candidate seventh utility, proposed and not added

**None of these has been added to the catalogue.**

**Candidate 1: system write execution. Recommend admitting.** The single most frequently drawn step type in the deck, and the catalogue has no home for it. Every flow ends by writing to EVE and often to a downstream system: create the organisation, update the flags, delete the alt code, upload via EVE RDM Bulk Loader, set up in Nomura Now and Postedge. U1 to U6 cover deciding what to do; nothing covers doing it. CLAUDE.md already implies it twice, in the wizard "outputs" field and in the principle that a human decides before any write, but it is not a catalogue capability. It needs its own entry because it carries properties none of the others do: idempotency, rollback, audit trail, and the distinction between screen automation and an API. **Strongest candidate by a wide margin.**

**Candidate 2: approval orchestration with pending-state tracking. Recommend admitting, and using it to complete U5.** Distinct from U6: U6 is the presentation to one reviewer at one moment; this is the machinery of requesting approval from a party who may be outside EDM, holding the request in a named state, chasing, resuming and closing on no reply. Evidence: 2.13 (a ServiceNow Legal ticket, an external approver, no rejection path drawn), 3.10 ("Wait for Approval mail" plus an "Account on hold" state, and a POC approvals spreadsheet outside EVE), 3.8-US ("Approval from FO for each TA", i.e. per-item approval), G3 {1.4 to 1.7} (three sequential approval points including a regional loop). The same pending-state machinery is what U5 is missing in 10 of its units.

**Candidate 3: cross-system position and linkage check. Recommend admitting, or formally splitting U4 into U4a and U4b.** Currently folded into U4. Evidence: 2.7 both regions, 3.8 all three regions, 3.4-Totoro. It reads many front-office systems to answer one question before a destructive action. Arguments for splitting: many read connectors rather than one lookup; it gates the irreversible actions; and it forces the Phase 1 read versus Phase 2 write decision into the open. Its Phase 2 write-side counterpart already exists as a separate activity, 3.13.

**Candidate 4: reference data lookup from an uncontrolled external source. Propose as a U4a sub-mode, not a utility.** Evidence: 2.15 and 3.16 both call the GLIEF Portal (industry name GLEIF), an external website Nomura does not control. It differs from U4a in what it worries about: availability, rate limits, terms of use, format change, and what the automation does when the source is down. Promote it to a utility only if the external-dependency risk needs its own owner.

**Candidate 5: document extraction and outbound document signing. Recommend splitting the two halves.** Evidence: 3.17, whose activity name is "Document validation for Name change, F1SA or if any other provided", and 3.15's PDF, Excel and Word attachments including a password-protected file. The inbound half (read a document rather than a form or spreadsheet) is best treated as a **U2b extension**. The outbound half (sign a document and send it to the PB) is an external-facing action with a control question attached, who signs and on what authority, so it should be raised as a control matter before it is designed as a capability.

**Candidate 6: bulk and batch load. Do not admit.** Evidence was 2.3 only (slide 17, EVE RDM Bulk Loader). **2.3 is now covered elsewhere with no to-be, so this candidate has no to-be to serve.** Slide 17 is retained as an as-is note in chapter 2 section 2. Revisit if Rupesh reassigns slide 17 to an activity that does have a to-be, in which case it becomes a mode of candidate 1 rather than a utility in its own right.

---

## The IP4 decision, applied

**IP4 is added to the taxonomy.** Definition for CLAUDE.md: *IP4 = the request originates as an item in EVE workflow or as an EVERequest, not as an email. Supporting detail may arrive separately by email.*

**The principle "automation starts at email receipt" becomes "automation starts at request receipt (email or EVE work item)".** Work performed by the requestor before receipt remains out of scope.

**U1 applies to email channels only. For IP4, U2 reads the request data from EVE (sub-mode U2d).**

Evidence, and how each unit is now tagged:

| Unit | Evidence | Tagged as |
|---|---|---|
| 3.1 | "Open EVE application / via workflow-EVERequest" alongside an email start box | IP3 + IP4, trigger [BUSINESS INPUT] |
| 3.8-US | "Request sent through mail/EVE workflow/KYC team" | IP3 + IP4 + KYC team assumed IP3, both [BUSINESS INPUT] |
| 3.8-EMEA | Same, plus "List of org id, account id, extract from Excel" | IP2 + IP4 + KYC team assumed IP3, both [BUSINESS INPUT] |
| 3.8-AEJ | Same | IP3 + IP4 + KYC team assumed IP3, both [BUSINESS INPUT] |
| 3.10 | Start box "Open EVE Request shared"; the requestor mail carries details that arrive after | IP4, trigger [BUSINESS INPUT] |
| 3.15 | Start box "Eve Workflow-NSI"; the client mail with attachments is a later data source | IP4, trigger [BUSINESS INPUT] |

Also outside the email taxonomy, though not IP4: **1.8** is triggered by a lower environment refresh (no request at all, out of scope) and **2.13** names no channel whatsoever, which stays an open point and must not be assumed.

Three consequences for the build:

1. **Some units have more than one input pattern, so the wizard field must become a list.** 3.1 is IP3 and IP4; 3.8 is IP2 or IP3, plus IP4, plus the KYC-team source; G1 {1.1, 1.2} is IP1 and IP3. Each pattern needs its own routing signal and its own extraction sub-mode within the same configuration record. The wizard field "input: pattern (IP1/IP2/IP3)" must accept a list, and the source field must accept an EVE queue and not only a mailbox.
2. **An intake mechanism for EVE is needed and is not in the catalogue.** How the automation learns that a new EVE workflow item or EVERequest exists (polling, subscription, webhook, database read) is not stated anywhere in reference/. This is a technical question for the platform and EVE owning teams, not a business question.
3. **A correlation step is needed and is not drawn anywhere.** For 3.10 and 3.15 an email arrives carrying supporting detail for an EVE item that is already open. Tying the two together is neither routing (U1) nor extraction (U2) as currently defined. It is small, but it is on the critical path for two Phase 1 units and it should be recorded as an open design point rather than assumed.

The **KYC-team trigger on 3.8 is assumed IP3** and marked [BUSINESS INPUT] for verification, assigned to Satya. If they raise something in a system instead of sending email, that system is not named on the slide and the assumption fails.
