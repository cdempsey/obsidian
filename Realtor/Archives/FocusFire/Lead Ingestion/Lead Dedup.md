---
created-on: 'September 16 2022'
tags: ['2022', 'September', 'Friday']
type: 'reference-note'
---

- Given
	- Lead inquiries are deduped on owner then phone_number
- Assumptions
	- There should be one and only one active Lead for a set of Lead Inquiry
	- If we make a Lead dead after the TTL expires then those LeadInquiry pointing to the now Dead Lead will stay that way.
	- New Leads created because of Dead Leads will have their own set of LeadInquiry pointing to them 
	- We want to avoid changes outside of the ingestion / dedupe process if possible to limit the changes that need to be made
- Open Questions
	- Do we need a link between the Dead Lead(s) and the current Live Lead?
	- Do we need to concern ourselves with analytics changes as part of this?
	- Do we need to mark all Lead as "dead" after the TTL expires or just those that get a new LeadInquiry after the TTL?
- General Process
	- Attempt to create the lead from the inquiry (see `inbound.py#_create_or_update_lead`)
	- Most of the work to create a new Lead is done in `ingestion.py#convert`
		- This code determines if a new Lead record in the database is created or not
- Changes to be made
	- Add an `expired` and `expired_at` to the `lead` table and model
		- Don't use any of the current fields to prevent having more than one "meaning" to a datum in the database
		- Instead of running a background job to mark Leads as "dead" we can do it as part of the deduping process
	- `inbound.py#_handle_dedup` will need to take a closer look at the Lead and determine if it's outside of the configured time to stay live
		- The `ingestion.py#convert` is there the decision to create a new Lead is made
		- The current code for this is in `ingestion.py#find_existing_lead_from_lead_client` and it just checks the `owner_parent_source_id`, `origin_parent_source_id`