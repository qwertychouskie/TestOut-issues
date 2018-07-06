# TestOut PC Pro issues

Various issues I've found in the TestOut PC Pro curiculum.  Feel free to submit PRs for anything I've missed.

## General:

- Many times, practice questions are repeated multiple times, usually only with very minor variation
  - Sometimes a question set has us do a lab as part of the set that we had done independently before
- The transcripts for videos often have errors
  - e.g. "ls pci" should be "lspci", etc.

## Chapters 3-4:

- Lab 4.1.3 (the one with the KVM switch) makes us plug in a 12 volt DC power adapter into a KVM switch clearly marked to use 5 volts(!)

- One lab (TODO: add number) made us set the resolution of a display to 1920x1080 when the display's native resolution was 1920x1200... Then, in a later lesson, they tell us multiple times to only use your display's native resolution.

## Chapter 5:

- Lab 5.8.4 has us "Set the storage to its maximum size", except with thin provisioning, what is the maximum?  The lab lets us set sizes like 100TB, but the correct amount is considered 2.3TB of usable space, even though with parity there is only 1.53TB of usable space.  So appearently "maximum" = thin provisioning an arbitrary amount.

- DVDs do not store "theater-quality video", they store 480p video (720p is the minimum resolution that is considered HD).  Most theaters display movies in 4K, a.k.a. 2160p (though some theaters may use 2K instead).  That's a pretty big difference...

- (Minor) Most burnable CDs that you can buy are the 700MB type, 650MB is much more rare.
