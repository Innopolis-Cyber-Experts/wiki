# Initial access

During initial access stage, adversary gains access (often as low-priority account) to target system. Corresponding MITRE ATT\&CK Tactic is [TA0001](https://attack.mitre.org/tactics/TA0001/)

While solving vulnboxes, the common ways to get initial access are:

* Exploit CVE
* Exploit RCE in application
* Exploit arbitrary file read to read `/.ssh/id_rsa` or file with credentials
* Leak passwords/hashes through SQL injections, open databases, etc
* Find credentials with bruteforce
