+++
author = "Dicky S"
title = "Try Hack Me Challenge Part 1"
date = "2021-03-17"
tags = [
    "CTF", "Learn"
]
categories = [ "Challenge" ]
+++

![img](https://miro.medium.com/max/2400/1*NqeovuV6RWG0-iK5yZYv6g.png)

Hai Guys! Hari ini saya akan menulis tentang challenge di [try hack me](https://www.tryhackme.com/). Disini saya mengambil challenge yang beginer dan topiknya tentang __NMAP__

#### Task 2 Introduction to Port Scanning

1. What networking constructs are used to direct traffic to the right application on a server?

```
Ports
```

2. How many of these are available on any network-enabled computer?

```
65535
```

3. [__Research__] How many of these are considered "well-known"? (These are the "standard" numbers mentioned in the task)

```
1024
```

#### Task 3 Nmap Switches

1. What is the first switch listed in the help menu for a 'Syn Scan' (more on this later!)?

```
-sS
```
2. Which switch would you use for a "UDP scan"?

```
-sU
```
3. If you wanted to detect which operating system the target is running on, which switch would you use?
```
-o
```
4. Nmap provides a switch to detect the version of the services running on the target. What is this switch?
```
-sv
```
5. The default output provided by nmap often does not provide enough information for a pentester. How would you increase the verbosity?
```
-v
```
6. Verbosity level one is good, but verbosity level two is better! How would you set the verbosity level to two?
(Note: it's highly advisable to always use at least this option)
```
-vv
```
We should always save the output of our scans -- this means that we only need to run the scan once (reducing network traffic and thus chance of detection), and gives us a reference to use when writing reports for clients.

7. What switch would you use to save the nmap results in three major formats?
```
-oA
```
8. What switch would you use to save the nmap results in a "normal" format?
```
-oN
```
9. A very useful output format: how would you save results in a "grepable" format?
```
-oG
```
Sometimes the results we're getting just aren't enough. If we don't care about how loud we are, we can enable "aggressive" mode. This is a shorthand switch that activates service detection, operating system detection, a traceroute and common script scanning.

10. How would you activate this setting?
```
-A
```
Nmap offers five levels of "timing" template. These are essentially used to increase the speed your scan runs at. Be careful though: higher speeds are noisier, and can incur errors!
11. How would you set the timing template to level 5?
```
-A
```
12. How would you tell nmap to only scan port 80?
```
-p 80
```
13. How would you tell nmap to scan ports 1000-1500?
```
-p 1000-1500
```
14. How would you tell nmap to scan all ports?
```
-p-
```
15. How would you activate a script from the nmap scripting library (lots more on this later!)?
```
--script
```
16. How would you activate all of the scripts in the "vuln" category?
```
--script=vuln
```
#### Task 5 TCP Connect Scans

1. Which RFC defines the appropriate behaviour for the TCP protocol?
```
RFC 793
```
2. If a port is closed, which flag should the server send back to indicate this?
```
RST
```
#### Task 6 SYN Scans
1. There are two other names for a SYN scan, what are they?
```
Half-Open, Stealth\
```
2. Can Nmap use a SYN scan without Sudo permissions (Y/N)?
```
N
```
#### Task 7 UDP Scans
1. If a UDP port doesn't respond to an Nmap scan, what will it be marked as?
```
open|filtered
```
2. When a UDP port is closed, by convention the target should send back a "port unreachable" message. Which protocol would it use to do so?
```
ICMP
```

Sampai Jumpa di part 2 nya !!!