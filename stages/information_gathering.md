# Information Gathering (Reconnaissance)

Information Gathering is the first stage of web hacking and it leads to great win in the end because reconnaissance, scanning and enumeration discovers the attack surface which carried to exploit. So effective recon gives lots of chances to discover more vulnerable endpoint and attack surfaces. It is done by with and without interacting with the target.

## Passive Reconnaissance

1. **Physical/Social**

- Location Information - Satellite images, Drone recon, Building layout (badge reader, break areas, security, fencing)
- Job information - Employees (name, job title, phone number, manager, etc) and Pictures (badge photo, desk photos, computer photos, etc)

2. **Web Application**

- Target Validation - WHOIS, nslookup, dnsrecon
- Finding Subdomains - Google Fu, dig, Nmap, sublist3r, Bluto, crt.sh, etc
- Fingerprinting - Nmap, Wappalyzer, WhatWeb, BulitWith, Netcat
- Data Breaches - HavelBeenPwned, Breach-Parse, WeLeakInfo

## Discovering Email Address

Discovering valid email address in a web application is also an important step because if a website lacks in brute force and rate limiting aspects which would leads to comprise using these valid email address

The website used for valid email address hunting in an application: 

- [hunter.io](https://hunter.io/)
- phonebook.cz(https://phonebook.cz/)
- [voilanorbert](https://www.voilanorbert.com/)
- [tools.verifyemailaddress.io](https://tools.emailhippo.com/) - to verify that the email address is exist
- [email checker](email-checker.net/validate)
- we can also use forgot password option in web application to validate email but it could make them to be voilanorbert


