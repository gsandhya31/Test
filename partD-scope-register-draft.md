VINGLLAN

12345

# Session 1, Part D: scope register, draft
Source: reference/edm-activities.md (14 Sep status snapshot) and reference/flows-area-1.md to flows-area-4.md. Draft for review, not yet a BRD section.
** 58 rows .** One row per underlying activity, plus one row per system where an activity is split by system (3.4, six systems) and one row per region where an activity is split by region (3.8, three regions). Row order follows the status sheet: area 2, then area
3, then area 1, then area 4.
Column meanings:
- ** Sheet status **: the substance of the "For BRD - Business review Status on AS-IS flows" cell, condensed. Verbatim wording is preserved in reference/edm-activities.md.

9

** Scope **: Phase 1 / Phase 2 / out of scope / covered elsewhere / pending.

10

** Reason **: code from the legend below.

11

** IP **: IP1, IP2, IP3, EVE-wf (candidate IP4), or "not stated".
** HITL **: yes if a human checkpoint is drawn in the flow; "not drawn" if none is drawn. Per the CLAUDE.md design principle a human decides in every Phase 1 to-be regardless, so "not drawn" is a documentation gap, not a design decision.
** Frequency **: as stated in the flow material, else "business to populate".
-** Unblocking question **: for pending and disputed rows, the single question whose answer moves the row. Blank where the row is settled.
## Reason code legend
Code | Meaning |

20

R1
Flow created and sign off provided by business |
R2
No as-is of its own; covered by other activities in the same Level 2 area |
R3
Out of scope, business confirmed: the volume already flows through EVE workflow

23

R4
Out of scope, business confirmed: performed only when there are exceptions (override function) |

24

R5
Out of scope for automation: IT or environment action, to be recommended to the owning tech team |

25

R6

Phase 2: third-party system integration, API access not beneficial from an ROI perspective, business confirmed |

26

R7
Phase 1 for this system or region only; the remaining systems or regions are Phase 2 or pending |

27

R8
Pending: sign off or SOP not yet provided by business|

28

R9
Pending: clarifications open on the flow as drawn |

29

R10
Pending: the list the activity depends on has not been provided by business |

33

## Area 2: Organisation Creation and Maintenance

B4

| # | Activity | Sheet status | Scope | Reason | IP | HITL | Frequency | Unblocking question |
--- | --- | --- | --- | --- | --- | --- | --- 1 --- 1
1
2.1 Org creation manual | Flow created, signed off | Phase 1 | R1 | not stated | yes, 4 EYE CHECK | business to populate |
2
2.2 Org contact set up manual | Flow created, signed off | Phase 1 | R1 | IP2 | yes, 4 EYE CHECK | business to populate
3 | 2.3 Adhoc request, no dedicated workflow | Boilerplate cell: "specific queries have not been mentioned/shared" | *disputed ** | R2 as ruled, contradicted by slide 17 | not stated | yes, 4 EYE CHECK | business to populate | ** [CONFLICT] ** Slide 17 draws a
unique EVE RDM Bulk Loader flow found nowhere else. Does 2.3 keep its own as-is and to-be, or is the flow discarded? And is the status cell a copy-paste from 2.14?
4 | 2.4 NLUX hierarchy set up manua

Signed off (no "flow created" prefix) | Phase 1 | R1 | not stated | yes, Checker Approval diamond with a Modify loop, plus 4 EYE CHECK | business to populate | |

41

5 | 2.5 ALD hierarchy set up manual

Out of scope, volume flows through EVE workflow | out of scope | R3 | n/a | n/a | n/a |

2.6 IWM hierarchy set up manual

Flow created, signed off | Phase 1 | R1 | not stated | yes, 4 EYE CHECK plus requester contact | business to populate | Which fields does "Validate the requester details" cover? The slide asks the question and does not
answer it. Also: which document is the "WMD Closure process according to Standard procedure"?

45

7
2.7 EMEA Org closure
| Sign off provided for EMEA | Phase 1 | R7 | not stated | ** not drawn ** | business to populate | ** [CONFLICT] ** The slide carries a red "Pending biz confirmation" box while the sheet records EMEA sign off. Which is current? |

44

8
2.7 AEJ Org closure
SOP not provided for AEJ | pending | R8 | not stated | ** not drawn ** | business to populate | Provide the AEJ SOP. Are slides 22 and 23 two regional variants of one activity, or two different activities? |

45

9
2.8 Org MIFID contact trigger through EMEA | Out of scope, volume flows through EVE workflow | out of scope | R3 | n/a | n/a | n/a | |

46

10 |
2.9 AGTS creation | Flow created, signed off | Phase 1 | R1 | IP3 | yes, 4 EYE CHECK | business to populate | Which activity does "Duplicate Check(from activity1)" refer to, 1.1 or 2.1? |

47

11
2.10 Org maintenance | Sign off not provided |
pending | R8 | IP3 | ** not drawn **
business to populate | Which conditions route to each of the two unlabelled branches out of "Input RDM ID in Search Field"? And which of C, R, U, D can arrive, with what

Field set for each? I
| 12 | 2.11 Override function for urgent exceptions | Out of scope, exception only | out of scope | R4 | n/a | n/a | n/a | |
13 | 2.12 Org flag updates | Flow created, signed off | Phase 1 | R1 | IP3 | yes, 4 eye | business to populate | Are AFFRM, CRED, COMP, RTCP2 and COBLK the complete flag list? |
14
2.13 Org attribute changes needing Legal approval | Sign off not provided | pending | R8 | ** no channel stated ** | yes, Legal approval (drawn as a box, not a decision) | business to populate | How does the attribute change request arrive? And what happens
when Legal rejects the ServiceNow ticket, given no rejection path is drawn?|
15 | 2.14 Queries and investigation | Covered in the remaining activities of this L2 area | covered elsewhere | R2 | n/a | n/a | n/a | |

## Area 3: Account Creation and Maintenance
# | Activity | Sheet status | Scope | Reason | IP | HITL | Frequency | Unblocking question |
| --- | --- | --- | --- | --- | --- | --- | --- | --- 1
| 16 | 3.1 Account creation manual | Flow created, signed off | Phase 1 | R1
IP3 + EVE-wf | yes, Checker (terminal, no outgoing arrow) | per min, to be checked for EMEA | Confirm the EVE workflow trigger as IP4. What does the Checker do on rejection? What is

the unreadable last line of the green duplicate-entities diamond?

60

17 | 3.2 Account contact set up manual | Sign off not provided | pending | R8 | IP2 | yes, 4 EYE CHECK | business to populate | The flow is drawn identically to 2.2. Is the process the same as the Organisation one, so that 3.2 becomes a covered-elsewhere row?
The slide asks Rupesh this directly |
| 18 | 3.3 Broker, comms and expense account set up | Flow created, signed off | Phase 1 | R1 | IP3 | yes, checker (plain text on a leader line) | rare, monthly 1 or 2 | Is the extraction three fields or four? The "Extract 4 fields" box and the later blue box
disagree
| 19 | 3.4 Totoro, TA creation | Flow created, signed off | Phase 1 | R7 | IP3, contradicted | yes, Checker | 2 to 3 requests, multiple RDM ID | Does the request arrive by mail (start box) or is the subject line taken from EVE (margin note)? Both are on the same
slide
| 20 | 3.4 Global1, TA creation | Third-party integration, API access not beneficial on ROI | Phase 2 | R6 | not stated | n/a | business to populate | |

54

21 | 3.4 Falcon, TA creation | As above | Phase 2 | R6 | not stated | n/a | business to populate | ** [CONFLICT] ** The sheet names Sphinx; the slide title names Falcon. Which system is it? |

55

3.4 GMI, TA creation | As above | Phase 2 | R6 | not stated | n/a | business to populate ||

66

23

3.4 Venom-Viper, TA creation | As above | Phase 2 | R6 | not stated | n/a | business to populate | |

67

24 | 3.4 Loanet, TA creation | As above | Phase 2 | R6 | not stated | n/a | business to populate | |

68

25
3.5 LCM manual set up | Third-party integration, API access not beneficial on ROI | Phase 2 | R6 | not stated | n/a | business to populate | |

69

26 | 3.6 Account hierarchy set up | Queries pending from business | pending | R9 | IP2 | partial: a checker box is drawn, but a slide note says "add flows for 4-eye check process" | 5 to 10 mails per month | Draw the 4-eye check. Where does the arrow out of
"Ask requestor for details" go? Why is "Drop a mail internal RDM org team" a decision diamond? Is this the same process as 2.4? |

70

| 27 | 3.7 IWM account hierarchy set up | Flow created and sign off provided | ** disputed ** | R1 as recorded, no flow exists | not stated | n/a | business to populate | ** [CONFLICT] ** Slide 39 draws no flow, only "Same as organization creation and maintenance".
Which numbered activity is the referent, presumably 2.6? Or does a flow exist that was not shared? |

71

| 28 | 3.8 US, Account closure | Sign off provided for US | Phase 1 | R7 | IP3 + EVE-wf + KYC team | yes, Manager Approvals and OBI report, plus FO approval per TA | business to populate | What is the terminal outcome of the "Status-Restricted" branch, which
currently ends at "No OBI report needed"? Which channel does the KYC team use?

72

29 | 3.8 EMEA, Account closure | SOP not provided | pending | R8 | IP2 + EVE-wf + KYC team | ** not drawn ** | business to populate | Provide the EMEA SOP. Why is the LVCC alt code check drawn twice, once unconnected? What condition routes out of "Check for
positions"?

73

30 | 3.8 AEJ, Account closure | SOP not provided | pending
the AEJ SOP and the AEJ FO system list |

R8 | IP3 + EVE-wf + KYC team | ** not drawn ** | business to populate | ** [CONFLICT] ** The slide is titled ASIA but the extraction step reads "inactive US trading Accounts". Which is correct? Provide

74

| 31 | 3.9 Override function for urgent exceptions | Out of scope, exception only | out of scope | R4 | n/a | n/a | n/a | Minor: the slide carries a "Review done" box although the activity is out of scope. Confirm the out-of-scope decision stands

75

32 | 3.10 SSI set up and maintenance | Flow created, signed off | Phase 1 | R1 | EVE-wf plus mail body | yes, POC approvals plus a "Wait for Approval mail" diamond and an "Account on hold" state | business to populate | The slide carries a reviewer question
What is automate?". Which part of this activity is in scope? Where does the POC approvals spreadsheet live and who maintains it?

76

| 33 | 3.11 Account flag updates | Signed off; flag types query pending | Phase 1 | R1 with R10 open | IP3 | yes, checker (terminal, no outgoing arrow) | business to populate | What are the flag types? Is the list the same as 2.12's (AFFRM, CRED, COMP, RTCP2,
COBLK)? |

77

34 | 3.12 Queries and investigation | Queries list pending, no flow created | pending | R10 | not stated | n/a | business to populate | Provide the queries list. Is 3.12 covered by the other 3.x activities, as 2.14 is for area 2? Does the subject-line note on
lide 46 belong to 3.12 or is it duplicated from 3.11? |

78

35 | 3.13 Linking alt codes for FO systems, e.g. GMI in EVE | Third-party integration, API access not beneficial on ROI | Phase 2 | R6 | not stated | n/a | business to populate | |

79

36 | 3.14 BPS, Impact, Gloss setup for Firm side for NSI | Third-party integration, API access not beneficial on ROI | Phase 2 | R6 | not stated | n/a | business to populate |
37 | 3.15 NSI account set up | Sign off not provided; "input in the form of ?" | pending | R8 | EVE-wf plus client mail with PDF, Excel and Word attachments, one password protected
'Logic For selecting account unknown". Provide the account selection rule. How do slides 49 and 50 connect, given slide 50 has no start box? Who holds the password for the PB sheet?

#*not drawn ** | business to populate | ** Build blocker :** slide 50 states

81

unconnected "Need to check business purpose" box?
38 | 3.16 Account LEI maintenance | Flow created, signed off; "input in the form of ?" | Phase 1 | R1 | IP3 | ** not drawn ** | business to populate | Drawn identically to 2.15. Is this a covered-elsewhere row, or a separate to-be? What is the subject of the

82

39 | 3.17 Client document validation and sign back | Sign off not provided; "input in the form of ?" | pending | R8 | IP3 | yes, a signature ("If match, signed and sent to PB") | business to populate | Who signs, and on what authority? What is F1SA? Where is
the validated document recorded, given neither branch returns to EVE? |
Note on 3.15, 3.16 and 3.17: the journal entry of 15 Sep records the input-format question for these three as closed, but no answer appears anywhere in reference/. The IP values above are read off the flow start boxes, not off a business answer.

## Area 1: Confirmation, Contacts & General Type
#
Activity | Sheet status | Scope | Reason | IP | HITL | Frequency | Unblocking question |

91

| --- | --- | --- | --- | --- | --- | --- | --- 1 --- 1

92

40

1.1 Confirmation contact removal | Flow created, signed off | Phase 1 | R1 | IP1 + IP3 | yes, two Checker boxes | business to populate | Shares one flow with 1.2 across slides 4 to 7. Confirm they are one to-be, not two|

93

1.2 Confirmation contact addition | Flow created, signed off | Phase 1 | R1 | IP1 + IP3 | yes, two Checker boxes | business to populate | As above|

42

1.3 Contact set up via Excel | Flow created, signed off | Phase 1 | R1

** IP2 ** | ** not drawn ** | business to populate | Who checks, given no checkpoint is drawn? |

43

1.4 G-Type set up | Flow created, signed off | Phase 1 | R1 | *IP2 ** | yes, three points: regional approval loop, requestor UAT approval, Checker Approval | business to populate | Shares one flow with 1.5, 1.6 and 1.7 on slide 9. Confirm they are one
to-be,
not four

96

44

1.5 G-Type maintenance | Flow created, signed off | Phase 1 | R1 | ** IP2 ** | yes, as 1.4 | business to populate | As above |

97

45
1.6 G-Type related activity | Flow created, signed off
Phase 1 | R1 | ** IP2 ** |
yes, as 1.4 | business to populate | As above |

98

46

1.7 G-Type related activity | Flow created, signed off

Phase 1
R1 | ** IP2 **
yes, as 1.4 | business to populate
As above |

47
1.8 Environment refresh data set up | IT team of today can take this up | out of scope | R5 | n/a, triggered by a lower environment refresh | n/a | business to populate | Which tech team owns the recommendation? |

190

48 | 1.9 Queries and investigation | Flow has been created; covered by 1.1 to 1.7 | covered elsewhere | R2 | n/a | n/a | n/a | The sheet says covered by 1.1 to 1.7; slide 10 says "Activity 1 to 8 already include this activity". Which is correct, and does the
difference matter given 1.8 is out of scope? |

101

49 | 1.10 Nomura Now and Postedge setup for NSI | Third-party integration, API access not beneficial on ROI | Phase 2 | R6 | not stated | n/a | business to populate | |

102
103

** Note :** the input pattern for 1.3 to 1.7 is IP2 for all five, read directly off the flow start boxes ("Excel Attached", "G-Type excel form received via email"). This closes a standing open point. Chapter 1's business-input request therefore covers HITL,
frequency and volumes only.

194
105
106
107

## Area 4: Commission & Fees

108
190

All nine rows are Phase 2 for the same reason (R6, third-party system integration, API access not beneficial from an ROI perspective, business confirmed). No slide content was read, so input pattern, HITL and frequency are business to populate throughout.

110
111

Activity | Sheet status | Scope | Reason
IP | HITL | Frequency | Unblocking question |

11

---
-- | --- | --- | --- | --- | --- | --- | --- 1

11

50
4.1 Commissions Fails Reports investigation | Third-party integration, API access not beneficial on ROI | Phase 2 | R6 | not stated | business to populate | business to populate | |

114

51
4.2 Checking Prop and Client Give Up Agreement | As above | Phase 2 | R6 | not stated | business to populate | business to populate | |

11

52
4.3 Client Commission Schedule approval in CAT (per the sheet) | As above | Phase 2 | R6 | not stated | business to populate | business to populate | ** [CONFLICT] ** reference/flows-area-4.md gives this title to 4.4. Which numbering is correct?

11

53
4.4 Fee and Commission from the Exchange and Agent Broker (per the sheet) | As above | Phase 2 | R6 | not stated | business to populate | business to populate | ** [CONFLICT] ** As above, titles swapped between the two sources

117

54
4.5 RDM Account/Book mappings in GMI | As above | Phase 2 | R6 | not stated | business to populate | business to populate | |

118

55
4.6 Queries and Investigation | As above | Phase 2 | R6 | not stated | business to populate | business to populate | Is this covered by the other 4.x activities, as 2.14 is for area 2? |

119

56

4.7 Rate maintenance for FX products | As above | Phase 2 | R6 | not stated | business to populate | business to populate | |

120

57
4.8 Account maintenance in LIMA | As above | Phase 2 | R6 | not stated | business to populate | business to populate | |

121

58 |
4.9 Payables & Receivables report | As above | Phase 2 | R6 | not stated | business to populate | business to populate | |

122
123

Only 4.5 (GMI) and 4.8 (LIMA) name a third-party system in the title. For the other seven, the third-party dependency behind reason code R6 rests on the status sheet and the business classification, not on any flow material.

124
125
126
127

127

## Summary of the register

128
129

Scope | Rows | Activities |

130

--- | --- / --- 1

131

Phase 1, settled | 24 rows | 22 activities plus 2 single-region rows (2.7 EMEA, 3.8 US) |

132

Phase 1, disputed | 2 rows | 2.3 (rule versus documented flow), 3.7 (signed off, no flow) |

133

Covered elsewhere | 3 rows | 1.9, 2.14, and 3.7 if reclassified |

134

Pending | 9 rows | 2.7 AEJ, 2.10, 2.13, 3.2, 3.6, 3.8 EMEA, 3.8 AEJ, 3.15, 3.17 |

135

Phase 2 | 18 rows | 1.10, 3.5, 3.13, 3.14, 4.1 to 4.9, plus 5 non-Totoro 3.4 system rows |

136

Out of scope | 5 rows | 1.8, 2.5, 2.8, 2.11, 3.9 |

137

** Total ** | ** 58 rows, 51 activities ** | |

138
139

Two rows carry a hard build blocker rather than a scope question: ** 3.15 ** (the account selection rule does not exist) and ** 3.6 ** (the 4-eye flow has not been drawn, and one arrow has no target).

140
