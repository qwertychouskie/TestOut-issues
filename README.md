# TestOut PC Pro issues

Various issues I've found in the TestOut PC Pro curiculum.  Feel free to submit PRs for anything I've missed.

## General:

- __*The main site (www.testout.com) doesn't force HTTPS, allowing a MITM attacker (e.g. fake coffee shop wifi) to easily change the "Login" button to point at a fake login.*__  Also the site allow some insecure chiphers, see https://www.ssllabs.com/ssltest/analyze.html?d=testout.com
- __*`su -` doesn't work by default on Ubuntu/Debian-based systems, `sudo commandname` or `sudo su -` should be used instead.*__
- Many times, practice questions are repeated multiple times, usually only with very minor variation
  - Sometimes a question set has us do a lab as part of the set that we had done independently before
- The transcripts for videos often have errors
  - e.g. "ls pci" should be "lspci", etc.

## Chapters 3-4:

- Lab 4.1.3 (the one with the KVM switch) makes us plug in a 12 volt DC power adapter into a KVM switch clearly marked to use 5 volts(!)

- One lab (TODO: add number) made us set the resolution of a display to 1920x1080 when the display's native resolution was 1920x1200... Then, in a later lesson, they tell us multiple times to only use your display's native resolution.

## Chapter 5:

- Lab 5.8.4 has us "Set the storage to its maximum size", except with thin provisioning, what is the maximum?  The lab lets us set sizes like 100TB, but the correct amount is considered 2.3TB of usable space, even though with parity there is only 1.53TB of usable space.  So appearently "maximum" = thin provisioning an arbitrary amount.

- Lab 5.9.6: Setting additional drives to defrag on the schedule results in failing the lab, with no prior indication to the user.

- 5.10.1: The transcript for `bootrec` commands is wrong.

- DVDs do not store "theater-quality video", they store 480p video (720p is the minimum resolution that is considered HD).  Most theaters display movies in 4K, a.k.a. 2160p (though some theaters may use 2K instead).  That's a pretty big difference...

- (Minor) Most burnable CDs that you can buy are the 700MB type, 650MB is much more rare.

## Chapter 6

- 6.5.4 equates HTTPS with SSL and talks about RSA, although __*both SSL and RSA are completely insecure and should not be used.*__ See https://www.trustzone.com/robot-attack-rsa-encryption-vulnerable-choose-ecc-tlsssl-certificates-ensure-security for info on RSA and why it shouldn't be used.

- 6.5.4: The entry for DNS should use `www.example.com`, `www.mydomain.com` is a real site.

- 6.5.5 q9: Should be SFTP or FTPS, not FTP, as __*FTP is insecure.*__  See https://en.wikipedia.org/wiki/File_Transfer_Protocol#Login

## Chapter 7

- Lab 7.3.5 fails you if you set the network printer as the default device even though the instructions never tell you not to.  In fact, since it is the only "real" printer configured on the system, it makes sense to make it the default device.

## Chapter 8

- 8.2.7 q2 and q7: Should be Mini-PCIe, not Mini-PCI.

- Lab 8.3.6: In the "Critical bettery action" section, __*Sleep=Do nothing, Hibernate=Sleep, and Shut down=Hibernate ?!?!?!?!?*__

- 8.3.7 q4: This wouldn't happen.  As long as hibernation support is enabled, `hiberfil.sys` allocates the size necessary for hibernation, the only situation in which this could happen is if the user upgraded their RAM, and there was not sufficient space for `hiberfil.sys` to grow.

- 8.5.3: Just needs to be redone, or something.
  - "Operating system" section: grammatical issues abound.
  - "Virtual assistant" section: What?? "Skyvi" is dead, couldn't even find "AIVIC" ??... I couldn't find "iris" on the Play store either.
  - "Wi-Fi calling": Not just an iPhone thing...
