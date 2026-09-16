The previous session was cut off part-way through applying the message below. First check which of its items are already in decisions/brd-decisions.md, brd/annex-scope-register.md and brd/01-capability-catalogue.md; apply only what is missing; then tell me what you found done and what you completed.

Log these as a dated entry, then apply the file changes listed at the end.

Decisions
- Supersedes yesterday's row 42 entry: Phase 1 write scope is EVE and Totoro only. For the closure flows (2.7, 3.8) the position and LVCC alt-code check against GMI, Venom-Viper, Loanet, Global1, Euclid and Nuvo stays a manual analyst step in Phase 1, presented as a HITL checkpoint with the result recorded; automating that read is Phase 2, with 3.13. Compare and Match sub-mode (b) in Phase 1 reads EVE and Totoro only.
- NTIs: TDG1001568 is extended to cover Compare and Match sub-mode (b). New NTIs are raised for each of the other seven skills the CSG to-bes use. The front section carries an NTI plan table (skill, existing NTI or new NTI).
- Every skill with more than one behaviour has named sub-modes in the catalogue, and to-be steps tag at sub-mode level, e.g. "Validate and Approve (a)". The uses / extends / new check in each chapter runs per sub-mode. A to-be may use one sub-mode of a skill and not the others.
- "Query and follow-up" is a composite pattern spanning Report and Notify and Monitor and Control, not a tenth skill.
- The email-to-EVE correlation step belongs under Ingestion.
- Standing rule: the to-be supplies a rejection path and a pending state in every configuration, stated as an addition to the as-is. Not an open point.
- Standing rule: writes execute on the analyst's own credentials; restated as a control requirement in every chapter section 7.
- Draft v0.1 assumptions, verified later and listed in the front section: one mailbox (RDM-ORGS2) for all areas; writes via API where available, otherwise screen automation, per-system confirmation as a section 9 prerequisite owned by IT; IP4 intake mechanism as a section 9 prerequisite owned by IT/EVE.
- Missing rule content, schemas, lists, wording and routing rules are configurable content, written as "content: to be supplied by <owner>", never open points that block a to-be.
- Count reconciliation, corrected: "33 Phase 1 activities = 28 with a drawn flow + 4 covered elsewhere (1.9, 2.3, 2.14, 3.7) + 1 with no flow (3.12). The 28 with a flow form 27 as-is units: 4 merge into shared flows (1.2 into 1.1; 1.5 to 1.7 into 1.4) and 3 are added by regional splits (2.7 x2, 3.8 x3)."

File changes
- brd/annex-scope-register.md: row 42 question replaced by "Phase 1: manual analyst check; automated in Phase 2 with 3.13". Rows 20 and 29: restore the unresolved sub-questions (2.9 six vs seven attributes; 3.3 three vs four fields). Replace the reconciliation line with the corrected one above.
- brd/01-capability-catalogue.md: replace the stale FO-systems passage with the Phase 1 position above; add sub-modes to every skill that has more than one behaviour; remove open points now decided or ruled as standing rules; keep the rest. Replace the reconciliation line with the corrected one above.
Do not print file contents.
