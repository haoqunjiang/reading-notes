## 1 Scope
## 2 Conformance


## 3 Normative references


- [ISO/IEC 10646:2003, Universal Multiple-Octet Coded Character Set (UCS)](http://www.iso.org/iso/catalogue_detail.htm?csnumber=39921)
- [ECMA-402, ECMAScript 2015 Internationalization API Specification](http://www.ecma-international.org/publications/standards/Ecma-402.htm)
- [ECMA-404, The JSON Data Interchange Format](http://www.ecma-international.org/publications/standards/Ecma-404.htm)


## 4 Overview


- ES is an OO language
- Need a host environment (for provisions for input/output interfaces), which is beyond the scope of this specification
- Originally designed to be a (Web) scripting language, now widely used as a general purpose programming language
- Some of the facilities are similar to those used in C, Java™, Self, and Scheme


### 4.1 Web Scripting


- A web browser as a host environment provides web page objects and events related to the page (which are defined in the DOM specification). Event driven means no need for a main program
- A web server provides server-side abstractions (objects representing requests, clients, and files; and mechanisms to lock and share data, etc.)


### 4.2 ECMAScript Overview


- ECMAScript is object-based: basic language and host facilities are provided by objects, and an ECMAScript program is a cluster of communicating objects
- Object properties are containers that hold
    + Primitive values: members of one of the following builtin-types:
        * `Undefined`
        * `Null`
        * `Boolean`
        * `Number`
        * `String`
        * `Symbol`
    + Other objects: members of the built-in type `Object`
    + Functions: callable objects
- Built-in objects:
    + Fundamental:
        * `Object`
        * `Function`
        * `Boolean`
        * `Symbol`
        * Various `Error` objects
     + Numerical:
         * `Math`
         * `Number`
         * `Date`
     + Text processing:
         * `String`
         * `RegExp`
     + Indexed collections of values:
         * Array
         * 9 kinds of Typed Arrays
     + Keyed collections
         * `Map`
         * `Set`
     + Objects supporting structured data:
         * `JSON`
         * `ArrayBuffer`
         * `DataView`
     + Objects supporting control abstractions:
         * generator functions
         * `Promise`
     + Reflection ojects
         * `Proxy`
         * `Reflect`
- Built-in operators
- Modules
- Intentionally resembles Java syntax


#### 4.2.1 Objects


- ES is not class-based
- Ways to create objects:
    + Object literal notation
    + Via *constructor* function in `new` expressions
- *constructor* functions has a `prototype` property used to implement *prototype-based inheritance* and *shared properties*
- ES includes syntactic class definitions beginning with ES2015


#### 4.2.2 The Strict Variant of ECMAScript (a.k.a *strict mode*)


### 4.3 Terms and definitions
### 4.4 Organization of This Specification


## 5 Notational Conventions