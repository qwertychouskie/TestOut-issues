# TestOut Linux Pro issues

Various issues I've found in the TestOut Linux Pro curriculum.  Feel free to submit PRs for anything I've missed.

## Chapter 1:

- 1.1.1: Ctl+Alt+F(1-6) is preferred over Alt+F(1-6) as the latter won't work if you are in a GUI evironment while the former will always work.  Both ways are mentioned but Ctl+Alt+F(1-6) should always work and thus should be prefered.

- 1.1.4: DO NOT USE `su` TO "EXIT" FROM A SESSION.  It actually puts you in a sub-sub-session, and anyone can get back to the previous account (which is USUALLY ROOT!) just with the `exit` command, no password needed!
