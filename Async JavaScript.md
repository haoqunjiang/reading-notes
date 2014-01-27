##Understanding JavaScript Events##

- JavaScript events handlers don't run until the the thread is free.


- <del>`console.log` in WebKit behaves asynchoronously</del> (Not true in Chrome 32.0/Ubuntu 13.10, as I tested);

  Node's `console.log`, on the other hand, is strictly synchronous.


- Timers are unspecified in JavaScript (it's a DOM specification). In HTML5, the minimum delay is 4ms. Node does not have this limitation; however, according to the author's test, `setTimeout(f, 0)` is still about 100 times slower than `process.nextTick`.

  Some alternatives to get finer-grained timing:

    + `window.postMessage`, see http://dbaron.org/log/20100309-faster-timeouts

    + `process.nextTick` in Node.

    + `requestAnimationFrame`

    + Web Worker

- Sometimes-Async Functions (**Be careful**)

    + jQuery DOM Ready

        * if DOM is already ready, then execute callback immediately
        * otherwise it's added to the callback queue

    + Aync Functions with Caching

    + Never define a potentially synchronous function that returns a value that might be useful in the callback

- Aync functions are run directly from the event queue. So, nesting functions won't show in the stack trace, neither can we catch errors from async callbacks with a try/catch block.

  So, callbacks in Node.js almost always take an error as their first argument, allowing the callback to decide how to handle it.

  Client-side JavaScript libraies are less consistent, but the most common pattern is for there to be seperate callbacks for success and failure.

- Handling Uncaught Exceptions

    + [Browsers] `window.onerror` (should return true to ignore all errors completely)

    + [Node.js] `process` object's `uncaughtException` event. (deprecated)

    + [Node.js] `domain`s

- Issac Schlueter advocated using `throw`s purely as `assert`-like constructs, a way of bringing applications to a halt when they're doing something completely unexpected.


##Distributing Events##

- PubSub (Publish/Subscribe)

  Examples:

    + DOM `object.onevent = ...`

    + W3C `addEventListener` / IE `attachEvent`

    + jQuery `on`

    + Node.js `EventEmitter`

  Easy to implement, but naive approaches will bring some pitfalls:

    + May blcok the thread and make the browser unresponsive if too many handlers are fire in sequence.

    + If events are emitted from event handlers, they can easily create an inifinite cycle.

  One possible solution:

        var tasks = [];
        setInterval(function() {
            var nextTask;
            if (nextTask = tasks.shift()) {
                nextTask();
            }
        }, 0);

- Evented Models