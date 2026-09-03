Yes — write-back and email drafting slot naturally after validation, and the behaviour should differ by outcome: matched cases can write back to PCM straight-through (with sampling-based review), partial matches write back a partial status and generate a draft discrepancy email for HITL approval before sending, and unmatched cases raise an exception with a draft chaser/investigation email routed through HITL. I've built that into the flow description below.

Here's the revised write-up with all your corrections:

---

**AI-Assisted Non-STP Processing — Pilot Evaluation: ServiceNow Track vs Internal Tools Track**

**Background**

Two parallel pilots were run to evaluate delivery approaches for the AI-assisted non-STP flow solution: email ingestion → classification → extraction → validation against cashflow data → write-back to PCM and outcome-based email drafting (matched / partial match / unmatched) → routing with human-in-the-loop review.

- **Track 1 (ServiceNow):** Built on a SNOW evaluation instance using mock email data and mock cashflow data. The workflow, including the HITL review component, was custom-developed on the platform; LLM calls were made via the Now Assist feature using the in-house Chinou API.
- **Track 2 (Internal Tools):** Built on internal infrastructure with actual mailbox integration (mock email content) and live integration to the test cashflow system.

**Track 1: ServiceNow — Pros**

- Proven integration precedent: the existing production SNOW implementation already has established mailbox integrations, access to trade data, and two-way counterparty email flows (outbound and reply capture). The integration patterns needed for this solution exist in production today, materially reducing delivery risk despite the pilot running on mock data.
- Bank-approved LLM proven on-platform: the pilot demonstrated 100% custom development of extraction and prompt/agent logic, with LLM calls routed through Now Assist to the in-house Chinou API — flexibility on model choice is not a constraint.
- Platform-native capabilities: audit trails, RBAC, change management, queue/case structures, and dashboards align with existing firm governance and SNOW operating experience.
- Data posture already accepted: since the prod instance already handles trade data and counterparty correspondence, the incremental info-sec review burden is limited.

**Track 1: ServiceNow — Cons**

- Now Assist licensing is an open commercial question: the team is evaluating whether the platform can be built without a Now Assist license; until resolved, cost at scale is uncertain.
- Custom-heavy build: because the HITL workflow and extraction logic were custom-developed rather than configured, the maintenance profile is closer to an internal build — the "config over code" advantage of a platform approach is reduced.
- Data fidelity gap: both email content and cashflow data were mocked, so end-to-end behaviour against real-format data (edge cases, malformed emails, cashflow data quirks) is untested.
- Eval-to-prod migration: the pilot ran on an evaluation instance; effort to port and harden on the firm's production instance needs sizing, even with integration patterns already proven there.
- Platform dependency: upgrades, platform release cycles, and any Now Assist architectural coupling create a dependency on the vendor roadmap.

**Track 2: Internal Tools — Pros**

- High integration fidelity: actual mailbox integration and live connectivity to the test cashflow system were proven — auth, entitlements, network access, and system APIs were exercised, not simulated.
- Full architectural control: model choice, prompt/agent design, extraction logic, memory, and future learning capabilities are unconstrained by any platform.
- No platform licensing exposure; cost is internal engineering capacity, and data remains fully within the bank's environment.
- Naturally extensible to the broader non-STP vision, where inputs, extraction fields, and target systems vary by ops team.

**Track 2: Internal Tools — Cons**

- Build-and-run burden: case management UI, audit trail, access controls, dashboards, and workflow routing must all be built and maintained internally — capabilities the SNOW platform provides natively.
- Slower horizontal scaling: each new team onboarding or feature is an engineering effort.
- Ownership and support model need definition — production support, on-call, and enhancement capacity beyond the pilot team.
- Full governance burden in-house: model risk documentation, testing evidence, and control attestations must be produced by the team.

**Key Observation**

The pilots retired different risks. The internal track proved *live system integration* (mailbox + test cashflow system); the SNOW track proved *custom AI development on the platform with the in-house Chinou API*, while leaning on production-proven integration patterns rather than testing them directly. The main open items are the Now Assist licensing question on the SNOW side and the build/ownership cost on the internal side.

**Suggested Next Steps**

- SNOW track: conclude the Now Assist licensing evaluation (including the no-license architecture option); run a follow-up test with real-format email and cashflow data; size the eval-to-prod migration.
- Internal track: size the effort to build production-grade case management, audit, and access controls; define the long-term ownership and support model.
- Both tracks: validate the write-back to PCM and outcome-based email drafting (matched / partial / unmatched) with HITL approval gates before counterparty sends.

---

One thing I'd flag: the "custom-heavy build" con for SNOW is the honest counterweight to your corrections — since HITL and extraction were custom dev, the maintenance argument between the two tracks narrows considerably, and the real differentiators become licensing cost vs build cost, and prod integration precedent vs proven test integration. If that framing is too sharp for your audience, I can soften it.

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
