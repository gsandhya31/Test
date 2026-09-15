# Session 1, Part B: activity tags and structure validation
Source: reference/edm-activities.md (14 Sep status snapshot) and reference/flows-area-1.md to flows-area-4.md. No slides were re-read.
Purpose: tag every underlying activity so the chapter structure in CLAUDE.md can be validated before drafting.
Key: IP1 = email with a link to a webform / screen. IP2 = email with an Excel attachment. IP3 = free-text email. ** EVE-wf ** = the request originates as an EVE workflow or EVERequest item, not as an email (candidate IP4, see partC). "not stated" = the flow
material does not state it, i.e. business to populate. "not drawn" in the HITL column = the flow draws no human checkpoint; per the CLAUDE.md design principle a human decides in every Phase 1 to-be regardless, so this is a documentation gap, not a design
decision.
Reason codes used in the excluded-activity tables: ** R3 ** out of scope, business confirmed, volume already flows through EVE workflow. ** R4 ** out of scope, business confirmed, performed only when there are exceptions. ** R5 ** out of scope for automation, IT or
environment action, to be recommended to the owning tech team. ** R6 ** Phase 2, third-party system integration, API access not beneficial from an ROI perspective, business confirmed.

## Area 1: Confirmation, Contacts & General Type
### Phase 1 and covered-elsewhere activities
| Act | Input pattern | As-is flow | Scope decision | Input format stated | HITL drawn | Frequency stated | Conflict with the status sheet |
--- | --- | ------------------ 1
1.1 | IP1 + IP3 | yes, slides 4 to 7, reference notes 12 and 13 | Phase 1, signed off | yes: start boxes read "Webform / EVE" and "Webform / EVE / Email (Less Freq)" | yes, two Checker boxes | no, only the words "Email (Less Freq)" | sheet describes the IP1
webform channel only; the flow adds an email channel. Already decided, journal 15 Sep |
1.2 | IP1 + IP3 | yes, same flow as 1.1 | Phase 1, signed off | as 1.1 | yes, two Checker boxes | no | the sheet gives 1.1 and 1.2 separate rows; the flow draws one process across four slides with no split between them |
1.3
** IP2 ** | yes, slide 8 | Phase 1, signed off | yes: "Email Received, Excel Attached and passed the mandatory fields check" | *not drawn ** | no | sheet says only "Input in the form of email"; the flow start box names an Excel attachment, i.e. IP2 |
1.4
** IP2 ** |
yes, slide 9, shared with 1.5 to 1.7 | Phase 1, signed off | yes: "Mandatory fields are filled in the G-Type excel form received via email" | yes, three points: regional approval loop, requestor UAT approval, Checker Approval | no | as 1.3 |

1.5

** IP2 ** |
yes, slide 9, shared
Phase 1, signed off | as 1.4
ves
no
as 1.3

1.6
** IP2 **
yes, slide 9, shared
Phase 1, signed off | as 1.4
yes
no
as 1.3

1.7
** IP2 ** | yes, slide 9, shared
Phase 1, signed off | as 1.4
yes
no
as 1.3 |

1.9
n/a | no. Slide 10 lower half states "Activity 1 to 8 already include this activity" | covered elsewhere | n/a | n/a | n/a | sheet says "Flow has been created" but no flow is drawn. Sheet says covered by 1.1 to 1.7; the slide says "Activity 1 to 8" |
### Excluded activities
Act | Scope decision | Reason |
--- / --- / ---
1.8 | out of scope | R5. Triggered by a lower environment refresh, not by a request. The sheet records "this activity can be taken up by the IT team of today" |
1.10 | Phase 2 | R6. Setup in Nomura Now and Postedge for NSI. No as-is flow: slide 11 carries only the title and the email-mapping margin note |
### Area 1 findings
- ** The open point "input pattern for 1.3 to 1.7" is answerable from the flow material: all five are IP2 .** Slide 8 reads "Excel Attached"; slide 9 reads "G-Type excel form received via email". Chapter 1's [BUSINESS INPUT] table therefore needs HITL, frequency
and volumes only, not input format.
Ten activities produce four as-is units: {1.1, 1.2}, {1.3}, {1.4 to 1.7}, {1.8}. Only three of those are in Phase 1 scope, so chapter 1 has three to-be units for seven Phase 1 activities.

---

## Area 2: Organisation Creation and Maintenance
### Phase 1 and covered-elsewhere activities
Act | Input pattern | As-is flow | Scope decision | Input format stated | HITL drawn | Frequency stated | Conflict with the status sheet
--- | --- | --- | --- | --- | --- | --- 1 --- 1
2.1 | not stated | yes, slide 15 | Phase 1, signed off | no. Start box reads "Organization Creation Request", no channel | yes, "4 EYE CHECK", no connector drawn | no | none |
45

| Act | Input pattern | As-is flow | Scope decision | Input format stated | HITL drawn | Frequency stated | Conflict with the status sheet |
| --- | --- | --- | --- | --- | --- | --- 1 --- 1
2.1 | not stated | yes, slide 15 | Phase 1, signed off | no. Start box reads "Organization Creation Request", no channel | yes, "4 EYE CHECK", no connector drawn | no | none |

48

| 2.2 | IP2 | yes, slide 16 | Phase 1, signed off | yes: "addition/ amendment/delete request in excel attachment" | yes, "4 EYE CHECK", no connector | no | none
2.3 | not stated | ** yes, a complete flow, slide 17 ** | ** disputed **: sheet and CLAUDE.md say covered elsewhere
no. Start box reads "Email Request Received" | yes, "4 EYE CHECK", no connector | no | ** [CONFLICT] ** slide 17 draws a distinct as-is that appears
nowhere else in the deck (EVE RDM Bulk Loader: configure request type, save file and upload, receive confirmation email). Separately, the 2.3 status cell is word for word the same boilerplate as 2.14's ("specific queries have not been mentioned/shared"), which
describes a queries activity, not "adhoc request raised for non-availability of the dedicated workflow". Reads as a copy-paste into the wrong row |

50

| 2.4 | not stated | yes, slide 19. Slide 18 ignored per SG | Phase 1, signed off | no. Start box reads "Email Request Received" | yes, "Checker Approval ?" diamond with a Modify details loop, plus "4 EYE CHECK" | no | the status cell omits the "flow created"
prefix that most rows carry. The Amend branch is drawn as a closure flow, which does not obviously correspond to "Amend" |

51

| 2.6 | not stated | yes, slide 21 | Phase 1, signed off | no. Start box reads "Email Request Received" | yes, "4 EYE CHECK" plus "Contact the requester to confirm the fund" | no | the fields to validate are an open question on the slide itself ("which fields?
"), and the "WMD Closure process according to Standard procedure" names a document not in reference/ |

52

| 2.7 EMEA | not stated | yes, slide 22 | Phase 1, signed off for EMEA, ** disputed ** | no | *$not drawn ** | no | ** [CONFLICT] ** both 2.7 slides carry a red "Pending biz confirmation" box, while the sheet records sign off provided for EMEA. On slide 22 the
position-found path has no outgoing arrow and reaches no terminal |

53

2.7 AEJ | not stated | yes, slide 23 | pending, SOP not provided | no | ** not drawn ** | no | slides 22 and 23 describe the same activity with different step sets and different terminals, unannotated as regional variations. On slide 23 the LVCC alt code path
has no incoming arrow

54

2.9 | IP3 | yes, slide 25 | Phase 1, signed off | partly: "AGTS creation email request received", no attachment named | yes, "4 EYE CHECK", no connector | no | "Duplicate Check(from activity1)" cross-references an activity number with no area prefix. "Country
of Domicile" appears twice in both seven-box attribute lists

55

| 2.10 | IP3 | yes, slide 26 | ** pending ** , sign off not provided | partly: "Email request received", plus "Follow actions mentioned in the email (CRUD)" | ** not drawn ** | no | the two branches out of "Input RDM ID in Search Field" carry no labels, so the
condition that routes to the failure path is not stated

56

| 2.12 | IP3 | yes, slide 28 | Phase 1, signed off | partly: the slide states "Required flags to be updated will be available in the email" | yes, "4 eye", no connector | no | the requestor is the ODRG team, an internal team, not a business requestor. Whether
the five flag codes (AFFRM, CRED, COMP, RTCP2, COBLK) are exhaustive is not stated |

57

2.13 | ** no channel stated at all ** | yes, slide 29 | ** pending ** , sign off not provided | no. Start box reads "Attribute change request" | yes, Legal approval, but drawn as a box not a decision | no | "Ticket Request Approved" is a box, so there is no Legal
rejection path. "COD" is not expanded, although slide 25 writes "Country of Domicile" in full |

58

2.14 | n/a
no. Slide 30 states the activity is already covered in the remaining activities of this L2 area | covered elsewhere | n/a | n/a | n/a | none
2.15 | IP3 | yes, slide 31 | Phase 1, signed off | partly: start box "Request Received / Via Mail" | ** not drawn ** | no | the status cell omits the "flow created" prefix. A floating "Need to check business purpose" box sits on the slide with no connector and
no stated subject

60
61

### Excluded activities

62
63

| Act | Scope decision | Reason |

64

| --- | --- | --- 1

65

2.5 | out of scope | R3. ALD hierarchy set up manual. Slide 20, not transcribed |

66

| 2.8 | out of scope

R3. Org MIFID contact trigger through EMEA. Slide 24, not transcribed

67

2.11 | out of scope
R4. Override function for urgent exceptions. Slide 27, not transcribed

68
69

### Area 2 findings

70
71
72

- No volumes and no frequency anywhere in the area. Chapter 2 carries a [BUSINESS INPUT] table for all 2.x activities.
- Input pattern is stated for 2.2 only (IP2). Everything else is inferred from "Email Request Received" wording or is genuinely absent (2.1, 2.13).

73

- The Validation utility tag appears on no slide in the area, although validation steps are clearly drawn (2.1 "Validate required fields", 2.6 "Validate the requester details").

74
75
76
77

## Area 3: Account Creation and Maintenance

78
79

### Phase 1 activities

81

| Act | Input pattern | As-is flow | Scope decision | Input format stated | HITL drawn | Frequency stated | Conflict with the status sheet |

82

| 3.1 | IP3 + ** EVE-wf ** | yes, slide 33 | Phase 1, signed off | partly: "Account Creation Request Received Via Mail", second box "Open EVE application / via workflow-EVERequest" | yes, "Checker" box, but it is a terminal with no outgoing arrow | ** yes:
| --- | --- | --- | --- | --- | --- | --- 1 --- 1

R3
82

| --- | --- | --- | --- | --- | --- | --- | --- 1
3.1 | IP3 + ** EVE-wf ** | yes, slide 33 | Phase 1, signed off | partly: "Account Creation Request Received Via Mail", second box "Open EVE application / via workflow-EVERequest" | yes, "Checker" box, but it is a terminal with no outgoing arrow | ** yes:
"Frequency: per min (to be checked for EMEA region)" ** | the EVE workflow route is a second trigger the three-pattern taxonomy does not cover. The green duplicate-entities diamond is dark text on dark green and its last line cannot be read

84

| 3.2 | IP2 | yes, slide 34 | ** pending ** , sign off not provided | yes: "addition/ amendment/delete request in excel attachment" | yes, "4 EYE CHECK", no connector | no | the flow is drawn identically to 2.2 (slide 16) box for box. The slide itself carries a
yellow box asking Rupesh to confirm whether the process is the same as the Organisation one |

85

| 3.3 | IP3 | yes, slide 35 | Phase 1, signed off | partly: "Broker/Comms/Expense Request Received Via Mail", no attachment named | yes, "checker" as plain text on a leader line | ** yes: "Frequency : rare, monthly 1 or 2" ** | the "Extract 4 fields" box names
Four fields; the later blue box lists only three, with the alt code added at a separate step |
| 3.4 Totoro | IP3, conflicted | yes, slide 36 | Phase 1, signed off, Totoro only | partly: "TA Creation Request Received Via Mail", contradicted by the margin note | yes, "Checker" box | ** yes: "Frequency: 2-3 requests multiple RDM ID" ** | ** [CONFLICT] ** the
sheet names the systems as "Global1 / Sphinx / GMI / Venom-Viper / Totoro / Loanet"; the slide title names "Global1/Falcon/GMI/Venom-Viper/Totoro/Loanet", i.e. Sphinx versus Falcon. Also the margin note "Subject line: not from mail, check in EVE" contradicts the
start box "Received Via Mail" |

87

| 3.6 | IP2 | yes, slide 38 | ** pending ** , awaiting clarifications | yes: "Email might have in subject line,but attached excel with fields is a mandatory" | partial. A "checker" box is drawn, but a yellow instruction box reads "add flows for 4-eye check
process", i.e. the 4-eye flow has not been drawn | ** yes: "5-10 mails per month" ** | reuses the 2.4 (slide 19) Create / Amend structure with account wording, including the same Amend-branch-is-a-closure-flow oddity. "Drop a mail internal RDM org team" is drawn
as a decision diamond although the label is an action. The arrow out of "Ask requestor for details" has no target box
| 3.7 | not stated | ** no flow .** Slide 39 carries only a box reading "Same as organization creation and maintenance" | Phase 1, signed off, ** disputed ** | no | n/a | no | ** [CONFLICT] ** the sheet records "Flow created and Sign off Provided by business"; slide
39 draws no flow at all. The pointer names an L2 area, not a numbered activity; the likely referent is 2.6 (IWM hierarchy set up manual) but the slide does not say so

89

3.8 US | IP3 + ** EVE-wf ** + KYC team | yes, slide 40 | Phase 1, signed off for US | partly: "Request sent through mail/EVE workflow/KYC team" | yes, "Check Manager Approvals and OBI report" and "Approval from FO for each TA" | no | the "Status-Restricted"
branch ends at "No OBI report needed" with no terminal outcome. "TA inactivation process" and "Closure process" have no incoming arrow. A floating "Review done for US" box sits on the slide |

90

| 3.8 EMEA | IP2 + ** EVE-wf ** + KYC team | yes, slide 41 | ** pending ** , SOP not provided | partly: as above, plus "List of org id, account id, extract from Excel"

** not drawn ** | no | a second box with identical text "Check for altcode LVCC in FO systems in
Totoro & GMI" sits unconnected below the first. "Check for positions" is a diamond with one unlabelled outgoing arrow; the floating boxes "Positions not clear" and "Not closed" have no arrows drawn to them |

91

| 3.8 AEJ | IP3 + ** EVE-wf ** + KYC team
yes, slide 42 | ** pending ** , SOP not provided | partly: as above | ** not drawn ** | no | ** [CONFLICT] ** the slide is titled ASIA but its second box reads "Extract list of inactive US trading Accounts based on RDM ID, alt
code", the same US wording as slide 40. One of the two is wrong. The three 3.8 slides carry three different step sets, three different endings and three different FO system lists, none annotated as a regional variation|

92

3.10 | ** EVE-wf ** + mail body | yes, slide 44 | Phase 1, signed off | partly: start box "Open EVE Request shared", second box "Requestor mail carries details(RDM ID, Name of SSI, EVE ID,FX NIC)" | yes, "Reach out to respective teams for approval(POC approvals)
'and a "Wait for Approval mail" diamond with an "Account on hold" state | no | the trigger is an EVE request, not an email, so the three-pattern taxonomy does not cover it. A floating "What is automate?" box is an open question from the reviewer about the
activity itself. Approvals depend on a POC approvals Excel spreadsheet held outside EVE |
|3.11 | IP3 | yes, slide 45 | Phase 1, signed off, one query open | partly: start box "Mail received", plus the routing note "Subject: TradingAlert Counterparty Name/Obligor" | yes, "checker" box, but a terminal with no outgoing arrow | no | the sheet records
"Sign off Provided by business.what are the flag types query pending", i.e. signed off with a substantive question open. This is the account-side counterpart of 2.12; slide 28 lists the flag codes and names the ODRG team, slide 45 names neither |

94

3.12 | not stated | *$no flow .** Slide 46 is titled "(to -work)" and is empty | ** pending ** , queries list not provided | no | n/a | no | consistent with the sheet ("Queries list pending from business, no flow created"). Differs from its area 2 counterpart 2.
14, which states it is covered by other activities. The subject-line note on slide 46 is identical to the one on slide 45, so whether it belongs to 3.12 is not stated |
3.15 | ** EVE-wf ** + client mail with PDF / Excel / Word attachments | yes, but two disjoint fragments: slide 49 and slide 50 | ** pending ** , sign off not provided | partly: slide 49 start box "Eve Workflow-NSI"; the client mail enters later as a data source.
Slide 50 has no trigger box at all | ** not drawn on either slide ** | no | the sheet still reads "input in the form of ?". The journal entry of 15 Sep declares the input format for 3.15, 3.16 and 3.17 closed but records no answer, so the answer is nowhere in
reference/. Slide 50 carries a dark red box reading "Logic For selecting account unknown". The PB sheet used for compare and match is marked "(Password Protected)". Slide 50 has no start box, so how it connects to slide 49 is not drawn |

96

3.16 | IP3 | yes, slide 51 | Phase 1, signed off | partly: start box "Request Received / Via Mail" | ** not drawn ** | no | the sheet reads "input in the form of ?" although the start box states "Via Mail". Drawn identically to 2.15 (slide 31) box for box,
including the same unconnected "Need to check business purpose" box; the title states the similarity

97

| 3.17 | IP3 | yes, slide 52 | ** pending ** , sign off not provided | partly: start box "Request Received Via Mail" | yes, "If match, signed and sent to PB" (signer not named) and "Send Request to client for confirmation" | no | the sheet reads "input in the form
of ?". "F1SA" is not expanded anywhere. Neither branch returns to EVE, so where the validated document is recorded is not shown |

98

### Excluded activities

100
101

| Act | Scope decision | Reason |

102

--- | --- / --- 1

103

3.4 Global1 | Phase 2 | R6. Named in the slide's own out-of-scope box. No flow drawn anywhere in the deck|

194

3.4 Falcon (sheet: Sphinx) | Phase 2 | R6. As above. Sheet and slide name different systems |

105

3.4 GMI | Phase 2 | R6. As above

106

3.4 Venom-Viper | Phase 2 | R6. As above |

107

3.4 Loanet | Phase 2 | R6. As above |

108

3.5 | Phase 2 | R6. LCM manual set up. Slide 37, not transcribed |

109

3.9

out of scope | R4. Override function for urgent exceptions. Slide 43, not transcribed. Note: slide 43 carries a floating "Review done" box although the activity is out of scope |

110

3.13
Phase 2 | R6. Linking alt codes for FO systems, e.g. GMI in EVE. Slide 47, not transcribed |

111

3.14

Phase 2 | R6. BPS, Impact, Gloss setup for Firm side for NSI. Slide 48, not transcribed |

112

112
113

### Area 3 findings

114
115

- Frequency is stated for four activities only (3.1, 3.3, 3.4, 3.6). Chapter 3's [BUSINESS INPUT] table therefore covers the remaining 3.x activities, not all of them.

116

Routing signals are stated for six activities (3.3, 3.4, 3.6, 3.8, 3.11, 3.12), the only direct evidence anywhere in the deck for the U1 hypothesis. Every one of them describes a subject line plus context, never a subject line alone.

117

Four activities start outside the locked three-pattern taxonomy: 3.1, 3.8 (all three regions), 3.10 and 3.15 begin in an EVE workflow or EVERequest item, and 3.8 can also begin with the KYC team. See partC for the IP4 finding.

118
119
120
121

## Area 4: Commission & Fees

122
123

All nine activities are Phase 2. No slide content was read, so no input format, HITL point or frequency exists for any of them; all are business to populate.

124
125

| Act | Scope decision | Reason |

126
127

4.1 | Phase 2 | R6. Commissions Fails Reports investigation |

128

4.2
Phase 2
R6. Checking Prop and Client Give Up Agreement |

129

4.3
Phase 2
R6. Title disputed, see below

130

4.4
Phase 2
R6. Title disputed, see below

131

4.5
Phase 2
R6. RDM Account/Book mappings in GMI. GMI named in the title |

132

4.6
Phase 2
R6. Queries and Investigation |

133

4.7
Phase 2
R6. Rate maintenance for FX products |

134

4.8
| Phase 2
R6. Account maintenance in LIMA. LIMA named in the title |

135

| 4.9
Phase 2 | R6. Payables & Receivables report

136
137

** [CONFLICT] 4.3 and 4.4 are swapped between the two sources .** The status sheet has 4.3 = "Client Commission Schedule approval in CAT" and 4.4 = "Fee and Commission from the Exchange and Agent Broker". reference/flows-area-4.md has the reverse. One of the two
is wrong, and it changes which activity the open CAT question attaches to.

138
139

Only 4.5 (GMI) and 4.8 (LIMA) name a third-party system in the title. For the other seven the third-party dependency rests on the status sheet and the business Phase 2 classification, not on the flow material.

140
141
142
143

## Count reconciliation

144
145

The 15 Sep figures in decisions/brd-decisions.md reconcile exactly against the status sheet:

146
147

| Category | Count | Members |

148

--- | --- | --- 1

149

Phase 1, fully signed off | 24 | 1.1 to 1.7, 1.9; 2.1, 2.2, 2.3, 2.4, 2.6, 2.9, 2.12, 2.14, 2.15; 3.1, 3.3, 3.4, 3.7, 3.10, 3.11, 3.16 |

150

| Phase 1, signed off for one region | 2 | 2.7 (EMEA), 3.8 (US) |

151
152

Phase 1, pending | 7 | 2.10, 2.13, 3.2, 3.6, 3.12, 3.15, 3.17 |
Phase 2 | 13 | 1.10, 3.5, 3.13, 3.14, 4.1 to 4.9 |

153

Out of scope | 5 | 1.8, 2.5, 2.8, 2.11, 3.9 |

154

| ** Total ** | ** 51 ** | |

155
156

Phase 1 total is 33. No drift between the journal and the sheet.

157
158

The scope register is *$58 rows ** , not 51: 3.4 expands to six rows (one per system) and 3.8 to three rows (one per region).

159

160
161
162

## Where the chapter structure in CLAUDE.md breaks

163
164

1. ** "One sub-section per activity" fails in chapter 1 .** Ten activities produce four as-is units and three to-be units, because {1.1, 1.2} share one flow and {1.4, 1.5, 1.6, 1.7} share another. Sections 2 and 5 need activity-group sub-sections keyed to the
flow, with a mapping table at the head of section 2.

165

2. ** 2.3 breaks a locked scope rule .** CLAUDE.md states 2.3 gets no separate as-is or to-be, but slide 17 draws a unique documented mechanism (EVE RDM Bulk Loader) that appears nowhere else in the deck. Either the rule bends for 2.3, or documented content is
discarded. The suspected copy-paste in the 2.3 status cell should be checked at the same time.

166

3. ** 3.7 is a Phase 1 signed-off activity with no as-is anywhere .** The locked rule forbids a to-be where no as-is exists, so as things stand chapter 3 carries a signed-off Phase 1 activity with neither a to-be nor a covered-elsewhere decision. It must become a
covered-elsewhere row pointing at 2.6, or the flow must be produced.

167

4. ** Cross-area duplication forces double authorship .** 3.2 is 2.2 box for box; 3.16 is 2.15 box for box; 3.6 reuses 2.4's structure; 3.11 is the account-side twin of 2.12; 3.7 points at area 2. One chapter per area plus one wizard configuration per activity
means writing the same to-be twice and shipping two identical configurations. Options: write once in the earlier chapter and cross-reference, or promote the shared process into the capability catalogue as a parameterised utility.

168

5. ** Regional variants have no home in the template .** 2.7 (two regions) and 3.8 (three regions) have materially different step sets, endings and system lists. Section 5 assumes one to-be per activity, and the scope-register rule covers per-system rows only.
Extend it to per-region rows and allow region sub-sub-sections in sections 2 and 5.

169

6. ** 3.15 is one activity with two disconnected as-is fragments ** , and slide 50 states its own account-selection logic is unknown. Section 2 can carry slide 50 as a sub-step of slide 49, but the missing rule belongs in section 10 as a build blocker.

170

7. ** Chapter 4 cannot fill the ten-section template .** No flow content was read, so sections 2, 3, 5, 6, 7 and 8 have no source. CLAUDE.md already calls chapter 4 short, but the template says every chapter carries the ten sections. Define a reduced template for
Phase 2 chapters: sections 1, 4, 9 and 10 only.

17

8. ** "Automation starts at email receipt" is false for four Phase 1 activities .** 3.1, 3.8, 3.10 and 3.15 start from an EVE workflow item or an EVERequest; 3.8 can also start from the KYC team; 1.8 starts from an environment refresh; 2.13 names no channel at
all. This is larger than a missing label: where there is no email, U1 has nothing to classify, and the wizard field "input: pattern (IP1/IP2/IP3)" cannot express the trigger.

172

9. ** The [BUSINESS INPUT] tables can be narrowed .** Input format is now derivable for all of area 1 (IP1 plus IP3 for 1.1 and 1.2, IP2 for 1.3 to 1.7), so chapter 1's table covers HITL, frequency and volumes only. Chapter 3's table covers the thirteen activities
without a stated frequency, not all seventeen.

173
