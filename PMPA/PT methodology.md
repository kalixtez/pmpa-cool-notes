![[Pasted image 20250628174717.png]]

## Reconnaissance

Active - Physically interacting with the target through social engineering.
Passive - Crawling through publicly available info on the target that's on the internet.
## Enumeration/Scanning

Using tools that remotely interact with the target's network deployments, in search of running services and vulnerabilities associated to them. Attack surfaces, in general. Trying to list as many as possible.

## Exploitation

Leveraging any or many of the enumerated vulnerabilities in order to violate the integrity of the system some way or another, by leaking data, stealing information, gaining remote access, etc...

## Privilege scalation/post-exploitation

Moving laterally or vertically in order to gain access to different devices or gain higher privilege user access.

## Covering tracks

Obfuscating as much as possible all your activity during the irruption. This is often not necessary for pentesters.

## Reporting

Finally, notifying the target of the findings and giving them a detailed accounting of what was done and more importantly how to fix it.

# MAPT methodology



## Reconnaissance

Going to the target app store page and reading relevant information.

Enumerate things like patches, patch notes, other apps developed by the same team, etc.

Uber example:
![[Pasted image 20250628182515.png]]

## Static analysis

Decompiling and trying to make sense out of all of that mess, trying to find vulnerabilities embedded that are noticeable in written form.

![[Pasted image 20250628183834.png]]
## Dynamic analysis

Running the app and attaching an external debugger, trying to make something out of the execution flow, trying to find vulnerabilities that might be easier to spot when on runtime.

## Reporting

Same as in normal pentesting. It can include, as bonus, positive notes on security measures that did get implemented properly in the code.