# TestOut Linux Pro issues

Various issues I've found in the TestOut Linux Pro curriculum.  Feel free to submit PRs for anything I've missed.

## Chapter 1:

- 1.1.1: Ctl+Alt+F(1-6) is preferred over Alt+F(1-6) as the latter won't work if you are in a GUI evironment while the former will always work.  Both ways are mentioned but Ctl+Alt+F(1-6) should always work and thus should be prefered.

- 1.1.4: DO NOT USE `su` TO "EXIT" FROM A SESSION.  It actually puts you in a sub-sub-session, and anyone can get back to the previous account (which is USUALLY ROOT!) just with the `exit` command, no password needed!

- 1.1.6: `chsh` does not accept `-l` as a parameter, at least on Ubuntu 18.04.

- 1.5.3: The redundant phrase "Environment environmental variables are..." is redundant.

- 1.7.5: `ls /nonesuch 2 > /tmp/deleteme` should be `ls /nonesuch 2> /tmp/deleteme` (no space between the 2 and the >).

- 1.8.5: `rm` description is confusing.

- 1.9.5: "mv ... copies all text files..." s/copies/moves

## Chapter 2:

- 2.1.3: Arch list is outdated, e.g. Apple != PPC, Macs since ~2006 use i686 or x86-64.  Most use of PPC is IBM POWER9 machines.

- 2.1.3: Filesystem list is also outdated.  EXT4 is the default on most systems, and fiesystems like BTRFS, XFS, and ZFS are competing for the spot for the next main Linux FS.
