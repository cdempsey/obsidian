---
alias: ['FocusFire Tips and Tricks']
tags: ['focusfire', 'opcity', 'referral', 'testing', 'python', 'javascript']
---

- [Running server tests](https://www.notion.so/Run-Tests-1afb0197b6824f928bca61084afb3441)
	- This works but takes a long time for the initial set up to complete
	- In general, a developer should mark specific tests they want to run with `@pytest.mark.only`
	- `fab local.test:clean && fab local.test:build` to set things up
	- `fab local.test:server,only=True` to only run tests marked with `@pytest.mark.only`
	- `fab local.test:server,only=True,remote_debug=True` to attach a remote debugger
	- Attempting to run the entire test suite will fail
- Running frontend tests