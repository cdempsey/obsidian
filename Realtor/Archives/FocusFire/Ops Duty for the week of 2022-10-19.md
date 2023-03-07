---
created-on: 'October 20 2022'
tags: ['2022', 'October', 'Thursday']
type: 'reference-note'
---

- 2022-10-20 10:57 am (Thursday) - [We started seeing a low but persistent rate of SSL handshake errors](https://app.datadoghq.com/monitors/28052324?from_ts=1666280864000&to_ts=1666282064000&eval_ts=1666282064000) when communicating with Yonyx. While the error rate was low it was steady and some CSRs saw the fallback script instead of Yonyx. Ultimately, [[Justin]], [[Ruhul]], and I got on a Zoom call with Nixon and Sanjay with Yonyx Support.
	- Event Length: 57 minutes
	- CSR Affecting: Yes/Minor
	- Discussion: [Slack discussion](https://moveinc.slack.com/archives/C9520AWPK/p1666282344723949)
	- Root cause: At 10:57am on 2022-10-20 GCP had an issue affecting TLS handshaking on load balancers.
	- ![[Pasted image 20221020122053.png]]