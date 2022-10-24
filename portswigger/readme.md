<h1 align="center">Portswigger</h1>
<p align="center">This page is about portswigger.net</p>

See more:

https://portswigger.net/web-security

## Variations of Cross-site request forgery (CSRF)
* CSRF where token validation depends on request method
* CSRF where token validation depends on token being present
* CSRF where token is not tied to user session
* CSRF where token is tied to non-session cookie
* CSRF where token is duplicated in cookie
* CSRF where Referer validation depends on header being present
* CSRF with broken Referer validation

### Two actions in just one open
##### With CRLF (%0D%0A) Injection: 
_When a browser sends a request to a web server, the web server answers back with a response containing both the HTTP response headers and the actual website content, i.e. the response body. The HTTP headers and the HTML response (the website content) are separated by a specific combination of special characters, namely a carriage return and a line feed. For short they are also known as CRLF(%0D%0A)._

See more: https://book.hacktricks.xyz/pentesting-web/crlf-0d-0a

%3B = ";"

As the content of "src" attribute is invalid (it set a cookie on client's browser), the content of "onerror" (a submit) will execute in sequence.

```html
<img src="https://URL/?search=test%0D%0ASet-Cookie:%20csrfKey=YOUR-KEY%3b%20SameSite=None" --action #1 - set a cookie
  onerror="document.forms[0].submit()"> -- action #2 - submit
```
