# snap-shot

> Jest-like snapshot feature for the rest of us

[![NPM][npm-icon] ][npm-url]

[![Build status][ci-image] ][ci-url]
[![semantic-release][semantic-image] ][semantic-url]
[![js-standard-style][standard-image]][standard-url]

## Why

I like [Jest snapshot](https://facebook.github.io/jest/blog/2016/07/27/jest-14.html)
idea and want it without the rest of Jest testing framework. This module is
JUST a single assertion method to be used in BDD frameworks (Mocha, Jasmine)

## Example

Install: `npm install --save-dev snap-shot`

```js
const snapshot = require('snap-shot')
it('is 42', () => {
  snapshot(42)
})
```

Run it first time with `mocha spec.js`.
This will create snapshots JSON values file inside `.snap-shot`.

```sh
$ mocha spec.js
$ cat .snap-shot/snap-shot.json
{
  "spec.js": {
    "is 42": 42
  }
}
```

Now modify the `spec.js` file

```js
const snapshot = require('snap-shot')
it('is 42', () => {
  snapshot(80)
})
```

```sh
$ mocha spec.js
1) is 42:
    Error: expected 42 got 80
```

## Related

* [chai-jest-snapshot](https://github.com/suchipi/chai-jest-snapshot) if
  you are using [Chai](http://chaijs.com/)

### Small print

Author: Gleb Bahmutov &lt;gleb.bahmutov@gmail.com&gt; &copy; 2017

* [@bahmutov](https://twitter.com/bahmutov)
* [glebbahmutov.com](http://glebbahmutov.com)
* [blog](http://glebbahmutov.com/blog)

License: MIT - do anything with the code, but don't blame me if it does not work.

Support: if you find any problems with this module, email / tweet /
[open issue](https://github.com/bahmutov/snap-shot/issues) on Github

## MIT License

Copyright (c) 2017 Gleb Bahmutov &lt;gleb.bahmutov@gmail.com&gt;

Permission is hereby granted, free of charge, to any person
obtaining a copy of this software and associated documentation
files (the "Software"), to deal in the Software without
restriction, including without limitation the rights to use,
copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the
Software is furnished to do so, subject to the following
conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES
OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT
HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY,
WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.

[npm-icon]: https://nodei.co/npm/snap-shot.svg?downloads=true
[npm-url]: https://npmjs.org/package/snap-shot
[ci-image]: https://travis-ci.org/bahmutov/snap-shot.svg?branch=master
[ci-url]: https://travis-ci.org/bahmutov/snap-shot
[semantic-image]: https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg
[semantic-url]: https://github.com/semantic-release/semantic-release
[standard-image]: https://img.shields.io/badge/code%20style-standard-brightgreen.svg
[standard-url]: http://standardjs.com/
