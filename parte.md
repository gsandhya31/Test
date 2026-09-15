# Session 1, Part E: facts needed and not found in reference/

Every fact I needed to write a chapter or a wizard configuration record and could not find in reference/. Grouped by the owner who can close it. Numbered continuously, 61 items.
Revised 15 Sep to apply the Part B to E decisions: eight items from the previous version are now closed by decision and are listed at the end so nothing is silently dropped.

Owner names are taken from the SABRE SPOC and Business SPOC columns of reference/edm-activities.md. **In this log file the names are routing labels. In brd/ they appear in the stakeholder table only, never inside process or requirement text, per CLAUDE.md.**

Activity names quoted below are the status-sheet values verbatim.

Reading note: **[BLOCKER]** stops a to-be from being written at all. **[SECTION 10]** can be carried into the open-points section of a chapter and the draft still ships on 18 Sep. **[BUSINESS INPUT]** is a value the business supplies or verifies; the [BUSINESS INPUT] tables carry frequency and volumes only, everything else so marked is an inline open point.

---

## Area 1: Confirmation, Contacts & General Type. Owners: Rishabh (SABRE), Ashish (Business)

1. **Volumes and frequency for all ten activities.** [BUSINESS INPUT] Not one number appears in slides 1 to 13. The nearest thing is "Email (Less Freq)" on the 1.1 / 1.2 flow, which is a comparison, not a volume. **[SECTION 10]**
2. **Who checks 1.3, "3) Duplicate check of G-type attribute requested".** Slide 8 draws no human checkpoint, yet the design principle requires one in every Phase 1 to-be. **[SECTION 10]**
3. **The duplicate-match rule.** Four activities are duplicate checks by name: 1.3, 2.1 ("1) Duplicate checks for Org creation"), 3.1 ("1) Duplicate check for Account Creation") and, by cross-reference, 2.9's "Duplicate Check(from activity1)". **What makes two records a duplicate is stated nowhere in reference/.** It is a rules-based U3 check on the highest-frequency activity in the programme (3.1, "per min"). **[BLOCKER for four units]**
4. **Whether the mandatory confirmation entity list is complete** (NIP, NFPE, NFRNC, NFPFR, NAIMF), and where the authoritative list is maintained. A rules-based U3 cannot be built on a possibly partial list. **[BLOCKER for group G1]**
5. **The public-domain email rejection list.** The flow rejects public-domain addresses but gives no list and no source. Is it a maintained list, a domain pattern, or judgement? **[BLOCKER for group G1]**
6. **What the fax tone check actually checks,** and whether fax remains an in-scope channel in the to-be at all. **[SECTION 10]**
7. **The full route code and email combination matrix.** The rule is named on slides 4 to 7; the valid combinations are not enumerated. **[BLOCKER for group G1]**
8. **Which fields are mandatory on the G-type form, and the rules for the complex components** named in 1.4's activity name: alt code, sector code, trading scope. The slide 13 TACE sector codes table may be part of the answer for sector code; nothing covers alt code or trading scope. **[BLOCKER for group G3]**
9. **Whether the slide 12 and 13 reference notes are complete.** They carry the standard query format and five relationship-justification samples. Five samples is a sample set, not a rule. Are there further categories? **[SECTION 10]**
10. **Which activities 1.9 is covered by.** The sheet says "essentially covered in activities frm 1.1 to 1.7"; slide 10 says "Activity 1 to 8". 1.8 is out of scope so the difference is probably immaterial, but it should be confirmed rather than assumed. **[SECTION 10]**
11. **Whether 1.10's Phase 2 classification is confirmed.** The sheet reads "out of scope-thrid party integration (awaiting business confirmation). Will be taken up in phase2", i.e. the classification itself is awaiting confirmation. Also: what the setup in Nomura Now and Postedge for NSI involves, since slide 11 carries a title and a margin note only. **[SECTION 10]**

## Area 2: Organisation Creation and Maintenance. Owners: Vishnu (SABRE), Rupesh (Business)

12. **Volumes and frequency for all fifteen activities.** [BUSINESS INPUT] No area 2 slide states either. **[SECTION 10]**
13. **How the 2.1 request arrives.** The start box reads only "Organization Creation Request" with no channel, so the wizard "input: pattern" field cannot be filled. **[BLOCKER for 2.1]**
14. **How the 2.13 request arrives.** The start box reads only "Attribute change request". **No channel is stated anywhere and it must not be assumed.** Recorded as an open point by decision, 15 Sep. **[BLOCKER for 2.13]**
15. **Which fields 2.1's "Validate required fields" covers.** **[BLOCKER for U3 on 2.1]**
16. **Which fields 2.6's "Validate the requester details" covers,** and where the document called "WMD Closure process according to Standard procedure" can be found. The slide asks the first question and does not answer it. **[BLOCKER for U3 on 2.6]**
17. **Which activity slide 17 belongs to.** 2.3 is now covered elsewhere with no to-be, and slide 17 is retained as an as-is note in chapter 2 section 2. Three parts to put to Rupesh together: (a) which activity the EVE RDM Bulk Loader mechanism belongs to, since it appears nowhere else in the deck; (b) whether the 2.3 status cell is a copy-paste from 2.14, because it is word for word 2.14's boilerplate and describes a queries activity rather than an adhoc-request activity; (c) **3.3 carries the identical sheet name, "Adhoc request raised for non-availability of the dedicated workflow", and is Phase 1 with its own signed-off flow.** The same activity name is covered elsewhere in area 2 and a to-be in area 3. **[SECTION 10]**, but it decides whether a documented mechanism is discarded
18. **Why 2.4's Amend branch is drawn as a closure flow.** Either the branch is mislabelled or amendment proceeds by closing and recreating. The two lead to different to-be designs, and the same structure is reused by 3.6. **[BLOCKER for the 2.4 / 3.6 configuration]**
19. **Whether the red "Pending biz confirmation" box on the 2.7 slides is current, or the sheet's EMEA sign off is.** Also: where does the position-found path on slide 22 terminate? It has no outgoing arrow. **[SECTION 10]** for the first, **[BLOCKER]** for the second
20. **The AEJ SOP for 2.7,** plus confirmation that slides 22 and 23 are two regional variants of one activity rather than two activities, and why the LVCC alt code path on slide 23 has no incoming arrow. **Also the region label**: the sheet says AEJ, the slide says Asia. **[BLOCKER for the 2.7 AEJ region sub-section]**
21. **Which activity 2.9's "Duplicate Check(from activity1)" refers to,** 1.1 or 2.1. Also: "Country of Domicile" appears twice in both seven-box attribute lists on slide 25, so the real field count may be six. **[BLOCKER for the 2.9 field schema]**
22. **The 2.10 branch conditions and CRUD field sets.** What routes a request to each of the two unlabelled arrows out of "Input RDM ID in Search Field", which of create, read, update and delete can arrive, and the field set required for each. The activity is "10) Orgs / Vendor attributes movements" and the flow says "Follow actions mentioned in the email (CRUD)", so **extraction must decide the operation, not just the values.** This is the hardest extraction case in the programme. **[BLOCKER for 2.10]**
23. **Whether 2.12's flag list is complete** (AFFRM, CRED, COMP, RTCP2, COBLK), and whether the requestor being the ODRG team, an internal team rather than a business requestor, changes anything about intake. Answers here also close 3.11, which carries the identical sheet name. **[BLOCKER for the 2.12 / 3.11 configuration]**
24. **What happens when Legal rejects the 2.13 ServiceNow ticket.** "Ticket Request Approved" is drawn as a box, not a decision, so there is no rejection path. Also expand "COD"; slide 25 writes "Country of Domicile" in full, slide 29 does not. **[BLOCKER for 2.13]**
25. **The subject of the unconnected "Need to check business purpose" box** on slides 31 and 51. It floats with no connector and no stated subject, so which step it questions cannot be told. **[SECTION 10]**
26. **What the automation does when the GLIEF Portal is unavailable.** 2.15 and 3.16 both depend on an external website Nomura does not control. Availability, rate limits and format change are not addressed anywhere. **[SECTION 10]**
27. **Confirmation that 2.5, 2.8 and 2.11 remain out of scope,** since none was transcribed and the decision rests on the status sheet alone. **[SECTION 10]**

## Area 3: Account Creation and Maintenance. Owners: Satya (SABRE), Sharon (Business)

28. **Volumes and frequency for the thirteen activities without one, plus 3.1's EMEA figure.** [BUSINESS INPUT] Only 3.1, 3.3, 3.4 and 3.6 state anything, and 3.1's reads "per min (to be checked for EMEA region)", i.e. itself unverified. **[SECTION 10]**
29. **Verification of the four IP4 triggers.** [BUSINESS INPUT] IP4 is added to the taxonomy by decision, and 3.1, 3.8 (all three regions), 3.10 and 3.15 are tagged as drawn, with the trigger marked for verification. Confirm that each request genuinely originates as an EVE workflow or EVERequest item and not as an email. **[SECTION 10]**, but it decides the intake design for four units
30. **Which channel the KYC team uses to trigger 3.8.** [BUSINESS INPUT] **Assumed IP3 by decision, pending verification.** The slide names the KYC team as a request source but not the mechanism. If they raise something in a system instead of sending email, that system is not named and the assumption fails. **[BLOCKER for 3.8 intake if the assumption is wrong]**
31. **What the 3.1 Checker does on rejection,** given the Checker box is a terminal with no outgoing arrow. Also the unreadable last line of the green duplicate-entities diamond, which is dark text on dark green. **[BLOCKER for 3.1]**
32. **The 3.2 sign-off.** The structure question is closed by decision (one parameterised configuration written at 2.2, org or account), but the sheet still records sign off pending and the slide still carries the yellow box asking Rupesh to confirm the process is the same as the Organisation one. **[SECTION 10]**, the to-be proceeds regardless
33. **Whether 3.3 extracts three fields or four.** The "Extract 4 fields" box and the later blue box disagree, with the alt code added at a separate step. **[BLOCKER for the 3.3 extraction schema]**
34. **Whether the 3.4 request arrives by mail or the subject line is read from EVE.** The start box says "TA Creation Request Received Via Mail"; the margin note says "Subject line: not from mail, check in EVE". Both are on the same slide. **[BLOCKER for 3.4 intake]**
35. **Three things on 3.6.** Draw the 4-eye check, which a yellow slide note says is still to be added. Where does the arrow out of "Ask requestor for details" terminate, since it has no target box? And why is "Drop a mail internal RDM org team" drawn as a decision diamond when the label is an action? **[BLOCKER for the 2.4 / 3.6 configuration]**
36. **The 3.8 US flow gaps.** The terminal outcome of the "Status-Restricted" branch, which ends at "No OBI report needed" with no terminal, and why "TA inactivation process" and "Closure process" have no incoming arrow. **[BLOCKER for 3.8 US]**
37. **The 3.8 EMEA SOP and flow gaps.** Why the LVCC alt code check appears twice with the second copy unconnected, and what condition routes out of the "Check for positions" diamond, whose single outgoing arrow is unlabelled and whose "Positions not clear" and "Not closed" boxes float unattached. **[BLOCKER for the 3.8 EMEA region sub-section]**
38. **The 3.8 AEJ SOP, region and system list.** The slide is titled ASIA but its extraction step reads "Extract list of inactive US trading Accounts", the same wording as the US slide, so one of the two is wrong. The sheet says AEJ, the slide says ASIA: confirm the region label. Provide the AEJ FO system list. **[BLOCKER for the 3.8 AEJ region sub-section]**
39. **The front-office system read list per region for the closure checks.** The flows name GMI, Totoro, Euclid, Nuvo, Venom, Viper and Loanet across different slides with no consistent list. Needed for U4b on 2.7 and 3.8, and it forces a decision the deck never states: **Phase 1 needs read access to systems whose write automation is Phase 2 or out of scope** (GMI, Venom-Viper, Loanet, Global1 / Sphinx). Note that 3.13, "13) Linking alt codes for FO systems e.g. GMI in EVE", is the Phase 2 write-side counterpart of the same linkage domain. **[BLOCKER for 2.7 and 3.8]**
40. **Which part of 3.10 is in scope.** The slide carries the reviewer's own question, "What is automate?", so the business has not settled it. The activity is "10) Approvals related to Reparent of TA". **[BLOCKER for 3.10]**
41. **Where the POC approvals spreadsheet lives, who maintains it, and whether the automation may read it.** 3.10's approval routing depends on an Excel list held outside EVE. **[BLOCKER for 3.10]**
42. **The 3.11 flag types.** The sheet records sign off with this query explicitly open. Are they the same five as 2.12? Answering item 23 answers this. **[BLOCKER for the 2.12 / 3.11 configuration]**
43. **The 3.12 queries list,** and whether 3.12 joins the covered-elsewhere set as 1.9 and 2.14 have. Slide 46 is empty and titled "(to -work)". Also: does the subject-line note on slide 46 belong to 3.12, or was it duplicated from slide 45? **[BLOCKER for 3.12, which currently has no to-be]**
44. **The 3.15 account selection rule.** Slide 50 carries a dark red box reading "Logic For selecting account unknown". **This is the single hardest blocker in the programme: without the rule there is no to-be.** Also: how do slides 49 and 50 connect, given slide 50 has no start box? And who holds the password for the PB sheet marked "(Password Protected)"? **[BLOCKER for 3.15]**
45. **Three things on 3.17, "17) Document validation for Name change, F1SA or if any other provided".** Who signs the document sent back to the PB, and on what authority, since signing is an external-facing action. What F1SA is; the acronym appears in the activity name and is never expanded. And where the validated document is recorded, since neither branch returns to EVE. **[BLOCKER for 3.17]**
46. **Confirmation that 3.5, 3.9, 3.13 and 3.14 keep their classifications,** since none was transcribed. Minor oddity: slide 43 carries a floating "Review done" box although 3.9 is out of scope. **[SECTION 10]**

## Area 4: Commission & Fees. Owners: Aastha (SABRE), Rupesh (Business)

47. **Which third-party system each of 4.1, 4.2, 4.3, 4.4, 4.6, 4.7 and 4.9 depends on.** Only 4.5 (GMI) and 4.8 (LIMA) name one in the activity name, yet all nine carry the same third-party Phase 2 reason. The reason is therefore unevidenced for seven of nine. **[SECTION 10]**
48. **Whether CAT is an internal system or third party.** It appears in 4.3's activity name, "3) Client Commission Schedule approval in CAT", and is not in the CLAUDE.md internal system list. **[SECTION 10]**
49. **Whether 4.6, "6) Queries and investigation", is covered by the other 4.x activities,** as 1.9 and 2.14 are for their areas. All four areas have a queries activity and all four are currently handled differently. **[SECTION 10]**

## IT and the owning tech teams

50. **Who owns the 1.8 recommendation.** The sheet says "this activity can be taken up by the IT team of today" but names no team. Chapter 1 needs a named recipient. **[SECTION 10]**
51. **How the automation learns about a new EVE workflow item or EVERequest.** Polling, subscription, webhook, database read? This is the intake mechanism for the four IP4 activities (3.1, 3.8, 3.10, 3.15) and it does not exist in the catalogue or anywhere in reference/. **[BLOCKER for IP4 intake]**
52. **How an inbound email is correlated to an EVE item that is already open.** For 3.10 and 3.15 a mail arrives carrying supporting detail for an existing EVE request. Tying the two together is neither U1 routing nor U2 extraction as defined, and it is drawn on neither slide. Small, but on the critical path for two Phase 1 units. **[BLOCKER for 3.10 and 3.15]**
53. **How the IP1 webform is read.** The 1.1 / 1.2 start boxes say "Webform / EVE" but not whether the structured fields behind the link are reachable by API, by database, or by screen only. The whole U2a sub-mode rests on this one flow. **[BLOCKER for U2a]**
54. **The mailbox inventory, and how the automation is granted access.** `RDM-ORGS2@uk.nomura.com` on slide 1 is the only address in reference/. Do all 51 activities arrive there, or do area 3 and area 4 have their own mailboxes? One mailbox means U1 is one classifier over many classes; several mailboxes means several smaller ones. **[BLOCKER for U1 design]**
55. **What the EVE RDM Bulk Loader is and whether it is callable.** Named on slide 17 only. Relevant only if item 17 reassigns slide 17 to an activity that has a to-be. **[SECTION 10]**

## Platform and the technology team

56. **There is no target-platform specification in reference/ at all.** Nothing describes what the automation runs on, so no chapter can say how a utility is realised. **[BLOCKER for the platform and non-functional sections of every chapter]**
57. **What the Chinou API can and cannot do.** The AI execution stack is named in CLAUDE.md but no capability document exists in reference/. Needed to say whether U2c is feasible for the harder cases, above all 2.10's CRUD determination. **[BLOCKER for U2c feasibility]**
58. **The wizard configuration record schema.** CLAUDE.md names the fields (input pattern, mailbox or source, routing signal, extraction, checks, decision points, outputs) but no schema, worked example or validation rules exist. Two changes are already required by the IP4 decision: **input pattern must accept a list**, because 3.1, 3.8 and group G1 each have more than one, and **the source field must accept an EVE queue, not only a mailbox**. **[BLOCKER for wizard-readiness]**
59. **How writes are executed, per system.** API or screen automation, for EVE and for each downstream system (ServiceNow, NEWS, PCM, Takara, Totoro, GMI, Nomura Now, Postedge). This is the gap behind the strongest seventh-utility candidate, system write execution, which is the most frequently drawn step type in the deck and has no home in the catalogue. **[BLOCKER for every to-be]**

## Compliance and AI Governance

60. **The AI Governance Standard itself is not in reference/.** CLAUDE.md requires citation by article and verbatim quotation, and names Article 9 (Responsible and Trustworthy AI Principles) and Article 2-1 (AI Business Owner as a 1LOD role), but the text of neither is available. I will not paraphrase and present it as a quote. Also needed: **the named AI Business Owner** for this initiative, per Article 2-1; no name appears anywhere in reference/. **[BLOCKER for the governance section]**
61. **NTI and ORMF.** Both are referenced by CLAUDE.md. Neither document, nor any summary of what they require of this initiative, is in reference/. **[BLOCKER for the governance section]**

## Hemant and Mayur, as the update-email recipients

- **The expected cadence, format and level of detail of the update email.** Not a fact about the process, but it determines what is produced alongside the draft. Low priority relative to the 18 Sep date. **[SECTION 10]**

## SG, already ruled

Ruled 15 Sep, first entry: slide 18 ignored, text kept for provenance; slides 63 to 73 are reference material, not transcribed; draft v0.1 written from the area files as they stand with open points carried into section 10.

Ruled 15 Sep, second entry: the to-be rule (pending sign-off does not block a to-be); IP4 added and "automation starts at request receipt (email or EVE work item)"; U1 email channels only and U2 reads EVE for IP4; 2.3 covered elsewhere; 3.7 points to 2.6; 3.4 as two register rows; 4.3 / 4.4 sheet authoritative; chapter 4 with no template sections; flow-group sub-sections; per-region rows and sub-sections; cross-area duplicates written once as one parameterised configuration; naming from the sheet verbatim with an alias column; register order area 1 to 4; [BUSINESS INPUT] tables carry frequency and volumes only.

**Still needed from SG:** which seventh-utility candidates are admitted to the catalogue. Six were proposed in partC and none added. The recommendations there are: admit system write execution; admit approval orchestration with pending-state tracking, and use it to complete U5; admit cross-system position and linkage check, or split U4 formally into U4a and U4b; treat uncontrolled external reference lookup as a U4a sub-mode; split candidate 5 into a U2b extension plus a control question on document signing; do not admit bulk and batch load, which lost its only evidence when 2.3 lost its to-be.

## Stakeholder table

Needed for the stakeholder section and not in reference/: **surnames, roles and regional coverage for Rishabh, Ashish, Vishnu, Rupesh, Satya, Sharon and Aastha.** The status sheet gives first names only. Also unresolved: 2.7 and 3.8 are split by region and the SPOC columns are not, so who owns the EMEA and AEJ answers is not recorded, and those are the rows where the answers are missing.

---

## Closed by the 15 Sep decisions, listed so nothing is silently dropped

| Previously | Now |
|---|---|
| The 2.3 disposition | Covered elsewhere, no to-be. Slide 17 retained as an as-is note. The residual questions survive as item 17 |
| 3.4's Sphinx versus Falcon naming | **Dropped by decision.** The sheet's system list governs |
| The 3.7 as-is | Covered elsewhere, points to 2.6. The [CONFLICT] that the sheet claims a signed-off flow that does not exist is retained for the record in partB and partD, not as a question |
| 4.3 / 4.4 title swap | The sheet is authoritative. reference/flows-area-4.md corrected |
| Confirmation of IP4 as a pattern | Added to the taxonomy. What survives is verification of the four triggers, item 29, and the KYC channel, item 30 |
| Whether chapter 1's activity groups are one to-be or several | Sections 2 and 5 carry one sub-section per flow group: G1 {1.1, 1.2}, G2 {1.3}, G3 {1.4 to 1.7} |
| Whether 3.2 and 3.16 are the same process as 2.2 and 2.15 | Written once in the earlier chapter, cross-referenced, one parameterised configuration each. 3.2's outstanding sign-off survives as item 32 |
| Whether chapter 4 needs a reduced template | No template sections at all: one Phase 2 note plus the activity list |

---

## Cross-cutting observations

**Volumes and frequency are the single largest gap.** Four statements exist across 51 activities (3.1, 3.3, 3.4, 3.6), and one of those four flags itself as unverified. Without volumes there is no business case and no sizing, and this is the one gap only the business can close. It is also the whole content of the [BUSINESS INPUT] tables.

**Validation rule content is the second largest gap, and it grew.** Deriving U3 from the drawn steps rather than from the slide tags takes the number of units needing rules from 8 to 22 without adding a single rule. Items 3 to 8 are all area 1, and they are the only real rules in reference/. For the other 44 activities the rule set does not exist. Item 3, the duplicate-match rule, is the most valuable single answer on this list: it unblocks four units including the highest-frequency activity in the programme.

**Five hard blockers have no workaround:** 3.15's account selection rule (item 44), 2.10's CRUD determination and branch conditions (item 22), the duplicate-match rule (item 3), the write execution mechanism (item 59), and the AI Governance Standard text (item 60). The first three are business facts, the fourth is technical, and the fifth is a document that exists and simply has not been placed in reference/.
