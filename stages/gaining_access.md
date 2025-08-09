# Gaining Access

Gaining Access stage is where the attacker actively exploits vulnerabilities that is found in earlier stages (like information gathering, scanning and enumeration and vulnerability identification) to enter the target system or application.

Here the vulnerabilities includes

- Cross-Site Scripting (XSS)
- Access Control Vulnerabilities
- Authentication Vulnerabilities
- SQL Injection
- Path Traversal
- Cross-Site Request Forgery (CSRF)
- Server-Side Request Forgery (SSRF)
- Remote Code Execution (RCE)
- Command Injection
- JWT
- File Upload Vulnerability

## Short Introduction

### Cross-Site Scripting (XSS)

Injecting malicious JavaScript into web pages to steal cookies or session tokens of the other user. The attacker uploads a malicious javascript in web application (eg post malicious javascript in comments) which run in the another user browser when they visit the application 

```
// example for Reflected XSS
<script>alert("Hehe...")</script>

```
### Access Control Vulnerabilities

Access control vulnerabilities are where the unintended user or lower privileged user can access and manage the resources (ie can access, modify and delete the data) that are only intent to high privileged users 

**Example:** The Admin panel is without login or left unprotected but running in high port which could be found using the nmap scanning

### Authentication Vulnerabilities

Authentication is used to protect web application from unauthorised use, and it is used to verify the user and allow authorised used to access the resources. But Authentication Vulnerabilities could arises due improper code for authentication, use of default password, lack of brute force attack and rate limiting

**Example:** The attacker is login as admin by using the brute force attack 

### SQL Injection

Injecting malicious SQL queries into input fields to access or modify database data. SQLi could also make the deletion of the database. It arises due to blind trust in the user input and to prevent it, using parameterized queries

**Example:** 

The Login Query for web application is 

```
SELECT username, password FROM users WHERE username='$user_name' AND password='$password';
```

It is bypass using the SQLi

```
// By entering the payload in username field
admin' OR '1'='1';
```
