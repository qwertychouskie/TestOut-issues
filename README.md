# TestOut PC Pro issues

Various issues I've found in the TestOut PC Pro curiculum.  Feel free to submit PRs for anything I've missed.

## General:

- __*The main site (www.testout.com) doesn't force HTTPS, allowing a MITM attacker (e.g. fake coffee shop wifi) to easily change the "Login" button to point at a fake login.*__  Also the site allow some insecure chiphers, see https://www.ssllabs.com/ssltest/analyze.html?d=testout.com
- __*`su -` doesn't work by default on Ubuntu/Debian-based systems, `sudo commandname` or `sudo su -` should be used instead.*__  This is only very breifly touched on in 9.7.1.
- Many times, practice questions are repeated multiple times, usually only with very minor variation
  - Sometimes a question set has us do a lab as part of the set that we had done independently before
  - **The midterm is a direct subset of the practice midterm.**
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

- Modern phones have more secure facial recognition systems, e.g. Face ID.

- 8.2.7 q2 and q7: Should be Mini-PCIe, not Mini-PCI.

- Lab 8.3.6: In the "Critical battery action" section, __*Sleep=Do nothing, Hibernate=Sleep, and Shut down=Hibernate ?!?!?!?!?*__  Also, the lab makes us configure an action for the Low Battery section, not the Critical battery section, while in any real scenario the Low Battery section should just be reserved for a visual warning and the Critical Battery section used for an action such as hibernating.

- 8.3.7 q4: This wouldn't happen.  As long as hibernation support is enabled, `hiberfil.sys` allocates the size necessary for hibernation, the only situation in which this could happen is if the user upgraded their RAM, and there was not sufficient space for `hiberfil.sys` to grow.

- 8.5.3: Just needs to be redone, or something.
  - "Operating system" section: grammatical issues abound.
  - "Virtual assistant" section: What?? "Skyvi" is dead, couldn't even find "AIVIC" ??... I couldn't find "iris" on the Play store either.
  - "Wi-Fi calling": Not just an iPhone thing...

- 8.6: One again, __*It's not SSL.  SSL is insecure.  It's TLS.*__

## Chapter 9

- `sfc /scannow` is mentioned, but `DISM.exe /Online /Cleanup-image /Restorehealth` is not.

- 9.3.4 q4:  Leave blank??  What?!?

- 9.6.9: The services that are supposed to be set to not start on boot are already set to Manual.  This means the service will start only if another service needs it, and would probably be the prefered option here.  Disabled prevents the service from starting at all, even if another service needs it to work properly, so this option should be used with caution.

- 9.7: This section should mention Snap and Flatpak as they are the prefered way to get end-user application on modern distros.

- 9.7.2: The Ubuntu Software Center has been replaced with the distro-agnostic GNOME Software.

- 9.7.4 apt-get: The description for `apt-get update` is wrong.  The command updates the local copy of the list of available packages.  Generally this command should be run before the other apt-get commands.  Also commands like `apt-cache search` and `apt-cache show [packagename]` should be mentioned.  It would actually be good to update the `apt-get` and `apt-cache` commands to their `apt` counterparts, as the `apt` command gives more human-readable output:

  - `apt-get update`       -> `apt update`
  
  - `apt-get dist-upgrade` -> `apt full-upgrade`
  
  - `apt-get install`      -> `apt install`
  
  - `apt-get remove`       -> `apt remove`
  
  - `apt-cache search`     -> `apt search`
  
  - `apt-cache show`       -> `apt show`

- 9.10.8: Lab shows as failed if you use the Settings app instead of Control Panel.

- 9.11.5: Turning on System Protection is usless on drive D, as it is a Windows 10 system.

- 9.12.7: Video has large empty section.

- 9.13.5 q1: Should be "Select three", the minimum size can also be set.

## Chapter 11

- 11.4.6: Using Properties->Sharing->Advanced Sharing causes the lab to fail you for giving the read/write permissions to everyone, even if you do.

## Chapter 12

- 12.3.1: Group policy is useless against a bootable USB with e.g. Linux.  In fact a bootable USB is probably prefered as it can bypass most security measures like file permissions.

- 12.3.2: High voltage will fry the electronics, but the platters will likely be untouched, allowing the data to be potentially recovered.
