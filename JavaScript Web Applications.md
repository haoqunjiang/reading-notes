## Deploying

- Increasing Performance: minimize the amount of HTTP requests
	+ concatenating scripts, combining CSS
	+ CSS sprites
	+ avoiding redirects (the most common: missing trailing slash(/) in a URL)
	+ `defer` & `async` attributes of `<script />` label (may cause dependency errors)

- Caching
	+ `Expires` header for static resources (append a query parameter in the URL to force refresh)
	+ `Cache-Control` header
		* `max-age`
		* `public`
		* `no-store`
		* `must-revalidate`
	+ `Last-Modified` (in response) & `If-Modified-Since` (in request) headers (the server can return a 304 not modifed status)
	+ Etags as  an alternative to `Last-Modified`, paried with `If-None-Match` (not recommended, as two separate severs in the same cluster will give different Etags for the same resource)

- Minification
	+ YUI Compressor

- Gzip Compression
	+ client side: `Accept-Encoding: gzip, deflate`
	+ server side: `Content-Encoding: gzip`
	+ rule of thumb: gzip any text responses

- Using a CDN
	+ use a relative URL without a scheme so that the file will be fetched using the same protocol as the host page (e.g. `<script src="//ajax.googleapis.com/ajax/libs/jquery/1.10.2/jquery.min.js"></script>`)

- Auditors
	+ YSlow
	+ Chrome & Safari's built-in auditors


## The Spine Library

http://spinejs.com/docs/example
