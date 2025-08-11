# Access Control Vulnerabilities

Access control vulnerabilities are arises due to the unintended user are accessing the resources that they shouldn't. It mainly arises due to improper coding, access control and misconfiguration. 

They allow attackers to bypass intended permissions and perform actions they shouldn’t like viewing other users private data, modifying resources, or even gaining admin level capabilities.

## Types of Access Control Vulnerabilities

**a) Vertical Privilege Escalation**

A low privileged user accesses high privileged resources, and they can have functionality only specified for the high privileged user

Example: A normal user accessing /admin and performing admin actions for deleting, modify or delete 

**b) Horizontal Privilege Escalation**

A user accesses resources of another user with the same privilege level. It could make them to see other users private data 

Example: User A can view /profile?user_id=2 to see User B’s data

## Access Control Vulnerabilities in real world 

**a) Unrestricted Access to APIs (BOLA or BFLA)**

Backend APIs not checking the logged-in user’s permission. It could make the attackers with administrator functionality

- Broken Object Level Access Control (BOLA)

In this vulnerabilities the attacker can only view and can't modify or delete other user

Example: /api/users/123 

- Broken Functional Level Access Control (BFLA)

In this vulnerabilities the attacker can view, modify, delete other user data including the admin accounts. This could lead to account takeover

Example: /api/deleteUser?id=5 works for any logged-in user.

**b) Insecure Direct Object References (IDOR)**

Directly referencing resources without authorization checks. It is similar to the BOLA but there is no API endpoint to retrieve the data here 

Example:

```
GET /invoice/123
Changing 123 to 124 lets the attacker see another user’s invoice.
```

**c) Forced Browsing**

Accessing hidden but unprotected pages by guessing URLs

Example: /hidden/admin/config


