---
jira: 'https://moveinc.atlassian.net/browse/FF-1272'
tags: ['focusfire', 'opcity', 'referral', 'lead', 'ingestion']
title: ['Lead Ownership']
type: 'investigation'
---

- Opcity Owned
	- We pay upfront for leads purchased from a given vendor and take full closing commission
- Broker Lead Accelerator (BLA)
	- Brokerages send us their leads and we vet them first and attempt to dispatch the lead back to the brokerages own agents, we split the closing revenue
- Revenue Sharing
	- We split our revenue from closing consumers with the lead provider and the lead is dispatched to any agent
- If a consumer submits one inquiry on Realtor.com and another inquiry on movoto.com and both come to Opcity, that consumer then goes on to closes on a home with an Opcity agent, who gets the commission?
	- We have owner_broker_id, owner_parent_source_id and owner_source_id which are used to create duplicate leads for inquiries from different owners then we work each lead in tandem so whichever lead closes gets the revenue.
	- Lead inquiries are deduped on owner then phone_number

###### References
1. [Lead Ingestion on Google Docs](https://docs.google.com/presentation/d/1ffnp6xx8oWivDqApMG1QPsJBlagUASFGkfYzS0OtTrk/edit#slide=id.gc6f9e470d_0_0)
2. [What the heck is BLA?](https://www.notion.so/What-the-heck-is-BLA-f0a861da09f54e2599b6cb0293fb4a14)