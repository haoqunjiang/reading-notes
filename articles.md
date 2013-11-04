## jQuery Source

- `jQuery.fn = jQuery.prototype`

- constructor
	+ without `new`
	+ `return new jQuery.fn.init( selector, context, rootjQuery );` using `new` to create a new scope each time, so that the `this` reference won't be confused
	+ `init()` returns `this`, which actually is a reference to the `jQuery` instance
	+ `jQuery.fn.init.prototype = jQuery.fn;` so that the instance and the prototype can share their methods

- `jQuery.extend = jQuery.fn.extend`
 	+ same implementation
 	+ when calling with different name, the `this` references are not the same


## Reverse AJAX
