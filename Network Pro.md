# TestOut Network Pro issues

Various issues I've found in the TestOut Network Pro curriculum.  Feel free to submit PRs for anything I've missed.

## General:

## Chapter 0:

- 0.1.0: "...skills beforeyou study for..." Typo in the very first page :(

## Chapter 1:

- 1.3.0: Items in list look like "`Layer 1&#8211;Physical`"

- 1.3.3: SSL again...

- 1.4.1: SSL doesn't just work "differently", it works highly insecurely...

- 1.4.4: "Web browsers use SSL to ensure safe web transactions."  *cough*poodle*cough*

## Chapter 3

- 3.2.3: The first time I completed the lab one of the computers had no connectivity for seemingly no reason.  The cable used to connect the modem may have been switched with one of the other cables but all devices were connected correctly.

## Chapter 4

- 4.4.5: I couldn't get a full score, as the "disconnect cable, ping workstations, reconnect cable" always showed as not done for some reason.

## Chapter 5

- 5.5.3: Should use www.example.com as the example site, www.mydomain.com is a real site.

## Chapter 6

- 6.3.8: Some questions have us work with interface "FastEthernet0/0", but interface numbers always start at 0/1.

## Chapter 7

- 7.1.2: "Routing is the process of moving packet" -> packets, also in Method: Static, "until they manually removed" -> "until they are manually removed".

- 7.4.6 q1: If the packet has the do-not-fragement flag set, and a size exceeding the MTU, the router has no choice but to drop the packet.  In this case the router is doing what it is supposed to do.  Also, the ping command used here will generate a packet larger than 1500 bytes.  Assuming an Ethernet network is used, the number should be 1472.

- 7.4.6 q9: Windows 2000 and 98?!?

## Chapter 8

- 8.1.9 q11: SSL again :( :( :(

## Chapter 9

- 9.1.5: The SAN technologies comparison table displays wrongly.

## Chapter 10

- 10.1.4: "such as a laptop or a wireless PDA."  PDA?  Sooooo old.

- 10.4.6: "Two laptops..."  This sentence is repeated twice.  Also the "Spectrum Analysis and Channel Plan" section has a lot of redundancy.

## Chapter 13

- 13.1.4: q2 and q14 are the same.

- 13.2.4: The emails are cut off horizontaly, with no way to scroll.

- 13.6.1: NOOOO! HTTP should never be used, only HTTPS. https://https.cio.gov/everything/
