Reduced test environment to debug an annoying Safari bug which makes it so
that the 'Vary' response header is not respected.

Safari, unlike other browsers, will not make two network requests when XHRs go out two the same URL from two iframes. Even if the HTTP response includes "Vary: Origin".

If the response also only does `Access-Control-Allow-Origin: onedomain`, then reusing from cache will block one of the windows from seeing the response.

# Usage

* Serve this dir at `some port`
* Serve this dir at localhost:8081 (for the iframe)
* Access `some port`/index.html

