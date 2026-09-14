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
- Input stays as today. Input patterns: IP1 email + linked webform (structured fields + free-text comments), IP2 email + Excel attachment, IP3 free-text email. An activity can carry more than one pattern, tagged per channel. "Re-engineer as request workflow" retired.
- Prerequisite: confirm whether IP1 form data is reachable via API/query or screen only.
- Source of truth: edm-activities-status.xlsx for scope/status until Session 1, then brd/annex-scope-register.md; flow material for as-is steps, input format, HITL, volumes.
- Model policy: Opus for judgement steps, Sonnet for mechanical steps, USD 50 daily cap, work spread over 2 to 3 days.

## 2026-09-15  Status changes from business update email
- 1.10 confirmed Phase 2 (third-party integration). Supersedes the 14 Sep open point.
- Input format for 3.15, 3.16, 3.17 no longer an open point.
- 3.11 signed off; flag types query still pending with business.
- 3.12 remains pending: queries list awaited from business.
- Update email sent to Hemant and Mayur on 15 Sep; draft BRD committed for 18 Sep.
- Phase 1 count: 33 activities (24 signed off incl. 1.9, 2.3, 2.14 covered elsewhere; 2 signed off for one region; 7 pending). Phase 2: 13. Out of scope: 5.

## 2026-09-15  Terminology
- "Input pattern" replaces "intake pattern". Labels IP1 / IP2 / IP3 replace P1 / P2 / P3 to avoid confusion with Phase 1 / Phase 2.

## Open points (as at 15 Sep, before Session 0 entries below)
- IP1 form data access: API/query vs screen only.
- Input pattern for 1.3 to 1.7 ("input in the form of email": IP2 or IP3?).
- Rows with sign off pending or SOP pending: 2.7 (AEJ), 2.10, 2.13, 3.2, 3.6, 3.8 (EMEA, AEJ), 3.11 (flag types query), 3.12 (queries list), 3.15, 3.17.

## >>> PASTE HERE the Session 0 entry that Claude Code appended to your current decisions file, then delete this line <<<
