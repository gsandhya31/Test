 Two consequences you have to rule on, because both contradict rules currently locked in CLAUDE.md:

  (i) Credentials. The locked rule is "all writes execute on the analyst's own credentials". With code as maker that cannot hold: the maker write has no human behind it. The honest split is the maker write on
  a named automation identity (a service account under change control) and the finalising approval on the human checker's own credentials. If instead the maker write ran on the checker's credentials, the same
  person would enter and approve, which collapses segregation of duties (the control that the person who does the work is not the person who signs it off). So the rule needs restating, not just relabelling.

  (ii) A prerequisite that did not exist before. The pattern depends on each target system having a pending / unapproved state for the code to write into. EVE workflow has one. Totoro is unconfirmed. Where no
  pending state exists the change has to be staged outside the system and the comparison table built from the staged payload, which is a different build. This joins the existing per-system write-mechanism
  prerequisite, owned by IT.

  And one new open point, which is the only thing here that can stop the design: whether ORM and the AI Governance Standard accept automation as the maker with a single human checker, i.e. whether "four eyes"
  is satisfied by code plus one human. That needs the AI Business Owner (Article 2-1, still unnamed) and ORM, and it belongs in section 9 and section 10 of every chapter rather than buried in the catalogue.

  Where the change lands:

  ┌────────────────────────────────┬──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┐
  │              File              │                                                                               What changes                                                                               │
  ├────────────────────────────────┼──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┤
  │ decisions/brd-decisions.md     │ New dated entry. Supersedes the 15 Sep two-human model and the "writes on the analyst's own credentials" standing rule. Closes the catalogue's open point "the maker in  │
  │                                │ maker-checker has to be somebody": the maker is the code                                                                                                                 │
  ├────────────────────────────────┼──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┤
  │ CLAUDE.md                      │ Four places: design principles (add "the automation is the maker; the single human decision point is the checker"); the credentials rule; the Validate and Approve       │
  │                                │ catalogue bullet ("maker confirmation, checker, ..."); the sub-mode bullet, where (b) becomes one checker approval                                                       │
  ├────────────────────────────────┼──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┤
  │                                │ Seven places: the preamble sentence on line 9; the Validate and Approve row of the usage summary; skill 4, both the "maker-checker is a control pattern inside this      │
  │ brd/01-capability-catalogue.md │ skill" framing and the whole (b) approval half; skill 5 ("always after human approval", plus the closing standing rule); skill 7, where the manual front-office check    │
  │                                │ becomes the checker's checkpoint; skill 9 ("hand-off to the checker", plus the now-closed open point); the approval-orchestration row of the "no tenth skill" table      │
  ├────────────────────────────────┼──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┤
  │ brd/annex-scope-register.md    │ The "As-is checker drawn" column meaning: "the to-be carries a human decision point regardless" becomes "the to-be carries one human decision point, the checker; the    │
  │                                │ maker is the automation"                                                                                                                                                 │
  ├────────────────────────────────┼──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┤
  │ brd/00-front-section.md        │ Empty, so this becomes a drafting rule for sections 5, 7, 9 and 10: the control story, the NTI and ORMF mapping, the ORM acceptance dependency                           │
  ├────────────────────────────────┼──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┤
  │ brd/ch-01 to ch-03             │ Empty, so a drafting rule for sections 5, 6, 7 and 9: one decision point per configuration, FRs written to it, section 7 maker-checker mapping, section 9 the two items  │
  │                                │ above                                                                                                                                                                    │
  ├────────────────────────────────┼──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┤
  │ brd/solution-overview.html     │ One HUMAN DECIDES box, plus your points 2 and 4                                                                                                                          │
  ├────────────────────────────────┼──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┤
  │ log/                           │ Dated session entry                                                                                                                                                      │
  └────────────────────────────────┴──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┘

  Confirm (i), the credentials split, and I will apply this in the CLAUDE.md-mandated order: decisions journal first, then CLAUDE.md, then the catalogue, then the register, then the HTML.
