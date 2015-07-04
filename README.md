# object-visit [![NPM version](https://badge.fury.io/js/object-visit.svg)](http://badge.fury.io/js/object-visit)

> Call the given method on each value in the given object.

## Install

Install with [npm](https://www.npmjs.com/)

```sh
$ npm i object-visit --save
```

## Usage

```js
var visit = require('object-visit');

var ctx = {
  data: {},
  set: function (key, value) {
    if (typeof key === 'object') {
      visit(ctx, 'set', key);
    } else {
      ctx.data[key] = value;
    }
  }
};

ctx.set('a', 'a');
ctx.set('b', 'b');
ctx.set('c', 'c');
ctx.set({d: {e: 'f'}});

console.log(ctx.data);
//=> {a: 'a', b: 'b', c: 'c', d: { e: 'f' }};
```

## Related projects

* [assign-deep](https://github.com/jonschlinkert/assign-deep): Deeply assign the enumerable properties of source objects to a destination object.
* [extend-shallow](https://github.com/jonschlinkert/extend-shallow): Extend an object with the properties of additional objects. node.js/javascript util.
* [get-value](https://github.com/jonschlinkert/get-value): Use property paths (`  a.b.c`) to get a nested value from an object.
* [has-value](https://github.com/jonschlinkert/has-value): Returns true if a value exists, false if empty. Works with deeply nested values using… [more](https://github.com/jonschlinkert/has-value)
* [set-value](https://github.com/jonschlinkert/set-value): Create nested values and any intermediaries using dot notation (`'a.b.c'`) paths.

## Running tests

Install dev dependencies:

```sh
$ npm i -d && npm test
```

## Contributing

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](https://github.com/jonschlinkert/object-visit/issues/new)

## Author

**Jon Schlinkert**

+ [github/jonschlinkert](https://github.com/jonschlinkert)
+ [twitter/jonschlinkert](http://twitter.com/jonschlinkert)

## License

Copyright © 2015 Jon Schlinkert
Released under the MIT license.

***

_This file was generated by [verb-cli](https://github.com/assemble/verb-cli) on July 04, 2015._