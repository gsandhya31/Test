# BRD decisions (append-only journal)

Rule for this file only: never rewrite or delete earlier entries. Append new entries at the bottom with the date. If a decision changes, add a new entry that says "supersedes <date> entry". The BRD files in brd/ are edited freely; this journal is the trail of why.

## 2026-09-14  Pre-session decisions (agreed before Claude Code work started)
- Structure: one BRD; front section, capability catalogue, one chapter per Level 2 area (4 chapters), scope register annex.
- Chapters are per Level 2 area, not per underlying activity.
- Front section is drafted after chapters 1 and 2.
- Capability catalogue: hypothesis in Session 1 (U1 to U6 in CLAUDE.md), corrected per chapter, rewritten clean in Phase 3.
- To-be flows only where a documented as-is exists and the activity is in Phase 1 scope.
- Every to-be written in the wizard configuration shape (intake, extraction, checks, decision points, outputs) so each activity maps to one wizard configuration on the target platform.
- Input format, HITL and frequency come from the flow slides; where absent, the chapter carries a "Business to populate" table tagged [BUSINESS INPUT]. No older tracker is kept.
- Third-party system activities (GMI/Consensys, FIA Tech, LIMA, Nomura Now, Postedge, FO systems except Totoro) are out of scope for Phase 1, listed as Phase 2 candidates. Reason: API access not beneficial from an ROI perspective (business confirmed).
- 1.9, 2.3, 2.14 are covered by other activities; no separate as-is or to-be.
- 3.4 is split: Totoro Phase 1, other FO systems Phase 2.
- 2.11, 3.9 (override) out of scope; 2.5, 2.8 out of scope (volume flows through EVE); business confirmed.
- 1.8 (pre-refresh backup) is an IT action, out of scope for automation, to be recommended to the owning tech team.
- Intake stays as today: P1 email + linked webform (structured fields + free-text comments; confirmed for 1.1, 1.2), P2 email + Excel attachment, P3 free-text email. "Re-engineer as request workflow" retired.
- Prerequisite: confirm whether P1 form data is reachable via API/query or screen only.
- Source of truth: edm-activities-status.xlsx for scope/status; flow material for as-is steps, input format, HITL, volumes.
- Model policy: Opus for judgement steps, Sonnet for mechanical steps, USD 50 daily cap, work spread over 2 to 3 days.

## Open points
- P1 form data access: API/query vs screen only.
- Intake pattern for 1.3 to 1.7 ("input in the form of email": P2 or P3?) and for 3.15 to 3.17 ("input in the form of ?").
- Rows with sign off pending or SOP pending: 2.7 (AEJ), 2.10, 2.13, 3.2, 3.6, 3.8 (EMEA, AEJ), 3.11 (flag types query), 3.12 (queries list), 3.15, 3.17.
