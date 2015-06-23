## Introduction

- definition

	+ not authored by the content provider
	+ served from external servers that aren't controlled by the content provider
	+ written with the intention that it's to be executed as part of a content provider's website

- use cases

	+ embedded widgets
	+ analytics and metrics
	+ web servics API wrappers


## Distributing and Loading Your Application

- configure development environment

	+ hosts
	+ Apache

- including scripts on a publisher's web page

	+ `defer` attribute of `<script>` in HTML4

		* `defer="defer"` in XHTML
		* ignored in Opera

	+ `async` attribute in HTML5

	+ dynamic `<script>` tag insertion

		* should set `src.async = true`, otherwise, Opera & Firefox will attempt to preserve execution order
		* inserting before a found script element

- the initial script file

	+ aliasing `window`, `document` & `undefined`
	+ basic application flow: [load supporting files] -> [identify product] -> [fetch product data] -> [render output]

- loading additional files

	+ `loadScript(url, callback)`
	+ namespacing & `jQuery.noConflict`
	+ LABjs, RequireJS

- protocol-relative urls

	+ the server should be configured to handle both HTTP & HTTPS
	+ when viewing using file:/// protocol, it will resolve to a URL that (probably) doesn't exist
	+ some resources (like `<link>` tags) will load twice when using protocol-relative URLs on HTTPS pages

- passing script arguments

	+ using the query string

		* can send information to the servers
		* makes caching JavaScript files difficult

	+ using the fragment identifier (hash part)

	+ using custom data attributes (data-* introduced in HTML5 and supported in all common web browsers)

	+ using global variables

		* namespace the script parameter
		* asynchronous script includes don't preserve execution order, so race conditions may occur
		* use global variable arrays to avoid collisions


## Rendering HTML and CSS

- outputing HTML

	+ using document.write

		only works in conjunction with a standard (blocking) script include

	+ appending tp a known location

		* JavaScript Templating Library