That's a strong third option, and often what these evaluations land on. Here's a section you can add before Key Observation:

---

**Hybrid Option: Combining Proven Components from Both Tracks**

Rather than selecting one track wholesale, the end solution can assemble the strongest proven component from each:

- **Ingestion layer from the internal track:** the mailbox integration is already built and proven against a live mailbox. This becomes the ingestion service, normalising inbound emails and handing them off to the downstream pipeline.
- **Workflow and case layer on SNOW:** classification, extraction (custom dev with Chinou API via Now Assist, as proven in the pilot), validation, HITL review queues, write-back to PCM, and outcome-based email drafting run on the platform, leveraging its native audit, RBAC, queue management, and the production-proven trade data and counterparty email integrations.

This split plays to each track's demonstrated strength: the internal track de-risked ingestion; the SNOW track de-risked AI processing on the platform.

**Considerations for the hybrid approach:**

- An interface contract is needed between the internal ingestion service and SNOW (e.g., normalised email payload with attachments and metadata pushed via API into a SNOW intake table). This handoff was not tested in either pilot and should be prototyped early.
- Ownership splits across two teams and two stacks; support model, change coordination, and incident routing across the boundary need defining.
- Duplication check: if the production SNOW instance's existing mailbox integration can serve this use case directly, the internal ingestion component may be redundant — worth confirming whether the prod integration covers the target mailboxes and formats before committing to the hybrid.
- The Now Assist licensing question applies to the hybrid equally, since the AI processing layer remains on SNOW.

---

The third bullet is the one to resolve first: the hybrid only earns its complexity if SNOW's existing prod mailbox integration *cannot* be reused for these mailboxes (different mailbox estate, format handling, attachment processing, or entitlement constraints). If it can, the simpler answer is all-SNOW; if it can't, the hybrid is well justified. Do you know yet whether the prod SNOW integration covers the mailboxes this solution needs?
