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
	- all web browsers in common use today support gzip

5. Put Stylesheets at the Top

	- The problem with putting the stylesheets near the bottom of the document is that it prohibits progressive rendering in many browsers (especially IE)

	  NOTE: [can't reproduce this behavior](http://stackoverflow.com/questions/19644650/modern-browsers-progressive-rendering-anc-css-at-bottom)

	- prefer `<link>` than inline `@import` as the latter may cause the stylesheets to be downloaded last and the result in Flash of Unstyled Content (FOUC), besides it causes the stylesheets to be downloaded sequentially (all particularly in IE, I can't reproduce that in Chrome)

	  for more information, refer to [this article](http://www.stevesouders.com/blog/2009/04/09/dont-use-import/)

6. Put Scripts at the Bottom

	- HTML/1.1 specification suggests that browsers download two components in parallel per hostname (while most browsers set a much larger upper bound)

		* can simply use CNAMEs (DNS aliases) to split the components across multiple hostnames
		* too many parallel downloads can degrade performance depending on the bandwidth and CPU speed

	- everything below the script won't render until the script is loaded

	- all components below the script don't start downloading until the script is done

	- in Firefox even *deferred scripts* block rendering and parallel downloads (but Okay in both IE and Chrome)

7. Avoid CSS Expressions

8. Make JavaScript and CSS External