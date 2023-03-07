---
created-on: 'September 14, 2022'
tags: ['clio', 'deployment', '2022', 'September', 'Wednesday']
type: 'reference-note'
---

###### Post-Deployment Checks

- Check [Datadog dashboards](https://app.datadoghq.com/dashboard/lists)
	- Set it to a 15 minute timeframe
	- Look for spikes or drops in various graphs
	- [Overall System Health](https://app.datadoghq.com/dashboard/n32-bqp-cnv/overall-system-health?from_ts=1663160864625&to_ts=1663161164625&live=true)
	- [Lead Page](https://app.datadoghq.com/dashboard/nt4-mkv-cq5/lead-page?from_ts=1663161318709&to_ts=1663162218709&live=true)
- Verify Production UI
	- Open the console in Dev Tools in your browser so any console output can be seen
	- Ensure you can still log into Production FocusFire
	- Check out various aspects of the FocusFire UI related to your change
	- Check out the general functionality of FocusFire
		- Search and load a Lead
		- Open the User, Reports, and Support tabs
- Keep an eye on Sentry notifications for a bit after your deployment
	- Sentry
		- [admin_new](https://sentry.io/organizations/opcity-inc/projects/admin_new/?environment=prod&project=6019903&statsPeriod=24h)
		- [frontend_test](https://sentry.io/organizations/opcity-inc/projects/frontend-test/?environment=prod&project=1881812&statsPeriod=24h)
		- [internal](https://sentry.io/organizations/opcity-inc/projects/internal/?environment=prod&project=1208762&statsPeriod=24h)
	- Slack
		- [#sentry-internal](https://moveinc.slack.com/archives/CC1KBSU11)
		- [#sentry-internal-noise](https://moveinc.slack.com/archives/CC1KBSU11)