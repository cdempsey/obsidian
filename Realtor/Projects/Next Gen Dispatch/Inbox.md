---
created-on: 'March 06, 2023'
tags: ['2023', 'March', 'Monday', 'next gen dispatch', 'dispatch']
type: 'reference-note'
---

[[2023-03-06]] - Next Gen Dispatch Meeting
Attendees: [[Akash]], [[Carmen]], [[Daniel]], [[Emily]], [[Minjie]], [[Yang]]

Pre-read:
[New Gen Dispatch](https://moveinc.atlassian.net/wiki/spaces/CON/pages/116438403099/New+Gen+Dispatch)

> [!quote]
> - The Referral model has changed a lot since the dispatch process was initially created. **Dispatch works one way needing a phone call, CSR, FocusFire, single agent population, assignment model, metrics,  and the lead page.**
> - Also, since Dispatch precedes all current assignments, any changes, including speed improvements, can have a major business impact.
> - **Dispatch, by initial design, has a deep coupling with a phone call and CSR**. In order for dispatch to run a CSR needs to be on the phone with a consumer.
> - All of the lead page has to be filled out in order for dispatch to run. The lead page is also required to run dispatch.
> - **We currently only segment who is in a dispatch by market** meaning if you are an active agent in the market of a lead, you will be considered for dispatch.
> - **The result of Dispatch is an assignment.** Assignments have side effects for nearly every part of the system.
> - Leads can have only a single active assignment, and each assignment is attached to a single Agent
> - **Currently, agents have to be notified in the dispatch process.** Agents can also only claim using these notifications.
> - **Currently Agents have to claim a lead before being able to work the lead.**
> - Additional challenges: 
>    -   It is hard to update DS models
>    -   Dispatch has a slow slow creation and update time
>    -   Dispatch is hard to extend
>    -   Dispatch is hard to test
>    -   Dispatch is hard to observe 
>    -   Dispatch database tables are incredibly large and not scaling well

##### Meeting Notes

- Dispatch is a result of Opcity's early startup days and implementation choices were made at the call volumes given at the time
- Any call savings can have a major impact on revenue and CSR compensation and stats
- Tight coupling between the Lead Page and Dispatch
- FocusFire backend doesn't start any Dispatch requests
- How we implement contracts with agents and brokers are tied back to Dispatch
- Dispatch process is tightly coupled to the data science models
- There was a lot of brainstorming around implementing Agent Choice
- We'd need to consider the VU request type to Dispatch
- How does this work intersect with MVIP needs?
	- Making the Dispatch matching algorithm customizable
- **TODO**: Look into the Dispatch nightly jobs
- [[Tran]]: Breaking the use of the FocusFire database as the point of synchronization
	- Talk to the database post the Dispatch process run
- [[Daniel]]: We know the database is slow