1. Making Fewer HTTP Requests
	- Image Maps
		+ server-side
		+ client-side (html `<map></map>` tag)

	- CSS Sprites

		[CSS Sprites: Image Slicing’s Kiss of Death](http://alistapart.com/article/sprites)

	- Inline Images
		+ `data:[<mediatype>][;base64],<data>`
		+ possible size limitation
		+ the base64 ebcoding increasing the size of images, thus increasing the total download size
		+ won't be cached (alternative: inline CSS images)
		+ combined scripts and stylesheets

2. Use a Content Delivery Network

3. Add an Expire Header
	- `Expires: Thu, 15 Apr 2010 20:00:00 GMT` (HTTP Response)
	- `Cache-Control: max-age=315360000` (HTTP Response) (only HTTP 1.1, but all common web browsers support that so it's not even a problem)
    - any component that changes infrequently should include a far future `Expires` header
    - revving filenames to update

4. Gzip Components
	- `Accept-Encoding: gzip, deflate` (HTTP Request)
	- `Content-Encoding:: gzip` (HTTP Response)
	- gzip any text response (HTML documents, scripts, stylesheets, XML & JSON)
	- Proxy Caching: `Vary: Accept-Encoding` (HTTP Response) causing the proxy to cache multiple versions of the response, one for each value of the `Accept-Encoding` request header
	- all web browsers in comuse today support gzip