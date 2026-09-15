Three things before the skeleton.

1. Catalogue taxonomy. The capability catalogue uses the nine platform skills defined in reference/platform-skills.md, not U1 to U6. Rewrite log/session-1/partC-utility-validation.md so every finding, evidence table and candidate is regrouped under the nine skills, following the mapping table in that file, keeping the U-number in brackets for traceability only. Mark Unstructured to Structured and Compare and Match as registered utilities reused from the SSG BRD. Keep the per-activity evidence intact.

2. Part E reclassification. Under the to-be rule, an activity with a drawn as-is gets a to-be; missing rule content becomes a named configurable check in the chapter with "content: to be supplied by <owner>" plus a section 10 open point. Re-tag every [BLOCKER] in partE-missing-facts.md as [SECTION 10], except where no to-be can exist at all: 3.15 (account selection rule) and 3.12 (no flow). Items 56, 60 and 61: the AI Governance Standard, NTI process, ORMF and the governance deck are now in reference/; mark them "source in reference/, to be read in the front section and chapter sessions".

3. Two design decisions, log them:
- Webform (IP1): as-is is a manual click-through from the email link; the to-be reads the form via API under Ingestion. Prerequisite: API availability confirmed by the EVE / webform owners. Chapter 1 writes the to-be this way with the prerequisite in section 9.
- Duplicate check (1.3, 2.1, 3.1, 2.9): designed as tiered, exact rules first then a fuzzy tier, same shape as the SSG matcher, so AI is in the path with human confirmation. The fuzzy tier is removed if the business rule proves deterministic.

Log all three as a dated entry. Do not print file contents. Then stop.
