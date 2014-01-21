##Understanding JavaScript Events##

- JavaScript events handlers don't run until the the thread is free.

- <del>`console.log` in WebKit behaves asynchoronously</del> (Not true in Chrome 32.0/Ubuntu 13.10, as I tested); Node's `console.log`, on the other hand, is strictly synchronous.

- Timers are unspecified in JavaScript (it's a DOM specification). In HTML5, the minimum delay is 4ms. Node does not have this limitation; however, according to the author's test, `setTimeout(f, 0)` is still about 100 times slower than `process.nextTick`. Some alternatives to get finer-grained timing:

    + `window.postMessage`, see http://dbaron.org/log/20100309-faster-timeouts

    + `process.nextTick` in Node.

    + `requestAnimationFrame`