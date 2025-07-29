**Description:**

Stored XSS on the api:

-/admin/user/new (Param: name)

of Calibre-web latest version v0.6.24 ([https://github.com/janeczku/calibre-web/releases/tag/0.6.24](https://github.com/janeczku/calibre-web/releases/tag/0.6.24))

**Proof of Concept:**

1. Add the above API with malicious script tags at Param malicious.
2. with /admin/user/new after adding, access the /admin/usertable -> click Edit Users -> Delete User just created-> Store XSS execute

**Impact:**
The vulnerability, as arbitrary JavaScript still executes in the context of an authenticated administrator.
This enables:

* Display fake login popups to phish admin credentials;

* Steal internal-only data by reading page content (e.g., document.body.innerText, document.forms, document.domain);
  
* ...

With /admin/user/new
![image](https://github.com/xuantien177/vuln_calibre-web/blob/main/Screenshot_11.png)
![image](https://github.com/xuantien177/vuln_calibre-web/blob/main/Screenshot_1.png)
