# CORS

> `CORS`(or Cross-Origin Resource Sharing) is an HTTP-header based mechanism that allows a server to indicate any origin(like domain or port) other than it's own from which a browser should permit loading resources.<br> The CORS mechanism supports secure cross-origin requests and data transfers between browsers and servers.

#

- Requests that `CORS` use:

  - Invocation of the XMLHttpRequest or Fetch API's.
  - Web Fonts for cross-domain font usage.
  - WebGL textures.
  - Images/video frames drawn to a canvas.
  - CSS Shapes from images.

#
[**Vulnerabilities arising from CORS configuration issues:**](https://portswigger.net/web-security/cors)
- Websites that are using CORS to `allow access from subdomains and trusted third parties`. Their implementation of CORS may contain mistakes or be overly lenient to ensure that everything works, and this can result in exploitable vulnerabilities.
- Mistakes often arise when `implementing CORS origin whitelists`. Some organizations decide to allow access from all their subdomains and some applications allow access from various other organizations. These rules are often implemented by matching URL prefixes or suffixes, or using regular expressions. Any mistakes in the implementation can lead to access being granted to unintended external domains.
- `Exploiting XSS via CORS trust relationships` -> If a website trusts an origin that is vulnerable to cross-site scripting (XSS), then an attacker could exploit the XSS to inject some JavaScript that uses CORS to retrieve sensitive information from the site that trusts the vulnerable application.
- `Breaking TLS with poorly configured CORS` -> Intercepting a victim user's traffic can exploit the CORS configuration to compromise the victim's interaction with the application.
- `Intranets and CORS without credentials` -> Can be performed from the external site that uses the victim's browser as a proxy for accessing intranet resources.

#
**`Overview`** -> The CORS standard works by adding new HTTP headers that let servers describe which origin are premitted to read that information from the web browser(like frontend JS code from accessing responses for cross-origin request).


