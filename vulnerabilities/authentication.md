# Authentication Vulnerabilities

Authentication is the process of an entity (example user or computer) proving they are who they claim to be. In simple words it verifying the identity of the users and making the access according their identity later. 

There are three main factor that controls the authentication 

- Something you know (example password, pin) 
- Something you have (example physical object, token)
- Something you are (example iris, biometrics)

Because of using these one or more factor in a web application is not mean its authentication mechanism is secure, because there could be a logic flaws exists in a web application

## Common types of Authentication

- Password based authentication
- Multi factor authentication
- Application behaviour or side channel analysis

## Common weakness

- Lack of brute force protection and rate limiting
- Logic flaws 

## Authentication Vulnerabilities

### Brute Force Attack and  Dictionary Attack

Trying all possible passwords combinations is called brute force attack and Trying common passwords from a wordlist is called a dictionary attack. In this types of attack monitoring the status code and response length make us big victory. The response timing is more useful in the response timing or side channel analysis

In the dictionary attack using a effective wordlist is important because it should n't be outdated and match according to the target application

The Best wordlist are

- [seclists](https://github.com/danielmiessler/SecLists)
- [assetnote](https://github.com/assetnote/wordlists)
- [cewl](https://github.com/digininja/CeWL) - custom wordlist generator

**Tools used to brute force**

- [hydra](https://www.kali.org/tools/hydra/)
- [fuzz](https://github.com/ffuf/ffuf) or [wfuzz](https://github.com/xmendez/wfuzz)
### Credential Stuffing 

In the previous data breach in an organisation or other other organisation have some password or credentials for particular user. So it using known leaked credentials to find the valid credentials in the current application

- [haveibeenpwned](https://haveibeenpwned.com/)
- [breach-parse](https://github.com/hmaverickadams/breach-parse)
- some other website which contains the data informations about an organisation in a data breach

### Hard Coded Credentials 

Hard coded credentials are usernames, passwords, API keys, tokens, or encryption keys that are literally written into the source code of an application, script, or configuration file instead of being stored securely

### Password Reset Flaws

Reset tokens are predictable, reusable, or don’t expire quickly. Generally no verification of identity before reset, Reset links sent over insecure channels

### Default Credentials 

Some applications uses the third party software, these software are published with a default username and password for administrative access (example admin:admin) which is need to be changed in the usage but few organization forgot or move with a default password which makes it vulnerable

So In the recon stage we have gathered the information of the third party software used, the documentations of these third party software reveal the default credentials
