Parameter	Track 1 — ServiceNow	Track 2 — Internal Tools	Internal assessment
Build type	Custom-developed on platform (workflow, HITL, extraction, prompt/agent logic); config-over-code advantage reduced, though SNOW marketplace functionality can be leveraged to accelerate build	Fully bespoke build on internal infrastructure; complete architectural control	Service Now
Input formats supported	Mock email + mock cashflow data only; real-format edge cases (malformed emails, cashflow quirks) untested	Actual mailbox content ingested; PDF, Excel, and image formats supported	Internal
Connectivity with Outlook	Prod SNOW instance integrates with the target mailbox via Exchange services; two-way counterparty email flows in place; pilot itself ran on mock mailbox	Outlook integration via Graph API — actual mailbox integration proven (auth, entitlements, network access exercised, not simulated)	Internal
Connectivity with target system (read & write-back)	Prod instance already accesses trade data(PCM); but not tested on real data in pilot	Live connectivity to test cashflow system proven, including PCM write-back already validated against that connectivity	Internal
POC	Ran on eval instance	Ran on internal infra with live test-system integration; production-grade case mgmt still to build	Internal
NTI	In progress	In progress	NA
Underlying LLM	Chinou LLM (via Now Assist) — same model as internal track	Chinou LLM — same model as SNOW track	NA
AI tokens / cost optimization	Token cost via Now Assist / Chinou routing; optimization levers may be tied to platform	Direct control over token usage, batching, caching, model selection	Service Now
Cost — licensing	Firm-wide Now Assist license available from Mar 2026 onwards	No platform licensing exposure	Internal 
Cost — resourcing	Can be staffed with SABRE, Protiviti, and IT resources	Can be staffed with SABRE, Protiviti, and IT resources	Service Now
Platform availability	No downtime observed historically on the SNOW platform	Downtime profile unknown — no availability track record yet	Service Now
Auditability	Out-of-the-box audit feature on the platform	Must be built from the ground up internally	Service Now
LangSmith integration (observability)	Integration being done on the SNOW track	Not present on the internal track	Service Now
Time to market	Faster where prod integration patterns are reused; licensing available from Mar 2026	Slower horizontal scaling — each new team/feature is an engineering effort	Service Now
Skillset	SNOW platform + Now Assist + Chinou API integration skills	Full-stack internal engineering (UI, workflow, integration, MLOps/GenAI)	Service Now
RTB costs	Lower as platform provides native audit/RBAC/change mgmt. but can have vendor-roadmap dependency	Full run burden in-house (support, on-call, enhancement, governance evidence)	Service Now
