# ZAP Scanning Report

ZAP by [Checkmarx](https://checkmarx.com/).


## Summary of Alerts

| Risk Level | Number of Alerts |
| --- | --- |
| High | 0 |
| Medium | 4 |
| Low | 5 |
| Informational | 15 |




## Alerts

| Name | Risk Level | Number of Instances |
| --- | --- | --- |
| Absence of Anti-CSRF Tokens | Medium | 7 |
| Content Security Policy (CSP) Header Not Set | Medium | 18 |
| Directory Browsing | Medium | 20 |
| Missing Anti-clickjacking Header | Medium | 8 |
| Cookie No HttpOnly Flag | Low | 3 |
| Cookie without SameSite Attribute | Low | 8 |
| Server Leaks Version Information via "Server" HTTP Response Header Field | Low | 59 |
| Timestamp Disclosure - Unix | Low | 1 |
| X-Content-Type-Options Header Missing | Low | 42 |
| Charset Mismatch | Informational | 2 |
| Cookie Poisoning | Informational | 3 |
| Information Disclosure - Suspicious Comments | Informational | 5 |
| Modern Web Application | Informational | 7 |
| Session Management Response Identified | Informational | 6 |
| Tech Detected - Apache HTTP Server | Informational | 1 |
| Tech Detected - Debian | Informational | 1 |
| Tech Detected - Gravatar | Informational | 1 |
| Tech Detected - PHP | Informational | 1 |
| Tech Detected - RSS | Informational | 1 |
| Tech Detected - Underscore.js | Informational | 1 |
| Tech Detected - WordPress | Informational | 1 |
| Tech Detected - jQuery | Informational | 1 |
| User Agent Fuzzer | Informational | 540 |
| User Controllable HTML Element Attribute (Potential XSS) | Informational | 21 |




## Alert Detail



### [ Absence of Anti-CSRF Tokens ](https://www.zaproxy.org/docs/alerts/10202/)



##### Medium (Low)

### Description

No Anti-CSRF tokens were found in a HTML submission form.
A cross-site request forgery is an attack that involves forcing a victim to send an HTTP request to a target destination without their knowledge or intent in order to perform an action as the victim. The underlying cause is application functionality using predictable URL/form actions in a repeatable way. The nature of the attack is that CSRF exploits the trust that a web site has for a user. By contrast, cross-site scripting (XSS) exploits the trust that a user has for a web site. Like XSS, CSRF attacks are not necessarily cross-site, but they can be. Cross-site request forgery is also known as CSRF, XSRF, one-click attack, session riding, confused deputy, and sea surf.

CSRF attacks are effective in a number of situations, including:
    * The victim has an active session on the target site.
    * The victim is authenticated via HTTP auth on the target site.
    * The victim is on the same local network as the target site.

CSRF has primarily been used to perform an action against a target site using the victim's privileges, but recent techniques have been discovered to disclose information by gaining access to the response. The risk of information disclosure is dramatically increased when the target site is vulnerable to XSS, because XSS can be used as a platform for CSRF, allowing the attack to operate within the bounds of the same-origin policy.

* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `<form action="http://192.168.1.120/wp-comments-post.php" method="post" id="commentform" class="comment-form">`
  * Other Info: `No known Anti-CSRF token [anticsrf, CSRFToken, __RequestVerificationToken, csrfmiddlewaretoken, authenticity_token, OWASP_CSRFTOKEN, anoncsrf, csrf_token, _csrf, _csrfSecret, __csrf_magic, CSRF, _token, _csrf_token, _csrfToken] was found in the following HTML form: [Form 1: "author" "comment_parent" "comment_post_ID" "email" "submit" "url" "wp-comment-cookies-consent" ].`
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/%3Freplytocom=1

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `<form action="http://192.168.1.120/wp-comments-post.php" method="post" id="commentform" class="comment-form">`
  * Other Info: `No known Anti-CSRF token [anticsrf, CSRFToken, __RequestVerificationToken, csrfmiddlewaretoken, authenticity_token, OWASP_CSRFTOKEN, anoncsrf, csrf_token, _csrf, _csrfSecret, __csrf_magic, CSRF, _token, _csrf_token, _csrfToken] was found in the following HTML form: [Form 1: "author" "comment_parent" "comment_post_ID" "email" "submit" "url" "wp-comment-cookies-consent" ].`
* URL: http://192.168.1.120/wp-login.php

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `<form name="loginform" id="loginform" action="http://192.168.1.120/wp-login.php" method="post">`
  * Other Info: `No known Anti-CSRF token [anticsrf, CSRFToken, __RequestVerificationToken, csrfmiddlewaretoken, authenticity_token, OWASP_CSRFTOKEN, anoncsrf, csrf_token, _csrf, _csrfSecret, __csrf_magic, CSRF, _token, _csrf_token, _csrfToken] was found in the following HTML form: [Form 1: "redirect_to" "rememberme" "testcookie" "user_login" "user_pass" "wp-submit" ].`
* URL: http://192.168.1.120/wp-login.php%3Faction=lostpassword

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `<form name="lostpasswordform" id="lostpasswordform" action="http://192.168.1.120/wp-login.php?action=lostpassword" method="post">`
  * Other Info: `No known Anti-CSRF token [anticsrf, CSRFToken, __RequestVerificationToken, csrfmiddlewaretoken, authenticity_token, OWASP_CSRFTOKEN, anoncsrf, csrf_token, _csrf, _csrfSecret, __csrf_magic, CSRF, _token, _csrf_token, _csrfToken] was found in the following HTML form: [Form 1: "redirect_to" "user_login" "wp-submit" ].`
* URL: http://192.168.1.120/wp-login.php%3Freauth=1&redirect_to=http%253A%252F%252F192.168.1.120%252Fwp-admin%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `<form name="loginform" id="loginform" action="http://192.168.1.120/wp-login.php" method="post">`
  * Other Info: `No known Anti-CSRF token [anticsrf, CSRFToken, __RequestVerificationToken, csrfmiddlewaretoken, authenticity_token, OWASP_CSRFTOKEN, anoncsrf, csrf_token, _csrf, _csrfSecret, __csrf_magic, CSRF, _token, _csrf_token, _csrfToken] was found in the following HTML form: [Form 1: "redirect_to" "rememberme" "testcookie" "user_login" "user_pass" "wp-submit" ].`
* URL: http://192.168.1.120/wp-login.php

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `<form name="loginform" id="loginform" action="http://192.168.1.120/wp-login.php" method="post">`
  * Other Info: `No known Anti-CSRF token [anticsrf, CSRFToken, __RequestVerificationToken, csrfmiddlewaretoken, authenticity_token, OWASP_CSRFTOKEN, anoncsrf, csrf_token, _csrf, _csrfSecret, __csrf_magic, CSRF, _token, _csrf_token, _csrfToken] was found in the following HTML form: [Form 1: "redirect_to" "rememberme" "testcookie" "user_login" "user_pass" "wp-submit" ].`
* URL: http://192.168.1.120/wp-login.php%3Faction=lostpassword

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `<form name="lostpasswordform" id="lostpasswordform" action="http://192.168.1.120/wp-login.php?action=lostpassword" method="post">`
  * Other Info: `No known Anti-CSRF token [anticsrf, CSRFToken, __RequestVerificationToken, csrfmiddlewaretoken, authenticity_token, OWASP_CSRFTOKEN, anoncsrf, csrf_token, _csrf, _csrfSecret, __csrf_magic, CSRF, _token, _csrf_token, _csrfToken] was found in the following HTML form: [Form 1: "redirect_to" "user_login" "wp-submit" ].`


Instances: 7

### Solution

Phase: Architecture and Design
Use a vetted library or framework that does not allow this weakness to occur or provides constructs that make this weakness easier to avoid.
For example, use anti-CSRF packages such as the OWASP CSRFGuard.

Phase: Implementation
Ensure that your application is free of cross-site scripting issues, because most CSRF defenses can be bypassed using attacker-controlled script.

Phase: Architecture and Design
Generate a unique nonce for each form, place the nonce into the form, and verify the nonce upon receipt of the form. Be sure that the nonce is not predictable (CWE-330).
Note that this can be bypassed using XSS.

Identify especially dangerous operations. When the user performs a dangerous operation, send a separate confirmation request to ensure that the user intended to perform that operation.
Note that this can be bypassed using XSS.

Use the ESAPI Session Management control.
This control includes a component for CSRF.

Do not use the GET method for any request that triggers a state change.

Phase: Implementation
Check the HTTP Referer header to see if the request originated from an expected page. This could break legitimate functionality, because users or proxies may have disabled sending the Referer for privacy reasons.

### Reference


* [ https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html ](https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html)
* [ https://cwe.mitre.org/data/definitions/352.html ](https://cwe.mitre.org/data/definitions/352.html)


#### CWE Id: [ 352 ](https://cwe.mitre.org/data/definitions/352.html)


#### WASC Id: 9

#### Source ID: 3

### [ Content Security Policy (CSP) Header Not Set ](https://www.zaproxy.org/docs/alerts/10038/)



##### Medium (High)

### Description

Content Security Policy (CSP) is an added layer of security that helps to detect and mitigate certain types of attacks, including Cross Site Scripting (XSS) and data injection attacks. These attacks are used for everything from data theft to site defacement or distribution of malware. CSP provides a set of standard HTTP headers that allow website owners to declare approved sources of content that browsers should be allowed to load on that page — covered types are JavaScript, CSS, HTML frames, fonts, images and embeddable objects such as Java applets, ActiveX, audio and video files.

* URL: http://192.168.1.120/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/%3Fs

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/favicon.ico

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/%3Freplytocom=1

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/category/uncategorized/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/robots.txt

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/sitemap.xml

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-login.php

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-login.php%3Faction=lostpassword

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-login.php%3Freauth=1&redirect_to=http%253A%252F%252F192.168.1.120%252Fwp-admin%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-comments-post.php

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-login.php

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-login.php%3Faction=lostpassword

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``


Instances: 18

### Solution

Ensure that your web server, application server, load balancer, etc. is configured to set the Content-Security-Policy header.

### Reference


* [ https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/CSP ](https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/CSP)
* [ https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html ](https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html)
* [ https://www.w3.org/TR/CSP/ ](https://www.w3.org/TR/CSP/)
* [ https://w3c.github.io/webappsec-csp/ ](https://w3c.github.io/webappsec-csp/)
* [ https://web.dev/articles/csp ](https://web.dev/articles/csp)
* [ https://caniuse.com/#feat=contentsecuritypolicy ](https://caniuse.com/#feat=contentsecuritypolicy)
* [ https://content-security-policy.com/ ](https://content-security-policy.com/)


#### CWE Id: [ 693 ](https://cwe.mitre.org/data/definitions/693.html)


#### WASC Id: 15

#### Source ID: 3

### [ Directory Browsing ](https://www.zaproxy.org/docs/alerts/0/)



##### Medium (Medium)

### Description

It is possible to view the directory listing. Directory listing may reveal hidden scripts, include files, backup source files, etc. which can be accessed to read sensitive information.

* URL: http://192.168.1.120/wp-admin/js/

  * Method: `GET`
  * Parameter: ``
  * Attack: `http://192.168.1.120/wp-admin/js/`
  * Evidence: `Parent Directory`
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/

  * Method: `GET`
  * Parameter: ``
  * Attack: `http://192.168.1.120/wp-content/themes/twentytwentyfive/`
  * Evidence: `Parent Directory`
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/

  * Method: `GET`
  * Parameter: ``
  * Attack: `http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/`
  * Evidence: `Parent Directory`
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts/

  * Method: `GET`
  * Parameter: ``
  * Attack: `http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts/`
  * Evidence: `Parent Directory`
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts/manrope/

  * Method: `GET`
  * Parameter: ``
  * Attack: `http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts/manrope/`
  * Evidence: `Parent Directory`
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/images/

  * Method: `GET`
  * Parameter: ``
  * Attack: `http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/images/`
  * Evidence: `Parent Directory`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/

  * Method: `GET`
  * Parameter: ``
  * Attack: `http://192.168.1.120/wp-includes/`
  * Evidence: `Parent Directory`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/navigation/

  * Method: `GET`
  * Parameter: ``
  * Attack: `http://192.168.1.120/wp-includes/blocks/navigation/`
  * Evidence: `Parent Directory`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/paragraph/

  * Method: `GET`
  * Parameter: ``
  * Attack: `http://192.168.1.120/wp-includes/blocks/paragraph/`
  * Evidence: `Parent Directory`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/quote/

  * Method: `GET`
  * Parameter: ``
  * Attack: `http://192.168.1.120/wp-includes/blocks/quote/`
  * Evidence: `Parent Directory`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/

  * Method: `GET`
  * Parameter: ``
  * Attack: `http://192.168.1.120/wp-includes/css/`
  * Evidence: `Parent Directory`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist/

  * Method: `GET`
  * Parameter: ``
  * Attack: `http://192.168.1.120/wp-includes/css/dist/`
  * Evidence: `Parent Directory`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist/block-library/

  * Method: `GET`
  * Parameter: ``
  * Attack: `http://192.168.1.120/wp-includes/css/dist/block-library/`
  * Evidence: `Parent Directory`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/images/

  * Method: `GET`
  * Parameter: ``
  * Attack: `http://192.168.1.120/wp-includes/images/`
  * Evidence: `Parent Directory`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/

  * Method: `GET`
  * Parameter: ``
  * Attack: `http://192.168.1.120/wp-includes/js/`
  * Evidence: `Parent Directory`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/

  * Method: `GET`
  * Parameter: ``
  * Attack: `http://192.168.1.120/wp-includes/js/dist/`
  * Evidence: `Parent Directory`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/

  * Method: `GET`
  * Parameter: ``
  * Attack: `http://192.168.1.120/wp-includes/js/dist/script-modules/`
  * Evidence: `Parent Directory`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library/

  * Method: `GET`
  * Parameter: ``
  * Attack: `http://192.168.1.120/wp-includes/js/dist/script-modules/block-library/`
  * Evidence: `Parent Directory`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library/navigation/

  * Method: `GET`
  * Parameter: ``
  * Attack: `http://192.168.1.120/wp-includes/js/dist/script-modules/block-library/navigation/`
  * Evidence: `Parent Directory`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/interactivity/

  * Method: `GET`
  * Parameter: ``
  * Attack: `http://192.168.1.120/wp-includes/js/dist/script-modules/interactivity/`
  * Evidence: `Parent Directory`
  * Other Info: ``


Instances: 20

### Solution

Disable directory browsing. If this is required, make sure the listed files does not induce risks.

### Reference


* [ https://httpd.apache.org/docs/current/mod/core.html#options ](https://httpd.apache.org/docs/current/mod/core.html#options)


#### CWE Id: [ 548 ](https://cwe.mitre.org/data/definitions/548.html)


#### WASC Id: 48

#### Source ID: 1

### [ Missing Anti-clickjacking Header ](https://www.zaproxy.org/docs/alerts/10020/)



##### Medium (Medium)

### Description

The response does not protect against 'ClickJacking' attacks. It should include either Content-Security-Policy with 'frame-ancestors' directive or X-Frame-Options.

* URL: http://192.168.1.120/

  * Method: `GET`
  * Parameter: `x-frame-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/%3Fs

  * Method: `GET`
  * Parameter: `x-frame-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/

  * Method: `GET`
  * Parameter: `x-frame-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/%3Freplytocom=1

  * Method: `GET`
  * Parameter: `x-frame-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed/

  * Method: `GET`
  * Parameter: `x-frame-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser/

  * Method: `GET`
  * Parameter: `x-frame-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/

  * Method: `GET`
  * Parameter: `x-frame-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed/

  * Method: `GET`
  * Parameter: `x-frame-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``


Instances: 8

### Solution

Modern Web browsers support the Content-Security-Policy and X-Frame-Options HTTP headers. Ensure one of them is set on all web pages returned by your site/app.
If you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY. Alternatively consider implementing Content Security Policy's "frame-ancestors" directive.

### Reference


* [ https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/X-Frame-Options ](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/X-Frame-Options)


#### CWE Id: [ 1021 ](https://cwe.mitre.org/data/definitions/1021.html)


#### WASC Id: 15

#### Source ID: 3

### [ Cookie No HttpOnly Flag ](https://www.zaproxy.org/docs/alerts/10010/)



##### Low (Medium)

### Description

A cookie has been set without the HttpOnly flag, which means that the cookie can be accessed by JavaScript. If a malicious script can be run on this page then the cookie will be accessible and can be transmitted to another site. If this is a session cookie then session hijacking may be possible.

* URL: http://192.168.1.120/wp-comments-post.php

  * Method: `POST`
  * Parameter: `comment_author_ac15cbef5f18ce9721669532eb10f867`
  * Attack: ``
  * Evidence: `Set-Cookie: comment_author_ac15cbef5f18ce9721669532eb10f867`
  * Other Info: ``
* URL: http://192.168.1.120/wp-comments-post.php

  * Method: `POST`
  * Parameter: `comment_author_email_ac15cbef5f18ce9721669532eb10f867`
  * Attack: ``
  * Evidence: `Set-Cookie: comment_author_email_ac15cbef5f18ce9721669532eb10f867`
  * Other Info: ``
* URL: http://192.168.1.120/wp-comments-post.php

  * Method: `POST`
  * Parameter: `comment_author_url_ac15cbef5f18ce9721669532eb10f867`
  * Attack: ``
  * Evidence: `Set-Cookie: comment_author_url_ac15cbef5f18ce9721669532eb10f867`
  * Other Info: ``


Instances: 3

### Solution

Ensure that the HttpOnly flag is set for all cookies.

### Reference


* [ https://owasp.org/www-community/HttpOnly ](https://owasp.org/www-community/HttpOnly)


#### CWE Id: [ 1004 ](https://cwe.mitre.org/data/definitions/1004.html)


#### WASC Id: 13

#### Source ID: 3

### [ Cookie without SameSite Attribute ](https://www.zaproxy.org/docs/alerts/10054/)



##### Low (Medium)

### Description

A cookie has been set without the SameSite attribute, which means that the cookie can be sent as a result of a 'cross-site' request. The SameSite attribute is an effective counter measure to cross-site request forgery, cross-site script inclusion, and timing attacks.

* URL: http://192.168.1.120/wp-login.php

  * Method: `GET`
  * Parameter: `wordpress_test_cookie`
  * Attack: ``
  * Evidence: `Set-Cookie: wordpress_test_cookie`
  * Other Info: ``
* URL: http://192.168.1.120/wp-login.php%3Faction=lostpassword

  * Method: `GET`
  * Parameter: `wordpress_test_cookie`
  * Attack: ``
  * Evidence: `Set-Cookie: wordpress_test_cookie`
  * Other Info: ``
* URL: http://192.168.1.120/wp-login.php%3Freauth=1&redirect_to=http%253A%252F%252F192.168.1.120%252Fwp-admin%252F

  * Method: `GET`
  * Parameter: `wordpress_test_cookie`
  * Attack: ``
  * Evidence: `Set-Cookie: wordpress_test_cookie`
  * Other Info: ``
* URL: http://192.168.1.120/wp-comments-post.php

  * Method: `POST`
  * Parameter: `comment_author_ac15cbef5f18ce9721669532eb10f867`
  * Attack: ``
  * Evidence: `Set-Cookie: comment_author_ac15cbef5f18ce9721669532eb10f867`
  * Other Info: ``
* URL: http://192.168.1.120/wp-comments-post.php

  * Method: `POST`
  * Parameter: `comment_author_email_ac15cbef5f18ce9721669532eb10f867`
  * Attack: ``
  * Evidence: `Set-Cookie: comment_author_email_ac15cbef5f18ce9721669532eb10f867`
  * Other Info: ``
* URL: http://192.168.1.120/wp-comments-post.php

  * Method: `POST`
  * Parameter: `comment_author_url_ac15cbef5f18ce9721669532eb10f867`
  * Attack: ``
  * Evidence: `Set-Cookie: comment_author_url_ac15cbef5f18ce9721669532eb10f867`
  * Other Info: ``
* URL: http://192.168.1.120/wp-login.php

  * Method: `POST`
  * Parameter: `wordpress_test_cookie`
  * Attack: ``
  * Evidence: `Set-Cookie: wordpress_test_cookie`
  * Other Info: ``
* URL: http://192.168.1.120/wp-login.php%3Faction=lostpassword

  * Method: `POST`
  * Parameter: `wordpress_test_cookie`
  * Attack: ``
  * Evidence: `Set-Cookie: wordpress_test_cookie`
  * Other Info: ``


Instances: 8

### Solution

Ensure that the SameSite attribute is set to either 'lax' or ideally 'strict' for all cookies.

### Reference


* [ https://datatracker.ietf.org/doc/html/draft-ietf-httpbis-cookie-same-site ](https://datatracker.ietf.org/doc/html/draft-ietf-httpbis-cookie-same-site)


#### CWE Id: [ 1275 ](https://cwe.mitre.org/data/definitions/1275.html)


#### WASC Id: 13

#### Source ID: 3

### [ Server Leaks Version Information via "Server" HTTP Response Header Field ](https://www.zaproxy.org/docs/alerts/10036/)



##### Low (High)

### Description

The web/application server is leaking version information via the "Server" HTTP response header. Access to such information may facilitate attackers identifying other vulnerabilities your web/application server is subject to.

* URL: http://192.168.1.120/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/%3Fp=1

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/%3Fp=2

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/%3Fs

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/favicon.ico

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/%3Freplytocom=1

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/feed/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser/feed/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/index.php/category/uncategorized/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/index.php/comments/feed/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/index.php/feed/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/feed/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/index.php/search/feed/rss2/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Fformat=xml&url=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Fformat=xml&url=http%253A%252F%252F192.168.1.120%252Findex.php%252Fsample-page%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Furl=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Furl=http%253A%252F%252F192.168.1.120%252Findex.php%252Fsample-page%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/wp/v2/pages/2

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/wp/v2/posts/1

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/wp/v2/users/1

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/robots.txt

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/sitemap.xml

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/js/password-strength-meter.min.js%3Fver=6.8.3

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/js/user-profile.min.js%3Fver=6.8.3

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/load-scripts.php%3Fc=0&load%255Bchunk_0%255D=clipboard,jquery-core,jquery-migrate,zxcvbn-async,wp-hooks&ver=6.8.3

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/load-styles.php%3Fc=0&dir=ltr&load%255Bchunk_0%255D=dashicons,buttons,forms,l10n,login&ver=6.8.3

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts/manrope/Manrope-VariableFont_wght.woff2

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/images/404-image.webp

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/style.css%3Fver=1.3

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/navigation/style.min.css%3Fver=6.8.3

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/paragraph/style.min.css%3Fver=6.8.3

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/quote/style.min.css%3Fver=6.8.3

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist/block-library/common.min.css%3Fver=6.8.3

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/wp-embed-template-ie.min.css%3Fver=6.8.3

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/images/w-logo-blue.png

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/comment-reply.min.js%3Fver=6.8.3

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/a11y.min.js%3Fver=3156534cc54473497e14

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/dom-ready.min.js%3Fver=f77871ff7694fffea381

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/i18n.min.js%3Fver=5e580eb46a90c2b997e6

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library/navigation/view.min.js%3Fver=61572d447d60c0aa5240

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/interactivity/index.min.js%3Fver=55aebb6e0a16726baffb

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/underscore.min.js%3Fver=1.13.7

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/wp-emoji-release.min.js%3Fver=6.8.3

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/wp-util.min.js%3Fver=6.8.3

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-login.php

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-login.php%3Faction=lostpassword

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-login.php%3Freauth=1&redirect_to=http%253A%252F%252F192.168.1.120%252Fwp-admin%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/xmlrpc.php

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/xmlrpc.php%3Frsd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-comments-post.php

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-login.php

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``
* URL: http://192.168.1.120/wp-login.php%3Faction=lostpassword

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65 (Debian)`
  * Other Info: ``


Instances: 59

### Solution

Ensure that your web server, application server, load balancer, etc. is configured to suppress the "Server" header or provide generic details.

### Reference


* [ https://httpd.apache.org/docs/current/mod/core.html#servertokens ](https://httpd.apache.org/docs/current/mod/core.html#servertokens)
* [ https://learn.microsoft.com/en-us/previous-versions/msp-n-p/ff648552(v=pandp.10) ](https://learn.microsoft.com/en-us/previous-versions/msp-n-p/ff648552(v=pandp.10))
* [ https://www.troyhunt.com/shhh-dont-let-your-response-headers/ ](https://www.troyhunt.com/shhh-dont-let-your-response-headers/)


#### CWE Id: [ 497 ](https://cwe.mitre.org/data/definitions/497.html)


#### WASC Id: 13

#### Source ID: 3

### [ Timestamp Disclosure - Unix ](https://www.zaproxy.org/docs/alerts/10096/)



##### Low (Low)

### Description

A timestamp was disclosed by the application/web server. - Unix

* URL: http://192.168.1.120/index.php/sample-page/embed/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1920439558`
  * Other Info: `1920439558, which evaluates to: 2030-11-09 09:25:58.`


Instances: 1

### Solution

Manually confirm that the timestamp data is not sensitive, and that the data cannot be aggregated to disclose exploitable patterns.

### Reference


* [ https://cwe.mitre.org/data/definitions/200.html ](https://cwe.mitre.org/data/definitions/200.html)


#### CWE Id: [ 497 ](https://cwe.mitre.org/data/definitions/497.html)


#### WASC Id: 13

#### Source ID: 3

### [ X-Content-Type-Options Header Missing ](https://www.zaproxy.org/docs/alerts/10021/)



##### Low (Medium)

### Description

The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'. This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type. Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.

* URL: http://192.168.1.120/

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/%3Fs

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/%3Freplytocom=1

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed/

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/feed/

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/index.php/author/cyberarenauser/

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/index.php/author/cyberarenauser/feed/

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/index.php/comments/feed/

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/index.php/feed/

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/index.php/sample-page/

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/index.php/sample-page/embed/

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/index.php/sample-page/feed/

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/index.php/search/feed/rss2/

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-admin/js/password-strength-meter.min.js%3Fver=6.8.3

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-admin/js/user-profile.min.js%3Fver=6.8.3

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-admin/load-scripts.php%3Fc=0&load%255Bchunk_0%255D=clipboard,jquery-core,jquery-migrate,zxcvbn-async,wp-hooks&ver=6.8.3

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-admin/load-styles.php%3Fc=0&dir=ltr&load%255Bchunk_0%255D=dashicons,buttons,forms,l10n,login&ver=6.8.3

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts/manrope/Manrope-VariableFont_wght.woff2

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/images/404-image.webp

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/style.css%3Fver=1.3

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-includes/blocks/navigation/style.min.css%3Fver=6.8.3

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-includes/blocks/paragraph/style.min.css%3Fver=6.8.3

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-includes/blocks/quote/style.min.css%3Fver=6.8.3

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-includes/css/dist/block-library/common.min.css%3Fver=6.8.3

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-includes/css/wp-embed-template-ie.min.css%3Fver=6.8.3

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-includes/images/w-logo-blue.png

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-includes/js/comment-reply.min.js%3Fver=6.8.3

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-includes/js/dist/a11y.min.js%3Fver=3156534cc54473497e14

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-includes/js/dist/dom-ready.min.js%3Fver=f77871ff7694fffea381

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-includes/js/dist/i18n.min.js%3Fver=5e580eb46a90c2b997e6

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library/navigation/view.min.js%3Fver=61572d447d60c0aa5240

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/interactivity/index.min.js%3Fver=55aebb6e0a16726baffb

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-includes/js/underscore.min.js%3Fver=1.13.7

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-includes/js/wp-emoji-release.min.js%3Fver=6.8.3

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-includes/js/wp-util.min.js%3Fver=6.8.3

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-login.php

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-login.php%3Faction=lostpassword

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-login.php%3Freauth=1&redirect_to=http%253A%252F%252F192.168.1.120%252Fwp-admin%252F

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/xmlrpc.php%3Frsd

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-login.php

  * Method: `POST`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://192.168.1.120/wp-login.php%3Faction=lostpassword

  * Method: `POST`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`


Instances: 42

### Solution

Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.
If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.

### Reference


* [ https://learn.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/compatibility/gg622941(v=vs.85) ](https://learn.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/compatibility/gg622941(v=vs.85))
* [ https://owasp.org/www-community/Security_Headers ](https://owasp.org/www-community/Security_Headers)


#### CWE Id: [ 693 ](https://cwe.mitre.org/data/definitions/693.html)


#### WASC Id: 15

#### Source ID: 3

### [ Charset Mismatch ](https://www.zaproxy.org/docs/alerts/90011/)



##### Informational (Low)

### Description

This check identifies responses where the HTTP Content-Type header declares a charset different from the charset defined by the body of the HTML or XML. When there's a charset mismatch between the HTTP header and content body Web browsers can be forced into an undesirable content-sniffing mode to determine the content's correct character set.

An attacker could manipulate content on the page to be interpreted in an encoding of their choice. For example, if an attacker can control content at the beginning of the page, they could inject script using UTF-7 encoded text and manipulate some browsers into interpreting that text.

* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Fformat=xml&url=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: `There was a charset mismatch between the HTTP Header and the XML encoding declaration: [UTF-8] and [null] do not match.`
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Fformat=xml&url=http%253A%252F%252F192.168.1.120%252Findex.php%252Fsample-page%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: `There was a charset mismatch between the HTTP Header and the XML encoding declaration: [UTF-8] and [null] do not match.`


Instances: 2

### Solution

Force UTF-8 for all text content in both the HTTP header and meta tags in HTML or encoding declarations in XML.

### Reference


* [ https://code.google.com/p/browsersec/wiki/Part2#Character_set_handling_and_detection ](https://code.google.com/p/browsersec/wiki/Part2#Character_set_handling_and_detection)


#### CWE Id: [ 436 ](https://cwe.mitre.org/data/definitions/436.html)


#### WASC Id: 15

#### Source ID: 3

### [ Cookie Poisoning ](https://www.zaproxy.org/docs/alerts/10029/)



##### Informational (Low)

### Description

This check looks at user-supplied input in query string parameters and POST data to identify where cookie parameters might be controlled. This is called a cookie poisoning attack, and becomes exploitable when an attacker can manipulate the cookie in various ways. In some cases this will not be exploitable, however, allowing URL parameters to set cookie values is generally considered a bug.

* URL: http://192.168.1.120/wp-comments-post.php

  * Method: `POST`
  * Parameter: `author`
  * Attack: ``
  * Evidence: ``
  * Other Info: `An attacker may be able to poison cookie values through POST parameters. To test if this is a more serious issue, you should try resending that request as a GET, with the POST parameter included as a query string parameter. For example: https://nottrusted.com/page?value=maliciousInput.

This was identified at:

http://192.168.1.120/wp-comments-post.php

User-input was found in the following cookie:
comment_author_ac15cbef5f18ce9721669532eb10f867=ZAP; expires=Wed, 11 Nov 2026 08:28:12 GMT; Max-Age=31536000; path=/

The user input was:
author=ZAP`
* URL: http://192.168.1.120/wp-comments-post.php

  * Method: `POST`
  * Parameter: `email`
  * Attack: ``
  * Evidence: ``
  * Other Info: `An attacker may be able to poison cookie values through POST parameters. To test if this is a more serious issue, you should try resending that request as a GET, with the POST parameter included as a query string parameter. For example: https://nottrusted.com/page?value=maliciousInput.

This was identified at:

http://192.168.1.120/wp-comments-post.php

User-input was found in the following cookie:
comment_author_email_ac15cbef5f18ce9721669532eb10f867=zaproxy@example.com; expires=Wed, 11 Nov 2026 08:28:12 GMT; Max-Age=31536000; path=/

The user input was:
email=zaproxy@example.com`
* URL: http://192.168.1.120/wp-comments-post.php

  * Method: `POST`
  * Parameter: `url`
  * Attack: ``
  * Evidence: ``
  * Other Info: `An attacker may be able to poison cookie values through POST parameters. To test if this is a more serious issue, you should try resending that request as a GET, with the POST parameter included as a query string parameter. For example: https://nottrusted.com/page?value=maliciousInput.

This was identified at:

http://192.168.1.120/wp-comments-post.php

User-input was found in the following cookie:
comment_author_url_ac15cbef5f18ce9721669532eb10f867=https://zap.example.com; expires=Wed, 11 Nov 2026 08:28:12 GMT; Max-Age=31536000; path=/

The user input was:
url=https://zap.example.com`


Instances: 3

### Solution

Do not allow user input to control cookie names and values. If some query string parameters must be set in cookie values, be sure to filter out semicolon's that can serve as name/value pair delimiters.

### Reference


* [ https://en.wikipedia.org/wiki/HTTP_cookie ](https://en.wikipedia.org/wiki/HTTP_cookie)
* [ https://cwe.mitre.org/data/definitions/565.html ](https://cwe.mitre.org/data/definitions/565.html)


#### CWE Id: [ 565 ](https://cwe.mitre.org/data/definitions/565.html)


#### WASC Id: 20

#### Source ID: 3

### [ Information Disclosure - Suspicious Comments ](https://www.zaproxy.org/docs/alerts/10027/)



##### Informational (Low)

### Description

The response appears to contain suspicious comments which may help an attacker.

* URL: http://192.168.1.120/wp-admin/load-scripts.php%3Fc=0&load%255Bchunk_0%255D=clipboard,jquery-core,jquery-migrate,zxcvbn-async,wp-hooks&ver=6.8.3

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `username`
  * Other Info: `The following pattern was used: \bUSERNAME\b and was detected in likely comment: "//,Bt={},_t={},zt="*/".concat("*"),Xt=C.createElement("a");function Ut(o){return function(e,t){"string"!=typeof e&&(t=e,e="*");v", see evidence field for the suspicious comment/snippet.`
* URL: http://192.168.1.120/wp-includes/js/wp-emoji-release.min.js%3Fver=6.8.3

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `select`
  * Other Info: `The following pattern was used: \bSELECT\b and was detected in likely comment: "//cdn.jsdelivr.net/gh/jdecked/twemoji@16.0.1/assets/",ext:".png",size:"72x72",className:"emoji",convert:{fromCodePoint:function(", see evidence field for the suspicious comment/snippet.`
* URL: http://192.168.1.120/wp-login.php

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `admin`
  * Other Info: `The following pattern was used: \bADMIN\b and was detected 3 times, the first in likely comment: "//192.168.1.120/wp-admin/load-scripts.php?c=0&amp;load%5Bchunk_0%5D=clipboard,jquery-core,jquery-migrate,zxcvbn-async,wp-hooks&a", see evidence field for the suspicious comment/snippet.`
* URL: http://192.168.1.120/wp-login.php%3Freauth=1&redirect_to=http%253A%252F%252F192.168.1.120%252Fwp-admin%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `admin`
  * Other Info: `The following pattern was used: \bADMIN\b and was detected 3 times, the first in likely comment: "//192.168.1.120/wp-admin/load-scripts.php?c=0&amp;load%5Bchunk_0%5D=clipboard,jquery-core,jquery-migrate,zxcvbn-async,wp-hooks&a", see evidence field for the suspicious comment/snippet.`
* URL: http://192.168.1.120/wp-login.php

  * Method: `POST`
  * Parameter: ``
  * Attack: ``
  * Evidence: `admin`
  * Other Info: `The following pattern was used: \bADMIN\b and was detected 3 times, the first in likely comment: "//192.168.1.120/wp-admin/load-scripts.php?c=0&amp;load%5Bchunk_0%5D=clipboard,jquery-core,jquery-migrate,zxcvbn-async,wp-hooks&a", see evidence field for the suspicious comment/snippet.`


Instances: 5

### Solution

Remove all comments that return information that may help an attacker and fix any underlying problems they refer to.

### Reference



#### CWE Id: [ 615 ](https://cwe.mitre.org/data/definitions/615.html)


#### WASC Id: 13

#### Source ID: 3

### [ Modern Web Application ](https://www.zaproxy.org/docs/alerts/10109/)



##### Informational (Medium)

### Description

The application appears to be a modern web application. If you need to explore it automatically then the Ajax Spider may well be more effective than the standard one.

* URL: http://192.168.1.120/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `<a href="http://192.168.1.120" target="_self" rel="home" aria-current="page">Centria cyberarena</a>`
  * Other Info: `Links have been found with a target of '_self' - this is often used by modern frameworks to force a full page reload.`
* URL: http://192.168.1.120/%3Fs

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `<a href="http://192.168.1.120" target="_self" rel="home">Centria cyberarena</a>`
  * Other Info: `Links have been found with a target of '_self' - this is often used by modern frameworks to force a full page reload.`
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `<a href="http://192.168.1.120" target="_self" rel="home">Centria cyberarena</a>`
  * Other Info: `Links have been found with a target of '_self' - this is often used by modern frameworks to force a full page reload.`
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/%3Freplytocom=1

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `<a href="http://192.168.1.120" target="_self" rel="home">Centria cyberarena</a>`
  * Other Info: `Links have been found with a target of '_self' - this is often used by modern frameworks to force a full page reload.`
* URL: http://192.168.1.120/index.php/author/cyberarenauser/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `<a href="http://192.168.1.120" target="_self" rel="home">Centria cyberarena</a>`
  * Other Info: `Links have been found with a target of '_self' - this is often used by modern frameworks to force a full page reload.`
* URL: http://192.168.1.120/index.php/category/uncategorized/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `<a href="http://192.168.1.120" target="_self" rel="home">Centria cyberarena</a>`
  * Other Info: `Links have been found with a target of '_self' - this is often used by modern frameworks to force a full page reload.`
* URL: http://192.168.1.120/index.php/sample-page/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `<a href="http://192.168.1.120" target="_self" rel="home">Centria cyberarena</a>`
  * Other Info: `Links have been found with a target of '_self' - this is often used by modern frameworks to force a full page reload.`


Instances: 7

### Solution

This is an informational alert and so no changes are required.

### Reference




#### Source ID: 3

### [ Session Management Response Identified ](https://www.zaproxy.org/docs/alerts/10112/)



##### Informational (Medium)

### Description

The given response has been identified as containing a session management token. The 'Other Info' field contains a set of header tokens that can be used in the Header Based Session Management Method. If the request is in a context which has a Session Management Method set to "Auto-Detect" then this rule will change the session management to use the tokens identified.

* URL: http://192.168.1.120/wp-login.php

  * Method: `GET`
  * Parameter: `wordpress_test_cookie`
  * Attack: ``
  * Evidence: `wordpress_test_cookie`
  * Other Info: `cookie:wordpress_test_cookie`
* URL: http://192.168.1.120/wp-login.php%3Faction=lostpassword

  * Method: `GET`
  * Parameter: `wordpress_test_cookie`
  * Attack: ``
  * Evidence: `wordpress_test_cookie`
  * Other Info: `cookie:wordpress_test_cookie`
* URL: http://192.168.1.120/wp-login.php%3Freauth=1&redirect_to=http%253A%252F%252F192.168.1.120%252Fwp-admin%252F

  * Method: `GET`
  * Parameter: `wordpress_test_cookie`
  * Attack: ``
  * Evidence: `wordpress_test_cookie`
  * Other Info: `cookie:wordpress_test_cookie`
* URL: http://192.168.1.120/wp-comments-post.php

  * Method: `POST`
  * Parameter: `comment_author_url_ac15cbef5f18ce9721669532eb10f867`
  * Attack: ``
  * Evidence: `comment_author_url_ac15cbef5f18ce9721669532eb10f867`
  * Other Info: `cookie:comment_author_url_ac15cbef5f18ce9721669532eb10f867
cookie:comment_author_email_ac15cbef5f18ce9721669532eb10f867`
* URL: http://192.168.1.120/wp-login.php

  * Method: `POST`
  * Parameter: `wordpress_test_cookie`
  * Attack: ``
  * Evidence: `wordpress_test_cookie`
  * Other Info: `cookie:wordpress_test_cookie`
* URL: http://192.168.1.120/wp-login.php%3Faction=lostpassword

  * Method: `POST`
  * Parameter: `wordpress_test_cookie`
  * Attack: ``
  * Evidence: `wordpress_test_cookie`
  * Other Info: `cookie:wordpress_test_cookie`


Instances: 6

### Solution

This is an informational alert rather than a vulnerability and so there is nothing to fix.

### Reference


* [ https://www.zaproxy.org/docs/desktop/addons/authentication-helper/session-mgmt-id/ ](https://www.zaproxy.org/docs/desktop/addons/authentication-helper/session-mgmt-id/)



#### Source ID: 3

### [ Tech Detected - Apache HTTP Server ](https://www.zaproxy.org/docs/alerts/10004/)



##### Informational (Medium)

### Description

The following "Web servers" technology was identified: Apache HTTP Server.
Described as:
Apache is a free and open-source cross-platform web server software.

* URL: http://192.168.1.120/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Apache/2.4.65`
  * Other Info: `The following CPE is associated with the identified tech: cpe:2.3:a:apache:http_server:*:*:*:*:*:*:*:*
The following version(s) is/are associated with the identified tech: 2.4.65`


Instances: 1

### Solution



### Reference


* [ https://httpd.apache.org/ ](https://httpd.apache.org/)



#### WASC Id: 13

#### Source ID: 4

### [ Tech Detected - Debian ](https://www.zaproxy.org/docs/alerts/10004/)



##### Informational (Medium)

### Description

The following "Operating systems" technology was identified: Debian.
Described as:
Debian is a Linux software which is a free open-source software.

* URL: http://192.168.1.120/wp-includes/blocks/navigation/style.min.css%3Fver=6.8.3

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Debian`
  * Other Info: `The following CPE is associated with the identified tech: cpe:2.3:o:debian:debian_linux:*:*:*:*:*:*:*:*
`


Instances: 1

### Solution



### Reference


* [ https://debian.org ](https://debian.org)



#### WASC Id: 13

#### Source ID: 4

### [ Tech Detected - Gravatar ](https://www.zaproxy.org/docs/alerts/10004/)



##### Informational (Medium)

### Description

The following "Miscellaneous" technology was identified: Gravatar.
Described as:
Gravatar is a service for providing globally unique avatars.

* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `<img alt='A WordPress Commenter Avatar' src='https://secure.gravatar.com/avatar/8e1606e6fba450a9362af43874c1b2dfad34c782e33d0a51e1b46c18a2a567dd?s=50&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/`
  * Other Info: ``


Instances: 1

### Solution



### Reference


* [ https://gravatar.com ](https://gravatar.com)



#### WASC Id: 13

#### Source ID: 4

### [ Tech Detected - PHP ](https://www.zaproxy.org/docs/alerts/10004/)



##### Informational (Medium)

### Description

The following "Programming languages" technology was identified: PHP.
Described as:
PHP is a general-purpose scripting language used for web development.

* URL: http://192.168.1.120/xmlrpc.php%3Frsd

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `.php?`
  * Other Info: `The following CPE is associated with the identified tech: cpe:2.3:a:php:php:*:*:*:*:*:*:*:*
`


Instances: 1

### Solution



### Reference


* [ https://php.net ](https://php.net)



#### WASC Id: 13

#### Source ID: 4

### [ Tech Detected - RSS ](https://www.zaproxy.org/docs/alerts/10004/)



##### Informational (Medium)

### Description

The following "Miscellaneous" technology was identified: RSS.
Described as:
RSS is a family of web feed formats used to publish frequently updated works—such as blog entries, news headlines, audio, and video—in a standardized format.

* URL: http://192.168.1.120/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `application/rss+xml`
  * Other Info: ``


Instances: 1

### Solution



### Reference


* [ https://www.rssboard.org/rss-specification ](https://www.rssboard.org/rss-specification)



#### WASC Id: 13

#### Source ID: 4

### [ Tech Detected - Underscore.js ](https://www.zaproxy.org/docs/alerts/10004/)



##### Informational (Medium)

### Description

The following "JavaScript libraries" technology was identified: Underscore.js.
Described as:
Underscore.js is a JavaScript library which provides utility functions for common programming tasks. It is comparable to features provided by Prototype.js and the Ruby language, but opts for a functional programming design instead of extending object prototypes.

* URL: http://192.168.1.120/wp-login.php%3Freauth=1&redirect_to=http%253A%252F%252F192.168.1.120%252Fwp-admin%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `underscore.min.js?ver=1.13.7`
  * Other Info: `The following version(s) is/are associated with the identified tech: 1.13.7`


Instances: 1

### Solution



### Reference


* [ https://underscorejs.org ](https://underscorejs.org)



#### WASC Id: 13

#### Source ID: 4

### [ Tech Detected - WordPress ](https://www.zaproxy.org/docs/alerts/10004/)



##### Informational (Medium)

### Description

The following "CMS, Blogs" technology was identified: WordPress.
Described as:
WordPress is a free and open-source content management system written in PHP and paired with a MySQL or MariaDB database. Features include a plugin architecture and a template system.

* URL: http://192.168.1.120/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `rel="https://api.w.org/"`
  * Other Info: `The following CPE is associated with the identified tech: cpe:2.3:a:wordpress:wordpress:*:*:*:*:*:*:*:*
`


Instances: 1

### Solution



### Reference


* [ https://wordpress.org ](https://wordpress.org)



#### WASC Id: 13

#### Source ID: 4

### [ Tech Detected - jQuery ](https://www.zaproxy.org/docs/alerts/10004/)



##### Informational (Medium)

### Description

The following "JavaScript libraries" technology was identified: jQuery.
Described as:
jQuery is a JavaScript library which is a free, open-source software designed to simplify HTML DOM tree traversal and manipulation, as well as event handling, CSS animation, and Ajax.

* URL: http://192.168.1.120/wp-login.php%3Freauth=1&redirect_to=http%253A%252F%252F192.168.1.120%252Fwp-admin%252F

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `jquery`
  * Other Info: `The following CPE is associated with the identified tech: cpe:2.3:a:jquery:jquery:*:*:*:*:*:*:*:*
`


Instances: 1

### Solution



### Reference


* [ https://jquery.com ](https://jquery.com)



#### WASC Id: 13

#### Source ID: 4

### [ User Agent Fuzzer ](https://www.zaproxy.org/docs/alerts/10104/)



##### Informational (Medium)

### Description

Check for differences in response based on fuzzed User Agent (eg. mobile sites, access as a Search Engine Crawler). Compares the response statuscode and the hashcode of the response body with the original response.

* URL: http://192.168.1.120/%3Fp=2

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/%3Fp=2

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/%3Fp=2

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/%3Fp=2

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/%3Fp=2

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/%3Fp=2

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/%3Fp=2

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/%3Fp=2

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/%3Fp=2

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/%3Fp=2

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/%3Fp=2

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/%3Fp=2

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/embed/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/author/cyberarenauser/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/comments/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/comments/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/comments/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/comments/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/comments/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/comments/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/comments/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/comments/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/comments/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/comments/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/comments/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/comments/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/embed/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/sample-page/feed

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Fformat=xml&url=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Fformat=xml&url=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Fformat=xml&url=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Fformat=xml&url=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Fformat=xml&url=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Fformat=xml&url=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Fformat=xml&url=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Fformat=xml&url=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Fformat=xml&url=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Fformat=xml&url=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Fformat=xml&url=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Fformat=xml&url=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Furl=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Furl=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Furl=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Furl=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Furl=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Furl=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Furl=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Furl=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Furl=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Furl=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Furl=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/index.php/wp-json/oembed/1.0/embed%3Furl=http%253A%252F%252F192.168.1.120%252Findex.php%252F2025%252F11%252F11%252Fhello-world%252F

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/js

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/js

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/js

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/js

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/js

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/js

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/js

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/js

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/js

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/js

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/js

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-admin/js

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts/manrope

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts/manrope

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts/manrope

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts/manrope

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts/manrope

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts/manrope

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts/manrope

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts/manrope

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts/manrope

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts/manrope

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts/manrope

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/fonts/manrope

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/images

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/images

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/images

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/images

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/images

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/images

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/images

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/images

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/images

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/images

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/images

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-content/themes/twentytwentyfive/assets/images

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/navigation

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/navigation

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/navigation

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/navigation

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/navigation

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/navigation

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/navigation

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/navigation

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/navigation

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/navigation

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/navigation

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/navigation

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/paragraph

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/paragraph

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/paragraph

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/paragraph

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/paragraph

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/paragraph

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/paragraph

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/paragraph

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/paragraph

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/paragraph

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/paragraph

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/paragraph

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/quote

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/quote

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/quote

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/quote

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/quote

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/quote

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/quote

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/quote

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/quote

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/quote

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/quote

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/blocks/quote

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist/block-library

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist/block-library

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist/block-library

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist/block-library

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist/block-library

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist/block-library

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist/block-library

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist/block-library

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist/block-library

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist/block-library

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist/block-library

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/css/dist/block-library

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/images

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/images

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/images

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/images

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/images

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/images

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/images

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/images

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/images

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/images

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/images

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/images

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library/navigation

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library/navigation

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library/navigation

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library/navigation

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library/navigation

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library/navigation

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library/navigation

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library/navigation

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library/navigation

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library/navigation

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library/navigation

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/block-library/navigation

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/interactivity

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/interactivity

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/interactivity

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/interactivity

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/interactivity

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/interactivity

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/interactivity

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/interactivity

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/interactivity

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/interactivity

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/interactivity

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-includes/js/dist/script-modules/interactivity

  * Method: `GET`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-comments-post.php

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-comments-post.php

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-comments-post.php

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-comments-post.php

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Trident/7.0; rv:11.0) like Gecko`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-comments-post.php

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.109.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-comments-post.php

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-comments-post.php

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:93.0) Gecko/20100101 Firefox/91.0`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-comments-post.php

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-comments-post.php

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (compatible; Yahoo! Slurp; http://help.yahoo.com/help/us/ysearch/slurp)`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-comments-post.php

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-comments-post.php

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `Mozilla/5.0 (iPhone; U; CPU iPhone OS 3_0 like Mac OS X; en-us) AppleWebKit/528.18 (KHTML, like Gecko) Version/4.0 Mobile/7A341 Safari/528.16`
  * Evidence: ``
  * Other Info: ``
* URL: http://192.168.1.120/wp-comments-post.php

  * Method: `POST`
  * Parameter: `Header User-Agent`
  * Attack: `msnbot/1.1 (+http://search.msn.com/msnbot.htm)`
  * Evidence: ``
  * Other Info: ``


Instances: 540

### Solution



### Reference


* [ https://owasp.org/wstg ](https://owasp.org/wstg)



#### Source ID: 1

### [ User Controllable HTML Element Attribute (Potential XSS) ](https://www.zaproxy.org/docs/alerts/10031/)



##### Informational (Low)

### Description

This check looks at user-supplied input in query string parameters and POST data to identify where certain HTML attribute values might be controlled. This provides hot-spot detection for XSS (cross-site scripting) that will require further review by a security analyst to determine exploitability.

* URL: http://192.168.1.120/index.php/2025/11/11/hello-world/%3Freplytocom=1

  * Method: `GET`
  * Parameter: `replytocom`
  * Attack: ``
  * Evidence: ``
  * Other Info: `User-controlled HTML attribute values were found. Try injecting special characters to see if XSS might be possible. The page at the following URL:

http://192.168.1.120/index.php/2025/11/11/hello-world/?replytocom=1

appears to include user input in:
a(n) [meta] tag [content] attribute

The user input found was:
replytocom=1

The user-controlled value was:
width=device-width, initial-scale=1`
* URL: http://192.168.1.120/wp-login.php%3Faction=lostpassword

  * Method: `GET`
  * Parameter: `action`
  * Attack: ``
  * Evidence: ``
  * Other Info: `User-controlled HTML attribute values were found. Try injecting special characters to see if XSS might be possible. The page at the following URL:

http://192.168.1.120/wp-login.php?action=lostpassword

appears to include user input in:
a(n) [form] tag [id] attribute

The user input found was:
action=lostpassword

The user-controlled value was:
lostpasswordform`
* URL: http://192.168.1.120/wp-login.php%3Faction=lostpassword

  * Method: `GET`
  * Parameter: `action`
  * Attack: ``
  * Evidence: ``
  * Other Info: `User-controlled HTML attribute values were found. Try injecting special characters to see if XSS might be possible. The page at the following URL:

http://192.168.1.120/wp-login.php?action=lostpassword

appears to include user input in:
a(n) [form] tag [name] attribute

The user input found was:
action=lostpassword

The user-controlled value was:
lostpasswordform`
* URL: http://192.168.1.120/wp-login.php%3Freauth=1&redirect_to=http%253A%252F%252F192.168.1.120%252Fwp-admin%252F

  * Method: `GET`
  * Parameter: `redirect_to`
  * Attack: ``
  * Evidence: ``
  * Other Info: `User-controlled HTML attribute values were found. Try injecting special characters to see if XSS might be possible. The page at the following URL:

http://192.168.1.120/wp-login.php?reauth=1&redirect_to=http%3A%2F%2F192.168.1.120%2Fwp-admin%2F

appears to include user input in:
a(n) [a] tag [href] attribute

The user input found was:
redirect_to=http://192.168.1.120/wp-admin/

The user-controlled value was:
http://192.168.1.120/`
* URL: http://192.168.1.120/wp-login.php%3Freauth=1&redirect_to=http%253A%252F%252F192.168.1.120%252Fwp-admin%252F

  * Method: `GET`
  * Parameter: `redirect_to`
  * Attack: ``
  * Evidence: ``
  * Other Info: `User-controlled HTML attribute values were found. Try injecting special characters to see if XSS might be possible. The page at the following URL:

http://192.168.1.120/wp-login.php?reauth=1&redirect_to=http%3A%2F%2F192.168.1.120%2Fwp-admin%2F

appears to include user input in:
a(n) [input] tag [value] attribute

The user input found was:
redirect_to=http://192.168.1.120/wp-admin/

The user-controlled value was:
http://192.168.1.120/wp-admin/`
* URL: http://192.168.1.120/wp-login.php%3Freauth=1&redirect_to=http%253A%252F%252F192.168.1.120%252Fwp-admin%252F

  * Method: `GET`
  * Parameter: `redirect_to`
  * Attack: ``
  * Evidence: ``
  * Other Info: `User-controlled HTML attribute values were found. Try injecting special characters to see if XSS might be possible. The page at the following URL:

http://192.168.1.120/wp-login.php?reauth=1&redirect_to=http%3A%2F%2F192.168.1.120%2Fwp-admin%2F

appears to include user input in:
a(n) [link] tag [href] attribute

The user input found was:
redirect_to=http://192.168.1.120/wp-admin/

The user-controlled value was:
http://192.168.1.120/wp-admin/load-styles.php?c=0&dir=ltr&load%5bchunk_0%5d=dashicons,buttons,forms,l10n,login&ver=6.8.3`
* URL: http://192.168.1.120/wp-login.php%3Freauth=1&redirect_to=http%253A%252F%252F192.168.1.120%252Fwp-admin%252F

  * Method: `GET`
  * Parameter: `redirect_to`
  * Attack: ``
  * Evidence: ``
  * Other Info: `User-controlled HTML attribute values were found. Try injecting special characters to see if XSS might be possible. The page at the following URL:

http://192.168.1.120/wp-login.php?reauth=1&redirect_to=http%3A%2F%2F192.168.1.120%2Fwp-admin%2F

appears to include user input in:
a(n) [script] tag [src] attribute

The user input found was:
redirect_to=http://192.168.1.120/wp-admin/

The user-controlled value was:
http://192.168.1.120/wp-admin/js/password-strength-meter.min.js?ver=6.8.3`
* URL: http://192.168.1.120/wp-login.php%3Freauth=1&redirect_to=http%253A%252F%252F192.168.1.120%252Fwp-admin%252F

  * Method: `GET`
  * Parameter: `redirect_to`
  * Attack: ``
  * Evidence: ``
  * Other Info: `User-controlled HTML attribute values were found. Try injecting special characters to see if XSS might be possible. The page at the following URL:

http://192.168.1.120/wp-login.php?reauth=1&redirect_to=http%3A%2F%2F192.168.1.120%2Fwp-admin%2F

appears to include user input in:
a(n) [script] tag [src] attribute

The user input found was:
redirect_to=http://192.168.1.120/wp-admin/

The user-controlled value was:
http://192.168.1.120/wp-admin/js/user-profile.min.js?ver=6.8.3`
* URL: http://192.168.1.120/wp-login.php%3Freauth=1&redirect_to=http%253A%252F%252F192.168.1.120%252Fwp-admin%252F

  * Method: `GET`
  * Parameter: `redirect_to`
  * Attack: ``
  * Evidence: ``
  * Other Info: `User-controlled HTML attribute values were found. Try injecting special characters to see if XSS might be possible. The page at the following URL:

http://192.168.1.120/wp-login.php?reauth=1&redirect_to=http%3A%2F%2F192.168.1.120%2Fwp-admin%2F

appears to include user input in:
a(n) [script] tag [src] attribute

The user input found was:
redirect_to=http://192.168.1.120/wp-admin/

The user-controlled value was:
http://192.168.1.120/wp-admin/load-scripts.php?c=0&load%5bchunk_0%5d=clipboard,jquery-core,jquery-migrate,zxcvbn-async,wp-hooks&ver=6.8.3`
* URL: http://192.168.1.120/wp-login.php

  * Method: `POST`
  * Parameter: `redirect_to`
  * Attack: ``
  * Evidence: ``
  * Other Info: `User-controlled HTML attribute values were found. Try injecting special characters to see if XSS might be possible. The page at the following URL:

http://192.168.1.120/wp-login.php

appears to include user input in:
a(n) [a] tag [href] attribute

The user input found was:
redirect_to=http://192.168.1.120/wp-admin/

The user-controlled value was:
http://192.168.1.120/`
* URL: http://192.168.1.120/wp-login.php

  * Method: `POST`
  * Parameter: `redirect_to`
  * Attack: ``
  * Evidence: ``
  * Other Info: `User-controlled HTML attribute values were found. Try injecting special characters to see if XSS might be possible. The page at the following URL:

http://192.168.1.120/wp-login.php

appears to include user input in:
a(n) [input] tag [value] attribute

The user input found was:
redirect_to=http://192.168.1.120/wp-admin/

The user-controlled value was:
http://192.168.1.120/wp-admin/`
* URL: http://192.168.1.120/wp-login.php

  * Method: `POST`
  * Parameter: `redirect_to`
  * Attack: ``
  * Evidence: ``
  * Other Info: `User-controlled HTML attribute values were found. Try injecting special characters to see if XSS might be possible. The page at the following URL:

http://192.168.1.120/wp-login.php

appears to include user input in:
a(n) [link] tag [href] attribute

The user input found was:
redirect_to=http://192.168.1.120/wp-admin/

The user-controlled value was:
http://192.168.1.120/wp-admin/load-styles.php?c=0&dir=ltr&load%5bchunk_0%5d=dashicons,buttons,forms,l10n,login&ver=6.8.3`
* URL: http://192.168.1.120/wp-login.php

  * Method: `POST`
  * Parameter: `redirect_to`
  * Attack: ``
  * Evidence: ``
  * Other Info: `User-controlled HTML attribute values were found. Try injecting special characters to see if XSS might be possible. The page at the following URL:

http://192.168.1.120/wp-login.php

appears to include user input in:
a(n) [script] tag [src] attribute

The user input found was:
redirect_to=http://192.168.1.120/wp-admin/

The user-controlled value was:
http://192.168.1.120/wp-admin/js/password-strength-meter.min.js?ver=6.8.3`
* URL: http://192.168.1.120/wp-login.php

  * Method: `POST`
  * Parameter: `redirect_to`
  * Attack: ``
  * Evidence: ``
  * Other Info: `User-controlled HTML attribute values were found. Try injecting special characters to see if XSS might be possible. The page at the following URL:

http://192.168.1.120/wp-login.php

appears to include user input in:
a(n) [script] tag [src] attribute

The user input found was:
redirect_to=http://192.168.1.120/wp-admin/

The user-controlled value was:
http://192.168.1.120/wp-admin/js/user-profile.min.js?ver=6.8.3`
* URL: http://192.168.1.120/wp-login.php

  * Method: `POST`
  * Parameter: `redirect_to`
  * Attack: ``
  * Evidence: ``
  * Other Info: `User-controlled HTML attribute values were found. Try injecting special characters to see if XSS might be possible. The page at the following URL:

http://192.168.1.120/wp-login.php

appears to include user input in:
a(n) [script] tag [src] attribute

The user input found was:
redirect_to=http://192.168.1.120/wp-admin/

The user-controlled value was:
http://192.168.1.120/wp-admin/load-scripts.php?c=0&load%5bchunk_0%5d=clipboard,jquery-core,jquery-migrate,zxcvbn-async,wp-hooks&ver=6.8.3`
* URL: http://192.168.1.120/wp-login.php

  * Method: `POST`
  * Parameter: `rememberme`
  * Attack: ``
  * Evidence: ``
  * Other Info: `User-controlled HTML attribute values were found. Try injecting special characters to see if XSS might be possible. The page at the following URL:

http://192.168.1.120/wp-login.php

appears to include user input in:
a(n) [input] tag [value] attribute

The user input found was:
rememberme=forever

The user-controlled value was:
forever`
* URL: http://192.168.1.120/wp-login.php

  * Method: `POST`
  * Parameter: `wp-submit`
  * Attack: ``
  * Evidence: ``
  * Other Info: `User-controlled HTML attribute values were found. Try injecting special characters to see if XSS might be possible. The page at the following URL:

http://192.168.1.120/wp-login.php

appears to include user input in:
a(n) [input] tag [value] attribute

The user input found was:
wp-submit=Log In

The user-controlled value was:
log in`
* URL: http://192.168.1.120/wp-login.php%3Faction=lostpassword

  * Method: `POST`
  * Parameter: `action`
  * Attack: ``
  * Evidence: ``
  * Other Info: `User-controlled HTML attribute values were found. Try injecting special characters to see if XSS might be possible. The page at the following URL:

http://192.168.1.120/wp-login.php?action=lostpassword

appears to include user input in:
a(n) [form] tag [id] attribute

The user input found was:
action=lostpassword

The user-controlled value was:
lostpasswordform`
* URL: http://192.168.1.120/wp-login.php%3Faction=lostpassword

  * Method: `POST`
  * Parameter: `action`
  * Attack: ``
  * Evidence: ``
  * Other Info: `User-controlled HTML attribute values were found. Try injecting special characters to see if XSS might be possible. The page at the following URL:

http://192.168.1.120/wp-login.php?action=lostpassword

appears to include user input in:
a(n) [form] tag [name] attribute

The user input found was:
action=lostpassword

The user-controlled value was:
lostpasswordform`
* URL: http://192.168.1.120/wp-login.php%3Faction=lostpassword

  * Method: `POST`
  * Parameter: `user_login`
  * Attack: ``
  * Evidence: ``
  * Other Info: `User-controlled HTML attribute values were found. Try injecting special characters to see if XSS might be possible. The page at the following URL:

http://192.168.1.120/wp-login.php?action=lostpassword

appears to include user input in:
a(n) [input] tag [value] attribute

The user input found was:
user_login=ZAP

The user-controlled value was:
zap`
* URL: http://192.168.1.120/wp-login.php%3Faction=lostpassword

  * Method: `POST`
  * Parameter: `wp-submit`
  * Attack: ``
  * Evidence: ``
  * Other Info: `User-controlled HTML attribute values were found. Try injecting special characters to see if XSS might be possible. The page at the following URL:

http://192.168.1.120/wp-login.php?action=lostpassword

appears to include user input in:
a(n) [input] tag [value] attribute

The user input found was:
wp-submit=Get New Password

The user-controlled value was:
get new password`


Instances: 21

### Solution

Validate all input and sanitize output it before writing to any HTML attributes.

### Reference


* [ https://cheatsheetseries.owasp.org/cheatsheets/Input_Validation_Cheat_Sheet.html ](https://cheatsheetseries.owasp.org/cheatsheets/Input_Validation_Cheat_Sheet.html)


#### CWE Id: [ 20 ](https://cwe.mitre.org/data/definitions/20.html)


#### WASC Id: 20

#### Source ID: 3


