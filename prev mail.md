From: Godavarthy, Sandhya (Operations/IN) <sandhya.godavarthy@nomura.com> 
Sent: Monday, August 24, 2026 10:00 AM
To: Mundra, Hemant (Operations/IN); Ramchandani, Vikas (Operations/IN); Fernandes, Maria (Operations/IN); Fernandes, Sharon (Operations/IN); Jani, Rupesh (Operations/IN); Kotian, Ashish (Operations/IN); Nachnani, Mayur (Operations/IN)
Cc: Wala, Vishnu (Operations/IN); Kinhikar, Rishabh (Operations/IN); Makkar, Aastha (Operations/IN); Mepani, Arati (Operations/IN); Adhikary, Gopinath (Operations/IN); Mohanty, Satyadarshi (Operations/IN); Nigam, Paramjeet Singh (Operations/IN)
Subject: RE: Update Note – CSG Entity Data | As on 17th June 2026

Hi Hemant, Mayur ,
 
Please find below an update on the in-scope activities and overall project status.
 
We have worked through each activity in detail with business, and we have now documented the AS-IS flows for all in-scope activities.
 
A few key observations from our discussions:
 
•	Common utilities identified – ‘Email ingestion’ and ‘unstructured-to-structured’ utilities are capabilities shared across all activities. A critical enabler will be the logic used to identify which activity (or activities) an incoming email should trigger; we are working with the team to fully understand how this is performed today.
•	Integrated maker-checker design – For the TO-BE flows, we are envisioning maker and checker activities being intertwined within a single workflow. We will be able to firm up this view once all discussions are concluded.
•	Automation opportunities : We have developed an initial view of the automation areas within these activities and expect to conclude on all open points by the end of this week.
 
#	Status of each activity	Count	Next action on
1	Out of scope - integration with 3rd party systems(GMI/Consensys/FIA Tech/ others ) ; API access not beneficial from an ROI perspective (confirmed by business)	12	NA
2	Sign off Provided by business	12	SABRE
3	Discussion in progress with business	10	SABRE
4	Awaiting clarifications from business	8	Business
5	Yet to discuss with business	6	SABRE
6	Out of scope (waiting business confirmation)	3	Business
 	Grand Total	51	 
 
Our thanks to Maria, Rupesh, Ashish and Sharon for taking the time to clarify our queries alongside their BAU commitments.
 
To keep momentum, we have set up a daily call between the SABRE and EDM teams to close out any open points. Detailed activity-level information is available in the appendix below :
 
Activity number	Level 2 activity	Underlying Activities	SABRE SPOC	Business SPOC	Business review Status on AS-IS flows
2.1	Organisation Creation and Maintenance	1) Duplicate checks for Org creation	Vishnu	Rupesh	Sign off Provided by business
2.2		2) Supporting request outside workflow where requester role are not in EVE workflow	Vishnu	Rupesh	Awaiting clarifications from business
2.3		3) Adhoc request raised for non-availability of the dedicated workflow	Vishnu	Rupesh	Sign off Provided by business
2.4		4) NLUX hierarchy set up manual	Vishnu	Rupesh	Awaiting clarifications from business
2.5		5) ALD hierarchy set up manual	Vishnu	Rupesh	Sign off Provided by business
2.6		6) IWM hierarchy set up manual	Vishnu	Rupesh	Awaiting clarifications from business
2.7		7) Org closure process outside EVE.	Vishnu	Rupesh	Awaiting clarifications from business
2.8		8) Org MIFID contact trigger through EMEA	Vishnu	Rupesh	Awaiting clarifications from business
2.9		9) AGTS creation and maintenance	Vishnu	Rupesh	Awaiting clarifications from business
2.10		10) Orgs / Vendor attributes movements	Vishnu	Rupesh	Yet to discuss with business
2.11		11) Override function used for any urgent exception where the Tech failure or Workflow failure or hard restriction.	Vishnu	Rupesh	Yet to discuss with business
2.12		12) Credit Alerts related amendments	Vishnu	Rupesh	Yet to discuss with business
2.13		13) Approval from Legal on attribute change outside of EVE	Vishnu	Rupesh	Yet to discuss with business
2.14		14) Any requester queries related to orgs	Vishnu	Rupesh	Yet to discuss with business
2.15		15) LEI check for Name	Vishnu	Rupesh	Sign off Provided by business
3.1	Account Creation and Maintenance	1) Duplicate check for Account Creation	Satya	Sharon	Sign off Provided by business
3.2		2) Supporting request outside workflow where requester roles are not in EVE workflow	Satya	Sharon	Awaiting clarifications from business
3.3		3) Adhoc request raised for non-availability of the dedicated workflow	Satya	Sharon	Sign off Provided by business
3.4		4) FO system manual set up - Global1 / Sphinx / GMI / Venom-Viper / Totoro / Loanet	Satya	Sharon	Sign off Provided by business
3.5		5) LCM manual set up	Satya	Sharon	Out of scope – integration with 3rd-party systems (GMI / Consensys / FIA Tech / others); API access not beneficial from an ROI perspective (confirmed by business)
3.6		6) NLUX hierarchy set up manual	Satya	Sharon	Awaiting clarifications from business
3.7		7) IWM hierarchy set up manual	Satya	Sharon	Yet to discuss with business
3.8		8) TA closure process outside EVE.	Satya	Sharon	Discussion in progress with business
3.9		9) Override function used for any urgent exception where the Tech failure or Workflow failure or hard restriction.	Satya	Sharon	Sign off Provided by business
3.10		10) Approvals related to Reparent of TA	Satya	Sharon	Sign off Provided by business
3.11		11) Credit Alerts related amendments	Satya	Sharon	Discussion in progress with business
3.12		12) Any requester queries related to TA	Satya	Sharon	Out of scope (waiting business confirmation)
3.13		13) Linking alt codes for FO systems e.g. GMI in EVE	Satya	Sharon	Out of scope – integration with 3rd-party systems (GMI / Consensys / FIA Tech / others); API access not beneficial from an ROI perspective (confirmed by business)
3.14		14) BPS, Impact, Gloss setup for Firm side for NSI	Satya	Sharon	Out of scope – integration with 3rd-party systems (GMI / Consensys / FIA Tech / others); API access not beneficial from an ROI perspective (confirmed by business)
3.15		15) Updating Class code for PB account(NSI)	Satya	Sharon	Out of scope (waiting business confirmation)
3.16		16) LEI check for Name	Satya	Sharon	Sign off Provided by business
3.17		17) Document validation for Name change, F1SA or if any other provided	Satya	Sharon	Out of scope (waiting business confirmation)
1.1	Confirmation, Contacts & General Type	1) Review of Domain matching with counterparty name for contact and confirmation	Rishabh	Ashish	Sign off Provided by business
1.2		2) Validate the relationship provided for mismatch	Rishabh	Ashish	Sign off Provided by business
1.3		3) Duplicate check of G-type attribute requested	Rishabh	Ashish	Discussion in progress with business
1.4		4) Validate the G-type form & request set up for all components of complex G-type screens (Alt code, sector code, Trading scope etc.)	Rishabh	Ashish	Discussion in progress with business
1.5		5) Approval of G-type form	Rishabh	Ashish	Discussion in progress with business
1.6		6) Set up of Type in UAT	Rishabh	Ashish	Discussion in progress with business
1.7		7) Set up of Type in Prod	Rishabh	Ashish	Discussion in progress with business
1.8		8) Unavoidable lower env refresh will retrigger the entire G-type process.	Rishabh	Ashish	Discussion in progress with business
1.9		9) Any requester queries related to Confirmation, Contacts & General Type	Rishabh	Ashish	Discussion in progress with business
1.10		10) Setup in Nomura Now and Postedge for NSI	Rishabh	Ashish	Discussion in progress with business
 	Commission & Fees	Below are the task processed for Commission and Fees process:	 	 	 
4.1		1) Commissions Fails Reports investigation	Aastha	Rupesh	Out of scope – integration with 3rd-party systems (GMI / Consensys / FIA Tech / others); API access not beneficial from an ROI perspective (confirmed by business)
4.2		2) Checking Prop and Client Give Up Agreement	Aastha	Rupesh	Out of scope – integration with 3rd-party systems (GMI / Consensys / FIA Tech / others); API access not beneficial from an ROI perspective (confirmed by business)
4.3		3) Client Commission Schedule approval in CAT	Aastha	Rupesh	Out of scope – integration with 3rd-party systems (GMI / Consensys / FIA Tech / others); API access not beneficial from an ROI perspective (confirmed by business)
4.4		4) Fee and Commission from the Exchange and Agent Broker	Aastha	Rupesh	Out of scope – integration with 3rd-party systems (GMI / Consensys / FIA Tech / others); API access not beneficial from an ROI perspective (confirmed by business)
4.5		5) RDM Account/Book mappings in GMI	Aastha	Rupesh	Out of scope – integration with 3rd-party systems (GMI / Consensys / FIA Tech / others); API access not beneficial from an ROI perspective (confirmed by business)
4.6		6) Queries and investigation	Aastha	Rupesh	Out of scope – integration with 3rd-party systems (GMI / Consensys / FIA Tech / others); API access not beneficial from an ROI perspective (confirmed by business)
4.7		7) Rate maintenance for FX products	Aastha	Rupesh	Out of scope – integration with 3rd-party systems (GMI / Consensys / FIA Tech / others); API access not beneficial from an ROI perspective (confirmed by business)
4.8		8) Account maintenance in LIMA	Aastha	Rupesh	Out of scope – integration with 3rd-party systems (GMI / Consensys / FIA Tech / others); API access not beneficial from an ROI perspective (confirmed by business)
4.9		9) Payables & Receivables report	Aastha	Rupesh	Out of scope – integration with 3rd-party systems (GMI / Consensys / FIA Tech / others); API access not beneficial from an ROI perspective (confirmed by business)
 
