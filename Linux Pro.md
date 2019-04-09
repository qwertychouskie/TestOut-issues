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

- 2.2.3: The 4-partition limit does not apply to GPT disks.

- 2.2.3 Remote Access: Both IPMI and Intel vPro/MEI/etc are notoriously insecure, and should NEVER BE RECOMMENDED.

## Chapter 3

-3.5.4: Rebooting uses `runlevel6.target`, not `runlevel1.target`.

## Chapter 4

- X11 is being replaced by Wayland.

- Why even mention XFree86?  2005 is an eternity ago in Linux years.

- KDE is now known as the "K Desktop Environment", not the "Kool Desktop Environment".  Also GNOME's acronym is never really used.

- Enlightenment hasn't been used in GNOME since 2.2 (2007!).  GNOME 2.2 and above use Metacity, and GNOME 3 switched to Mutter.

## Chapter 6

- 6.3.4:  Instructions don't say to remove `aespinoza` from `western_sales_group` but you get dinged if you don't.

## Chapter 8

- 8.3: Most distros got rid of HAL around 2011, with just udev being used now.

## Chapter 10

- 10.1.7: `vi less /var/log/messages` should be `vi /var/log/messages`

- 10.2.5: The shebang is `#!/bin/bash`, not `#! /bin/bash`.  Actually, for portability, `#!/usr/bin/env bash` may be better, see <https://stackoverflow.com/a/10383546/4901968>.
