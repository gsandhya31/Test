Annex: scope register
Status: draft v0.1, 15 Sep 2026. ** From Session 1 onwards this file supersedes reference/edm-activities-status.xlsx for scope and status ** , per CLAUDE.md. The Excel is the 14 Sep snapshot. Any status change is logged in decisions/brd-decisions.md first, then
applied here, then to the chapters.
Source: reference/edm-activities.md (14 Sep snapshot) and reference/flows-area-1.md to flows-area-4.md, via log/session-1/partD-scope-register-draft.md.

678 9

** 55 rows, 51 underlying activities .** One row per activity, plus one row per region where the flows differ and one row per system where the activity is split by system:
Split | Rows | Note |
--- | --- | --- 1
2.7 Org closure process outside EVE. | 2 | EMEA (slide 22), AEJ (slide 23) |

12

3.4 FO system manual set up | 2 | Totoro, Phase 1 (slide 36); all other FO systems as one group, Phase 2, systems named as on the sheet
3.8 TA closure process outside EVE. | 3 | US (slide 40), EMEA (slide 41), AEJ (slide 42)|

14
15

51 + 1 + 1 + 2 = 55 rows. ** Row order is area 1, 2, 3, 4, matching chapter order .**

16

## Column meanings

18

1

** Act **: the activity number, as in reference/edm-activities.md. Authoritative where a slide title disagrees, decided 15 Sep (this is what settles 4.3 and 4.4).

20

- ** Underlying activity **: the status-sheet "Underlying Activities" value ** verbatim ** , including its numbering prefix, spelling and punctuation. Activities are not renamed.
** Alias **: the slide title where it differs from the sheet name. "same" where it matches, "none" where no slide title exists.
** Slides **: the source slide number(s) in reference/flows-jpg/.

23

- ** Sheet status **: the substance of the "For BRD - Business review Status on AS-IS flows" cell, condensed. The verbatim cell is in reference/edm-activities.md.

24

** Scope **: Phase 1 / Phase 2 / out of scope / covered elsewhere.
** Reason **: code from the legend below.

26

** IP **: input pattern. IP1 email with a link to a webform or screen; IP2 email with an Excel attachment; IP3 free-text email; IP4 the request originates as an EVE workflow or EVERequest item with no email. [BI] marks a value the business must verify.

27

- ** As-is checker drawn **: whether a human checkpoint appears in the drawn as-is. "not drawn" is a gap in the as-is documentation, not a design decision: ** the to-be carries a human decision point regardless ** , by design principle.

28

** Frequency **: as stated in the flow material, else [BI]. Only four rows state anything, and 3.1's states that it is itself unverified for EMEA. The [BUSINESS INPUT] tables in each chapter carry frequency and volumes only.
** To-be **: whether a to-be is drafted, and where it is written. ** A to-be is drafted wherever a documented as-is exists and the activity is not Phase 2 and not out of scope. Pending sign-off does not block the to-be ** (decided 15 Sep, superseding "no to-be
until unblocked" in CLAUDE.md line 57); those rows read "yes, on an as-is pending sign-off".
- ** Unblocking question **: the single question whose answer moves the row, ** naming the slide it comes from **. Blank where the row is settled.
## Reason code legend

34

Code | Meaning

35

R1
Flow created and sign off provided by business |
R2
No as-is of its own; covered by other activities in the same Level 2 area |
R3
Out of scope, business confirmed: volume is flowing through EVE currently |
R4
Out of scope, confirmed with business: performed only when there are exceptions |

40

R5
Out of scope for automation: can be taken up by the IT team of today |

41

R6
Phase 2: integration with third-party systems; API access not beneficial from an ROI perspective, business confirmed |

42

R7
Phase 1 for this system or region only; the remaining systems or regions are Phase 2 or pending
R8
Sign off or SOP pending from business. Does not block the to-be

44

R9
Awaiting clarifications from business. Does not block the to-be |

45

R10 | The list the activity depends on has not been provided by business

46
47

R8 and R9 do not block a to-be. R10 blocks only where it removes the as-is entirely (3.12) or the rule the automation would apply (3.15).

48
4g

## Area 1: Confirmation, Contacts & General Type

53
54

| # | Act | Underlying activity, sheet verbatim | Alias | Slides | Sheet status | Scope | Reason | IP | As-is checker drawn | Frequency | To-be | Unblocking question |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- 1 --- 1
1 | 1.1 | 1) Review of Domain matching with counterparty name for contact and confirmation | Activity 1.1 & 1.2 - Domain review & validate relationship | 4, 5, 6, 7 | Flow created, signed off; input described as an email with a link to the webform, comments
Field free text | Phase 1 | R1 | IP1 + IP3 | yes, two Checker boxes | [BI] | yes, group G1 with 1.2 | Slides 4 and 5: is the mandatory entity list (NIP, NFPE, NFRNC, NFPFR, NAIMF) exhaustive, and where is the public-domain rejection list of slide 6 held?|

56

| 2 | 1.2 | 2) Validate the relationship provided for mismatch | Activity 1.1 & 1.2 - Domain review & validate relationship | 4, 5, 6, 7 | as 1.1 | Phase 1 | R1 | IP1 + IP3 | yes, two Checker boxes | [BI] | yes, group G1 with 1.1 | Slide 13: are the five
relationship-justification samples a complete rule set or a sample? Slide 7: does fax remain an in-scope channel, given the note that only the fax tone can be validated? |

57

| 3 | 1.3 | 3) Duplicate check of G-type attribute requested | Activity 1.3- Duplicate Check of G-Type attribute requested | 8 | Flow created, signed off; "Input in the form of email" | Phase 1 | R1 | ** IP2 ** | *$not drawn ** | [BI] | yes, group G2 | Slide 8: who
checks, given no checkpoint is drawn, and what is the exact duplicate-match rule (which fields, what counts as a match)?

58

| 4 | 1.4 | 4) Validate the G-type form & request set up for all components of complex G-type screens (Alt code, sector code, Trading scope etc.) | Activity 1.4,1.5,1.6,1.7- G-Type Attribute Processes | 9 | Flow created, signed off; "Input in the form of
email" | Phase 1 | R1 | ** IP2 ** | yes, three points: regional approval loop, requestor UAT approval, Checker Approval | [BI] | yes, group G3 with 1.5 to 1.7 | Slide 9: which fields are mandatory on the G-type form, and what are the rules for alt code, sector
code and trading scope? Slide 13's TACE table omits codes 13, 15, 16, 20, 21, 24, 25, 30 and 31 |

59

5 | 1.5 | 5) Approval of G-type form | Activity 1.4,1.5,1.6,1.7- G-Type Attribute Processes | 9 | as 1.4 | Phase 1 | R1 | ** IP2 ** | yes, as 1.4 | [BI] | yes, group G3 | As 1.4, slide 9 |
6
1.6 | 6) Set up of Type in UAT | Activity 1.4,1.5,1.6,1.7- G-Type Attribute Processes
9 | as 1.4 | Phase 1 | R1 | ** IP2 **
yes, as 1.4 | [BI] | yes, group G3 | As 1.4, slide 9 |

61

7 | 1.7 | 7) Set up of Type in Prod | Activity 1.4,1.5,1.6,1.7- G-Type Attribute Processes | 9 | as 1.4 | Phase 1 | R1 | ** IP2 ** | yes, as 1.4 | [BI] | yes, group G3 | As 1.4, slide 9

62

| 8 | 1.8 | 8) Unavoidable lower env refresh will retrigger the entire G-type process. | Activity 8: Unavoidable lower env refresh will retrigger the entire G-type process | 10 (upper half) | Flow created, signed off, but can be taken up by the IT team of
today | out of scope | R5 | n/a, triggered by a lower environment refresh | n/a, three linear steps only | [BI] | no, out of scope | Slide 10: which tech team owns the recommendation? The slide asks "has the request being given to IT? / the dept which does
environment refresh"

6

| 9 | 1.9 | 9) Any requester queries related to Confirmation, Contacts & General Type | none | 10 (lower half) | Flow created, signed off, but essentially covered in activities frm 1.1 to 1.7 | covered elsewhere | R2 | n/a | n/a | n/a | no, covered by Gl to G3 |
Slide 10 says "Activity 1 to 8" while the sheet says 1.1 to 1.7. 1.8 is out of scope, so probably immaterial: confirm |

64

| 10 | 1.10 | 10) Setup in Nomura Now and Postedge for NSI | Activity 10: Setup in Nomura Now and Postedge for NSI | 11 (body empty) | Out of scope, third party integration, awaiting business confirmation, will be taken up in phase2 | Phase 2 | R6 | not stated|
n/a, no flow | [BI] | no, Phase 2 | Slide 11 carries only a title, and the sheet says the Phase 2 classification is itself awaiting business confirmation: confirm it, and state what the activity involves

65
66

## Area 2: Organisation Creation and Maintenance

67

68

# | Act | Underlying activity, sheet verbatim
Alias
| Slides
Sheet status | Scope
Reason | IP | As-is checker drawn | Frequency | To-be | Unblocking question |

69

| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- 1 --- 1

70

|11 | 2.1 | 1) Duplicate checks for Org creation | Activity2.1 - Duplicate check for organization creation | 15 | Flow created, signed off | Phase 1 | R1 | not stated | yes,
"4 EYE CHECK", no connector | [BI] | yes | Slide 15: how does the request arrive, the

71

start box states no channel? Which fields does "Validate required fields" cover, and what is the duplicate-match rule?
| 12 | 2.2 | 2) Supporting request outside workflow where requester role are not in EVE workflow | Activity2.2 - Supporting request outside workflow where requester role is not in EVE workflow | 16 | Flow created, signed off | Phase 1 | R1 | IP2 | yes, "4 EYE
CHECK", no connector | [BI] | yes. ** Also carries 3.2 ** as one parameterised configuration, organisation or account ||

72

13 | 2.3 | 3) Adhoc request raised for non-availability of the dedicated workflow
Activity2.3 - Ad hoc request raised for non-availability of the dedicated workflow | 17 | Boilerplate cell, identical to 2.14: covered in remaining activities as specific
queries have not been mentioned/shared | covered elsewhere | R2 | not stated | yes, "4 EYE CHECK", no connector | [BI] | ** no .** Slide 17 (EVE RDM Bulk Loader) recorded as an as-is note in chapter 2 section 2 | Slide 17: which activity does the EVE RDM Bulk
Loader flow belong to, since it appears nowhere else in the deck? Is the 2.3 status cell a copy-paste from 2.14 (slide 30)? Note that ** 3.3 (slide 35) carries the identical sheet name and is a Phase 1 to-be **

73

| 14 | 2.4
not stated
4) NLUX hierarchy set up manual | Activity2.4 - NLUX hierarchy set up manual(New & Amend scenarios). Slide 18 carries the same title plus "(do not refer)" | 19 (slide 18 ignored, ruled 15 Sep) | Signed off (no "flow created" prefix) | Phase 1 | R1 |
yes, "Checker Approval ?" diamond with a Modify details loop, plus "4 EYE CHECK" | [BI] | yes. ** Also carries 3.6 ** as one parameterised configuration | Slide 19: why is the Amend branch drawn as a closure flow, and how does the request arrive? |

74

15 | 2.5 | 5) ALD hierarchy set up manual | not transcribed | 20 | Out of scope, biz confirmed, volume is flowing through EVE currently | out of scope | R3 | n/a
n/a | n/a | no, out of scope | Slide 20 was not transcribed, so the decision rests on the sheet

alone: confirm

75

| 16 | 2.6 | 6) IWM hierarchy set up manual | same | 21 | Flow created, signed off | Phase 1 | R1 | not stated | yes, "4 EYE CHECK" plus "Contact the requester to confirm the fund" | [BI] | yes. ** Also the referent for 3.7 ** | Slide 21: which fields does
"Validate the requester details" cover, where is the "WMD Closure process according to Standard procedure" document, and how does the request arrive? |

76

| 17 | 2.7 EMEA | 7) Org closure process outside EVE. | Activity 2.7 - Org Closure Process outside EVE (EMEA) | 22 | Flow created, sign off provided for EMEA | Phase 1 | R7 | not stated | ** not drawn ** | [BI] | yes, EMEA region sub-section | ** [CONFLICT: 2.7
EMEA, slide 22] ** the slide carries a red "Pending biz confirmation" box while the sheet records EMEA sign off: which is current? And where does the position-found path terminate, since it has no outgoing arrow? |

77

18
2.7 AEJ
7) Org closure process outside EVE. | Activity 2.7 - Org Closure Process outside EVE (Asia) | 23 | SOP pending for AEJ | Phase 1 | R8 | not stated | ** not drawn ** | [BI] | yes, on an as-is pending sign-off, AE] region sub-section | Slide 23:
provide the AEJ SOP. Are slides 22 and 23 two regional variants of one activity? Why does the LVCC alt code path have no incoming arrow? The sheet says AEJ, the slide says Asia: confirm the region label |

78

19 | 2.8 | 8) Org MIFID contact trigger through EMEA | not transcribed | 24 | Out of scope, biz confirmed, volume is flowing through EVE currently | out of scope | R3 | n/a | n/a | n/a | no, out of scope | Slide 24 was not transcribed: confirm |

70

20
2.9 | 9) AGTS creation and maintenance | same | 25 | Flow created, signed off | Phase 1 | R1 | IP3 | yes, "4 EYE CHECK", no connector | [BI] | yes | Slide 25: which activity does "Duplicate Check(from activity1)" refer to, 1.1 (slide 4) or 2.1 (slide 15)?
Is the attribute list seven fields or six, given "Country of Domicile" appears twice in both lists?

80

| 21 | 2.10 | 10) Orgs / Vendor attributes movements | same | 26 | Flow created, sign off pending from business | Phase 1 | R8 | IP3 | ** not drawn ** | [BI] | yes, on an as-is pending sign-off | Slide 26: which conditions route to each of the two unlabelled
branches out of "Input RDM ID in Search Field", and which of create, read, update and delete can arrive, with what field set for each? |

8

| 22 | 2.11 | 11) Override function used for any urgent exception where the Tech failure or Workflow failure or hard restriction. | not transcribed | 27 | Out of scope, confirmed with business, performed only when there are exceptions | out of scope | R4 | n/a |
n/a | n/a | no, out of scope | Slide 27 was not transcribed: confirm |

82

| 23 | 2.12 | 12) Credit Alerts related amendments | same | 28 | Flow created, signed off | Phase 1 | R1 | IP3 | yes, "4 eye", no connector | [BI] | yes. ** Also carries 3.11 ** as one parameterised configuration | Slide 28: are AFFRM, CRED, COMP, RTCP2 and COBLK

the complete flag list, and does the requestor being the ODRG team, an internal team, change the intake? |

83

| 24 | 2.13 | 13) Approval from Legal on attribute change outside of EVE | same | 29 | Flow created, sign off pending from business | Phase 1 | R8 | ** [OPEN: 2.13, slide 29] no channel stated ** | yes, Legal approval, drawn as a box not a decision | [BI] | yes,
on an as-is pending sign-off, Ingestion mode left as a named parameter | Slide 29: how does the attribute change request arrive, since no channel is stated anywhere and must not be assumed? What happens when Legal rejects the ServiceNow ticket, given no
rejection path is drawn? Expand "COD"

84

| 25 | 2.14 | 14) Any requester queries related to orgs | same | 30 | Covered in remaining activities of this L2 activity as specific queries have not been mentioned/shared | covered elsewhere | R2 | n/a | n/a | n/a | no, covered by the other 2.x to-bes | |
| 26 | 2.15 | 15) LEI check for Name | Activity 2.15 - LEI Check for name | 31 | Signed off (no "flow created" prefix) | Phase 1 | R1 | IP3 | ** not drawn ** | [BI] | yes. ** Also carries 3.16 ** as one parameterised configuration | Slide 31: what is the subject of
the unconnected "Need to check business purpose" box, and what does the process do when the GLIEF Portal is unavailable? |

86
87

## Area 3: Account Creation and Maintenance

88
89

# | Act | Underlying activity, sheet verbatim | Alias | Slides | Sheet status | Scope | Reason | IP | As-is checker drawn | Frequency | To-be | Unblocking question |

90

| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- 1

91

27 | 3.1 | 1) Duplicate check for Account Creation | same | 33 | Flow created, signed off | Phase 1 | R1 | IP3 + ** IP4 ** [BI] verify the trigger | yes, "Checker" box, but a terminal with no outgoing arrow
33: what does the Checker do on rejection, since the box has no outgoing arrow? What is the unreadable last line of the green duplicate-entities diamond? Confirm the EVE workflow trigger and the EMEA frequency |
per min (to be checked for EMEA region) | yes | Slide

92

| 28 | 3.2 | 2) Supporting request outside workflow where requester roles are not in EVE workflow | same | 34 | Flow created, sign off pending from business | Phase 1 | R8 | IP2 | yes, "4 EYE CHECK", no connector | [BI] | yes, on an as-is pending sign-off.
** Written at 2.2 (slide 16) ** , one parameterised configuration | Slide 34 asks directly whether the process is the same as the Organisation one: confirm, and provide the sign-off |

93

| 29 | 3.3 | 3) Adhoc request raised for non-availability of the dedicated workflow | same | 35 | Flow created, signed off | Phase 1 | R1 | IP3 | yes, "checker" as plain text on a leader line | rare, monthly 1 or 2 | yes | Slide 35: is the extraction three
fields or four, since the "Extract 4 fields" box and the later blue box disagree? Also ** 2.3 (slide 17) carries the identical sheet name and has no to-be **: confirm the two are different activities

94

| 30 | 3.4 Totoro | 4) FO system manual set up - Global1 / Sphinx / GMI / Venom-Viper / Totoro / Loanet | Activity 3.4 - FO system manual set up- Global1/Falcon/GMI/Venom-Viper/Totoro/Loanet | 36 | FLow created, signed off for Totoro system | Phase 1 | R7 | IP3,
contradicted on the slide | yes, "Checker" box | 2-3 requests multiple RDM ID | yes, Totoro only
Slide 36: does the request arrive by mail (start box) or is the subject line read from EVE (margin note)? Both are on the same slide

95

31 | 3.4 other FO systems | 4) FO system manual set up - Global1 / Sphinx / GMI / Venom-Viper / Totoro / Loanet | as above | 36 | Other systems (Global1 / Sphinx / GMI / Venom-Viper / Loanet) out of scope for phase1, will be considered in phase2 | Phase 2 |
R6, R7 | not stated | n/a, no flow of their own | [BI] | no, Phase 2 | Slide 36: confirm the Phase 2 system list. One row for the group, systems named as on the sheet

96

| 32 | 3.5 | 5) LCM manual set up | not transcribed | 37 | Out of scope, integration with 3rd-party systems (GMI / Consensys / FIA Tech / others), API access not beneficial on ROI, will be taken up in phase2 | Phase 2 | R6 | not stated | n/a | [BI] | no, Phase
2 | Slide 37 was not transcribed: confirm the classification stands |

97

| 33 | 3.6 | 6) NLUX hierarchy set up manual | Activity 3.6 - NLUX hierarchy set up manual(New & Amend scenarios) | 38 | Flow created, awaiting clarifications from business | Phase 1 | R9 | IP2 | partial: a "checker" box is drawn, but a yellow note reads "add
Flows for 4-eye check process" | 5-10 mails per month | yes. ** Written at 2.4 (slide 19) ** , one parameterised configuration | Slide 38: draw the 4-eye check, state where the arrow out of "Ask requestor for details" goes, and say why "Drop a mail internal RDM org
team" is drawn as a decision diamond

98

| 34 | 3.7 | 7) IWM hierarchy set up manual | Activity 3.7 - IWM hierarchy set up manual(same as Org) | 39 (no flow, one line of text) | Flow created and sign off provided by business, but no flow exists on the slide | covered elsewhere | R2 | not stated | n/a |
[BI] | ** no, points to 2.6 (slide 21) ** | Resolved by decision: 3.7 points to 2.6, supported by the identical sheet name and the slide alias "(same as Org)". ** [CONFLICT: 3.7, slide 39, against 2.6, slide 21] retained for the record :** the sheet claims a flow
was created and signed off, and none exists

99

| 35 | 3.8 US | 8) TA closure process outside EVE. | Activity 3.8 - TA closure process outside EVE(US region only) | 40 | Flow created, signed off for US | Phase 1 | R7 | IP3 + ** IP4 ** + KYC team, assumed IP3, both [BI] | yes, "Check Manager Approvals and OBI
report" plus "Approval from FO for each TA" | [BI] | yes, US region sub-section | Slide 40: what is the terminal outcome of the "Status-Restricted" branch, which ends at "No OBI report needed"? Why do "TA inactivation process" and "Closure process" have no
incoming arrow? Which channel does the KYC team use?

100

| 36 | 3.8 EMEA | 8) TA closure process outside EVE. | Activity 3.8 - TA closure process outside EVE(EMEA) | 41 | SOP pending for EMEA | Phase 1 | R8 | IP2 + ** IP4 ** + KYC team, assumed IP3, both [BI] | ** not drawn ** | [BI] | yes, on an as-is pending sign-off,
EMEA region sub-section | Slide 41: provide the EMEA SOP. Why is the LVCC alt code check drawn twice, once unconnected? What condition routes out of "Check for positions", whose one outgoing arrow is unlabelled?

101

| 37 | 3.8 AEJ | 8) TA closure process outside EVE.
Activity 3.8 - TA closure process outside EVE(ASIA) | 42 | SOP pending for AEJ | Phase 1 | R8
IP3 + ** IP4 ** + KYC team, assumed IP3, both [BI] | ** not drawn ** | [BI] | yes, on an as-is pending sign-off, AE]
region sub-section | ** [CONFLICT: 3.8 AE], slide 42, against 3.8 US, slide 40] ** the slide is titled ASIA but the extraction step reads "inactive US trading Accounts": which is correct? Provide the AEJ SOP and the AEJ FO system list, and confirm the region
label, since the sheet says AEJ and the slide says ASIA |

102

38 | 3.9 | 9) Override function used for any urgent exception where the Tech failure or Workflow failure or hard restriction. | not transcribed
43 | Out of scope, confirmed with business, performed only when there are exceptions | out of scope | R4 | n/a | n/

a | n/a | no, out of scope | Slide 43 carries a floating "Review done" box although the activity is out of scope: confirm the decision stands |

103

| 39 | 3.10 | 10) Approvals related to Reparent of TA | same | 44 | Flow has been created and sign off provided by business | Phase 1 | R1 | ** IP4 ** [BI] verify, plus the mail body as a later data source | yes, "Reach out to respective teams for approval(POC
approvals)" plus a "Wait for Approval mail" diamond and an "Account on hold" state | [BI] | yes | Slide 44 carries a reviewer question, "What is automate?": which part of this activity is in scope? Where does the POC approvals spreadsheet live, who maintains it,
and may the automation read it? |

194

| 40 | 3.11 | 11) Credit Alerts related amendments | same | 45 | Sign off provided by business; what are the flag types query pending | Phase 1 | R1 with R10 | IP3 | yes, "checker" box, a terminal with no outgoing arrow | [BI] | yes. ** Written at 2.12 (slide 28)
** , one parameterised configuration | Slide 45: what are the flag types, and is the list the same as slide 28's (AFFRM, CRED, COMP, RTCP2, COBLK)? |

105

41 | 3.12 | 12) Any requester queries related to TA | Activity 3.12 - Any requester queries related to TA (to -work) | 46 (empty) | Queries list pending from business, no flow created | Phase 1 | R10 | not stated | n/a, slide empty | [BI]

** no, no as-is to
draft from. Build blocker ** | Slide 46 is empty: provide the queries list, or declare 3.12 covered elsewhere as 1.9 (slide 10) and 2.14 (slide 30) are. Does the subject-line note on slide 46 belong to 3.12 or is it duplicated from slide 45? |

106

| 42 | 3.13 | 13) Linking alt codes for FO systems e.g. GMI in EVE | not transcribed | 47 | Out of scope, integration with 3rd-party systems, API access not beneficial on ROI, will be taken up in phase2 | Phase 2 | R6 | not stated | n/a
[BI] | no, Phase 2 |

This is the write-side counterpart of the Phase 1 Compare and Match sub-mode (b) linkage read in 2.7 (slides 22, 23) and 3.8 (slides 40 to 42). Confirm that reading FO systems in Phase 1 while writing to them only in Phase 2 is intended

107

| 43 | 3.14 | 14) BPS, Impact, Gloss setup for Firm side for NSI | not transcribed | 48 | Out of scope, integration with 3rd-party systems, API access not beneficial on ROI, will be taken up in phase2 | Phase 2 | R6 | not stated | n/a | [BI] | no, Phase 2|

108

Slide 48 was not transcribed: confirm the classification stands |
| 44 | 3.15 | 15) Updating Class code for PB account(NSI) | Activity 3.15 - Updating class code for PB account(NSI) (slide 49); Activity 3.15 - Updating Class code for PB account (NSI) (slide 50) | 49, 50 | Flow created but sign off pending from business; "input

108

44 | 3.15 | 15) Updating Class code for PB account(NSI) | Activity 3.15 - Updating class code for PB account(NSI) (slide 49); Activity 3.15 - Updating Class code for PB account (NSI) (slide 50) | 49, 50 | Flow created but sign off pending from business; "input
in the form of ?" | Phase 1 | R8 with R10 | ** IP4 ** [BI] verify, plus a client mail carrying PDF, Excel and Word attachments
** not drawn on either slide ** | [BI]
** no to-be until the rule exists .** Both fragments are carried as one as-is in section 2
** BUILD BLOCKER [3.15, slide 50] :** the slide states "Logic For selecting account unknown". Provide the account selection rule. How do slides 49 and 50 connect, given slide 50 has no start box? Who holds the password for the PB sheet marked "(Password Protected)
on slide 49?

199

45 | 3.16 | 16) LEI check for Name | Activity 3.16 - LEI Check for name (Similar as Org Creation and Maintenance) | 51 | Flow created, signed off; "input in the form of ?" | Phase 1 | R1 | IP3 | *$not drawn ** | [BI] | yes. ** Written at 2.15 (slide 31) ** , one
parameterised configuration | Slide 51: what is the subject of the unconnected "Need to check business purpose" box, which also appears on slide 31? |

110

46 | 3.17 | 17) Document validation for Name change, F1SA or if any other provided | same | 52 | Flow created but sign off pending from business; "input in the form of ?" | Phase 1 | R8 | IP3 | yes, "If match, signed and sent to PB", signer not named | [BI] |
yes, on an as-is pending sign-off | Slide 52: who signs the document sent to the PB, and on what authority? What is F1SA? Where is the validated document recorded, given neither branch returns to EVE?

111
112

## Area 4: Commission & Fees

113
114

All nine rows are Phase 2 for the same reason: integration with 3rd-party systems (GMI / Consensys / FIA Tech / others), API access not beneficial from an ROI perspective, confirmed by business, will be taken up in phase2. No slide body was read for any of them,
so no input pattern, no as-is checker and no frequency exists. ** Chapter 4 carries no template sections ** , so no [BUSINESS INPUT] table is raised for these rows.

115
116

** 4.3 and 4.4: the status sheet is authoritative .** The slide titles carry the opposite numbering; reference/flows-area-4.md records that.

117
118

# | Act | Underlying activity, sheet verbatim | Alias | Slides | Sheet status | Scope | Reason | IP | As-is checker drawn | Frequency

To-be
Unblocking question |

119

--- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- 1 --- 1

120

| 47 | 4.1 | 1) Commissions Fails Reports investigation | Activity 4.1 - Commissions Fails Reports investigation | 54 | Out of scope, 3rd-party integration, phase2 | Phase 2 | R6 | not stated | n/a | [BI] | no, Phase 2 | Slide 54: which third-party system does
it depend on? None is named in the activity name

121

48 | 4.2 | 2) Checking Prop and Client Give Up Agreement | Activity 4.2 - Checking Prop and Client Give Up Agreement | 55 | as above
Phase 2 | R6 | not stated | n/a | [BI] | no, Phase 2 | Slide 55: as 4.1 |

122

49 | 4.3 | 3) Client Commission Schedule approval in CAT | slide 57 carries this title numbered 4.4; sheet numbering governs | 57 | as above |
Phase 2 | R6 | not stated | n/a | [BI] | no, Phase 2 | Slide 57: is CAT an internal system or third party? It is not

in the CLAUDE.md internal system list |

123

50 4.4
4) Fee and Commission from the Exchange and Agent Broker | slide 56 carries this title numbered 4.3; sheet numbering governs | 56
as above | Phase 2 | R6 | not stated | n/a | [BI] | no, Phase 2 | Slide 56: as 4.1 |

124

51
4.5 | 5) RDM Account/Book mappings in GMI | Activity 4.5 - RDM Account/Book mappings in GMI | 58 | as above | Phase 2 | R6 | not stated

/a | [BI] | no, Phase 2|

125

52 4.6 | 6) Queries and investigation | Activity 4.6 - Queries and Investigation (en dash and capital I on the slide) | 59 | as above
Phase 2 | R6 | not stated | n/a | [BI] | no, Phase 2 | Slide 59: is 4.6 covered by the other 4.x activities, as 1.9 (slide

10) and 2.14 (slide 30) are for their areas? |

126

53 4.7
7) Rate maintenance for FX products | Activity 4.7 - Rate maintenance for FX products | 60 | as above | Phase 2 | R6 | not stated | n/a | [BI] | no, Phase 2 | Slide 60: as 4.1 |

127

54
4.8
8) Account maintenance in LIMA | Activity 4.8 - Account maintenance in LIMA | 61 | as above | Phase 2
R6 | not stated | n/a | [BI] | no, Phase 2 | |

128

55

4.9

9)

Payables & Receivables report

Activity 4.9 - Payables & Receivables report | 62 | as above | Phase 2 | R

not stated | n/a | [BI] | no, Phase 2 | Slide 62: as 4.1 |

129
130

Slides 63 to 73 are reference material, not as-is flows. Ruled 15 Sep, not transcribed.

131
132
133
13

## Summary

135
136

Scope
Rows | Note |

137

-- / ---
--- |

138

Phase 1, to-be drafted | 24 | 1.1 to 1.7; 2.1, 2.2, 2.4, 2.6, 2.7 EMEA, 2.9, 2.12, 2.15; 3.1, 3.2, 3.3, 3.4 Totoro, 3.6, 3.8 US, 3.10, 3.11, 3.16 |

139

Phase 1, to-be drafted on an as-is pending sign-off | 6 | 2.7 AEJ, 2.10, 2.13, 3.8 EMEA, 3.8 AEJ, 3.17 |

140

Phase 1, covered elsewhere, no to-be | 4 | 1.9, 2.3, 2.14, 3.7 |

141

Phase 1, no to-be: build blocker | 2 | 3.12 (no as-is drawn, slide 46), 3.15 (account selection rule unknown, slide 50) |

142

Phase 2 | 14 | 1.10, 3.4 other FO systems, 3.5, 3.13, 3.14, 4.1 to 4.9 |

143

Out of scope | 5 | 1.8, 2.5, 2.8, 2.11, 3.9 |

144

** Total ** | ** 55 rows, 51 activities ** | |

145
146

** 30 rows carry a to-be .** Because five cross-area pairs are written once as one parameterised configuration (3.2 with 2.2, 3.6 with 2.4, 3.11 with 2.12, 3.16 with 2.15, and 3.7 pointing at 2.6), those rows resolve to *$22 configuration records ** and ** 19 to-be
design units ** drawn from ** 27 as-is units **.

147
148

Reconciliation with log/session-1/partD-scope-register-draft.md, which counts 31 rows with a to-be, 23 configuration records and 20 design units: the difference is 3.15. The draft placed it in the pending sign-off group; this register places it with 3.12 as a
build blocker, because slide 50 states that the rule the automation would apply is unknown. That is the treatment recorded in partE-missing-facts.md and in the 15 Sep decisions. **The two build blockers are the only rows on which the 18 Sep draft cannot deliver a to-be.**

Rows carrying a region or system split, so that a regional answer changes one row and not the activity: 2.7 EMEA, 2.7 AEJ, 3.4 Totoro, 3.4 other FO systems, 3.8 US, 3.8 EMEA, 3.8 AEJ. The SPOC columns on the status sheet are not split by region, so the owner of the EMEA and AEJ answers is not yet recorded.
