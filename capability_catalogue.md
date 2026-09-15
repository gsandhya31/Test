**Open points.**
- **[OPEN: 2.9 slide 25, 2.10 slide 26, 2.12 slide 28, 2.15 slide 31, 3.1 slide 33, 3.4 Totoro slide 36, 3.8 US slide 40, 3.8 AEJ slide 42, 3.11 slide 45, 3.16 slide 51, 3.17 slide 52]** the output field schema is not stated. Schemas that are stated: 2.9 slide 25 seven attributes, though "Country of Domicile" is listed twice so the real count may be six; 2.13 slide 29 eight fields; 3.10 slide 44 four fields; 3.3 slide 35 three or four.
- **[CONFLICT: 3.3, slide 35]** the "Extract 4 fields" box names four fields while the later blue box on the same slide lists three, with the alt code added at a separate step. The one well specified extraction in the deck is internally inconsistent.
- **An IP4 request arrives with structured fields already**, so free-text extraction is not needed on its EVE path. The same configuration therefore needs free-text extraction for its email path and an EVE read under Ingestion for its EVE path: exactly the case for 3.1 (slide 33) and 3.8 (slides 40, 41, 42).


**Open points.**
- **[OPEN: 1.4 slide 9, 2.7 EMEA slide 22, 2.7 AEJ slide 23, 3.3 slide 35, 3.4 Totoro slide 36, 3.8 EMEA slide 41, 3.8 AEJ slide 42, and 3.13 slide 47 as the Phase 2 owner]** the alt code is the single most frequently derived value in the deck, appearing in seven of these nine units, and it is defined nowhere. What an alt code is, where the authoritative mapping lives, and what LVCC denotes are not stated in reference/. 3.13, "13) Linking alt codes for FO systems e.g. GMI in EVE", is the Phase 2 activity that owns the mapping, so the definition may surface only in Phase 2 work.
- **[OPEN: 1.4, slide 9, with the table on slide 13]** whether the TACE sector codes table is complete. Codes 13, 15, 16, 20, 21, 24, 25, 30 and 31 are not listed on it.


**Open points.**
- **[OPEN: 2.1 slide 15, 2.6 slide 21, 1.3 slide 8, 1.4 slide 9, 2.9 slide 25, 3.1 slide 33, 3.6 slide 38]** rule content for the tier B checks, per the table above.
- **[OPEN: 1.1 and 1.2, slides 4 to 7]** whether the tier A lists are complete: the mandatory entity list, and the public-domain rejection list, which the slide itself leaves open-ended ("and other public email domains").
- **[OPEN: 2.12 slide 28, 3.11 slide 45]** whether AFFRM, CRED, COMP, RTCP2 and COBLK are the complete flag list. This is the only permitted-value list outside area 1, it is drawn on slide 28 only, and 3.11's sheet cell records the flag types as an open query.
- **[OPEN: G3 {1.4 to 1.7} slide 9, 2.13 slide 29, 3.10 slide 44]** three units carry multi-party approval rather than a single checker. The routing of those approvals is Route and Distribute; the pending state while they are outstanding is Monitor and Control.
- **[OPEN: 2.13 slide 29, 3.1 slide 33, 3.11 slide 45, and 15 of the 18 drawn checkpoints]** what a rejection does. Fifteen of the eighteen checker steps have no rejection path drawn, and several are terminals with no outgoing arrow (3.1 slide 33, 3.11 slide 45). Only 2.4 slide 19 draws reject and loop back. **The to-be supplies a rejection path everywhere and states it as an addition to the as-is.**


**Open points.**
- **[OPEN: all Phase 1 activities, slides 4 to 52]** how writes are executed, per system: API or screen automation. Nothing in reference/ states this for any system, and it is the single answer that sizes every to-be.
- **[OPEN: 2.7 EMEA slide 22, 2.7 AEJ slide 23, 3.8 US slide 40, 3.8 EMEA slide 41, 3.8 AEJ slide 42]** rollback when a write half-completes. No flow draws it, and the closure flows are where it matters most.
- **[OPEN: all Phase 1 activities, slides 4 to 52]** confirmation that writes run on the analyst's own credentials, as the skill definition and the design principles state. It is a control statement carried from the definition, not evidenced in the CSG flows, and it determines what the audit trail shows and who is accountable for a write.
- **[OPEN: 2.3, slide 17]** the EVE RDM Bulk Loader would be a mode of this skill if slide 17 turns out to belong to an activity that carries a to-be. Held; 2.3 is covered elsewhere with no to-be, and slide 17 is retained as an as-is note in chapter 2 section 2.


**Open points.**
- **[OPEN: 2.6 slide 21, 2.9 slide 25, 2.10 slide 26, 2.13 slide 29, 3.1 slide 33, 3.3 slide 35, 3.4 Totoro slide 36, 3.6 slide 38, 3.11 slide 45, 3.17 slide 52]** the pending state. Ten flows know they need to ask a question; three know what happens next. Without a pending state a queried request is lost from the automation. **This is the single most repeated structural defect in the as-is material.** The to-be supplies a held state in all 22 configurations.
- **[OPEN: all Phase 1 activities, slides 4 to 52]** no flow anywhere states an SLA, an ageing threshold or a chase interval. Not one.
- **[OPEN: all Phase 1 activities, slides 4 to 52]** the audit trail. Nothing in the CSG flows describes one; the requirement comes from the skill definition and the control expectation. See chapter section 7 in each chapter.


**Open points.**
- **[OPEN: 2.7 slides 22 and 23, 3.8 slides 40, 41 and 42]** whether TDG1001568 covers the many-system read shape of sub-mode (b), or whether it is a CSG extension. This changes the governance route, so it is a question for the utility owners with an SG decision attached.
- **[OPEN: 2.7 slides 22 and 23, 3.8 slides 40, 41 and 42, 3.4 Totoro slide 36, 3.13 slide 47]** the front-office system read list per region. Three closure flows name three different lists, and sub-mode (b) cannot be configured per region without it.
- **[OPEN: 2.7 slides 22 and 23, 3.8 slides 40 to 42, 3.4 slide 36, 3.13 slide 47]** sub-mode (b) requires Phase 1 **read** access to systems whose **write** automation is Phase 2 or out of scope (GMI, Venom-Viper, Loanet, and Global1 / Sphinx via 3.4). The activity list supports the split, since 3.13 is the Phase 2 write-side counterpart of the same linkage domain, but the position is nowhere stated as a decision.


**Open points.**
- **[OPEN: 2.6 slide 21, 2.9 slide 25, 2.10 slide 26, 2.13 slide 29, 3.1 slide 33, 3.3 slide 35, 3.4 Totoro slide 36, 3.6 slide 38, 3.11 slide 45, 3.17 slide 52]** the query wording for areas 2 and 3 does not exist. Area 1's standard format (slide 12) is the template.
- **[OPEN: 1.1 and 1.2, slide 13]** whether the five relationship-justification samples are a complete rule set or a sample set. They read as samples.
- **[OPEN: all Phase 1 activities, slides 4 to 52]** whether confirmation mails, Outlook tags and notifications exist in EDM at all. Those modes come from the SSG usage and have no CSG evidence. Either EDM does not send confirmations, or the flows do not draw them; the second is more likely and should be asked rather than assumed.
- **[OPEN: 3.17, slide 52]** 3.17's outbound goes to the client and carries a signed document. Who signs, on what authority, and what record is kept is a control question, recorded in that chapter's section 7, not a capability question.
- 2.13 (slide 29) sends into ServiceNow rather than to a person, i.e. the outbound target is a system queue. The only instance, and it overlaps Route and Distribute.


**Open points.**
- **[OPEN: 2.7 slides 22 and 23, 3.8 slides 40, 41 and 42]** how the region of an incoming request is determined. Region routing is the most-used mode, five of the eight units, and no unit states the rule. The region sub-sections in each chapter's sections 2 and 5 will have to state a rule the as-is does not give.
- **[CONFLICT: 2.7 AEJ, slide 23, and 3.8 AEJ, slide 42, against the status sheet]** the region labels disagree: the sheet says AEJ, the slides say Asia and ASIA.
- **[OPEN: all Phase 1 activities, slides 4 to 52]** analyst assignment is not drawn anywhere in the CSG deck. Whether EDM assigns work to a named analyst at all, and on what basis, is not stated. It matters because the maker in maker-checker has to be somebody.
- **[OPEN: 2.13 slide 29, 3.10 slide 44, 3.8 US slide 40]** three of the eight route outside EDM (Legal, POC, FO) and none of the three draws what happens on rejection or on no reply. This is the pending-state gap seen from the routing side.
- **[OPEN: 3.10, slide 44]** where the POC approvals spreadsheet lives, who maintains it, and whether the automation may read it. Route and Distribute cannot be configured for 3.10 without it.
- **[BUSINESS INPUT: 3.8, slides 40, 41 and 42]** the KYC team is a request source rather than a routing target, and its channel is assumed IP3.


## Coverage: what fits no skill

**A flow exists and still fits no skill: 1.8, slide 10, only.** Its three linear steps (an environment refresh happens, refresh the data, confirm) involve no request, no extraction, no derivation, no check, no comparison, no query, no routing and no approval. Consistent with its out-of-scope classification and with the sheet's note that the IT team of today can take it up. **1.8 is the one activity in the deck the taxonomy does not reach, and it is already out of scope. Coverage of in-scope work is complete at the skill level.**

**No flow, so no skill can be assigned:** 1.9 slide 10, 2.3 slide 17, 2.14 slide 30, 3.7 slide 39 (covered elsewhere with no to-be, so this is expected); 3.12 slide 46 (no as-is drawn and no covered-elsewhere pointer, the one activity in that position); 1.10 slide 11, 3.5 slide 37, 3.13 slide 47, 3.14 slide 48 and 4.1 to 4.9 slides 54 to 62 (Phase 2).

**Partially fits: 3.15, slide 50, read in isolation.** Read together with slide 49 it uses Ingestion (EVE read), Unstructured to Structured (attachments) and Compare and Match sub-mode (a). Read alone it cannot be mapped, because its own dark red box states "Logic For selecting account unknown", and that rule is the missing piece. **Build blocker: 3.15 is the one activity with a drawn as-is where no to-be can be written.**

**One step type maps to no skill:** the correlation of a later email to an already-open EVE item (3.10 slide 44, 3.15 slides 49 and 50). It is closest to Ingestion and is recorded there, but it is drawn nowhere and no skill definition mentions it.

## No tenth skill is proposed

Five of the six candidates raised in Session 1 are absorbed by the nine.

| Candidate | Disposition |
|---|---|
| System write execution | **Absorbed: Calculate and Process.** The taxonomy already has it |
| Approval orchestration with a pending state | **Absorbed, split two ways:** the approval is Validate and Approve, the pending state and chasing are Monitor and Control. The composite is exactly what 10 units are missing |
| Cross-system position and linkage check | **Absorbed: Compare and Match sub-mode (b)** |
| Uncontrolled external reference lookup | **Absorbed: Compare and Match sub-mode (a)**, with the external-dependency note attached. Not a capability |
| Document extraction and outbound signing | **Split.** Inbound half is Unstructured to Structured, a configuration question for TDG1001567. Outbound signing is a control question: who signs 3.17's document (slide 52) and on what authority |
| Bulk and batch load | **Not admitted.** Its only evidence was slide 17 (EVE RDM Bulk Loader), which has no to-be. If 2.3's disposition changes, it becomes a mode of Calculate and Process, not a capability |

**Two naming questions, neither of which adds a skill.**
1. **[OPEN: all Phase 1 activities, slides 4 to 52]** whether "query and follow-up" is named as its own capability, as reference/platform-skills.md raises. On the CSG evidence the two halves are always drawn together and always fail together: of the 13 units that draw a query, 10 draw the send with no track. **Recommendation: name it as a composite pattern spanning Report and Notify and Monitor and Control, not as a tenth skill**, so the nine stay stable and the most common defect in the as-is material still gets a name. SG decision.
2. **[OPEN: 3.10 slide 44, 3.15 slides 49 and 50]** where the EVE-to-email correlation step belongs. Recorded under Ingestion for now.

## Input patterns, and what they require of the catalogue

**IP1** email with a link to a webform or screen (structured fields plus a free-text comments field); **IP2** email with an Excel attachment; **IP3** free-text email; **IP4** the request originates as an EVE workflow item or EVERequest with no email, and supporting detail may arrive separately by email.

The design principle reads **"automation starts at request receipt (email or EVE work item)"**. Work performed by the requestor before receipt is out of scope.

Two consequences for the configuration record, both of which change the wizard schema:

1. **Some units carry more than one input pattern, so the pattern field must accept a list.** 3.1 (slide 33) is IP3 and IP4; 3.8 (slides 40, 41, 42) is IP2 or IP3, plus IP4, plus the KYC-team source; G1 {1.1, 1.2} (slides 4 to 7) is IP1 and IP3. Each pattern needs its own Ingestion mode and its own extraction path inside the same configuration record.
2. **The source field must accept an EVE queue, not only a mailbox.**

