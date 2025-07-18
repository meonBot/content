---
title: Symbol.matchAll
short-title: matchAll
slug: Web/JavaScript/Reference/Global_Objects/Symbol/matchAll
page-type: javascript-static-data-property
browser-compat: javascript.builtins.Symbol.matchAll
sidebar: jsref
---

The **`Symbol.matchAll`** static data property represents the [well-known symbol](/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol#well-known_symbols) `Symbol.matchAll`. The {{jsxref("String.prototype.matchAll()")}} method looks up this symbol on its first argument for the method that returns an iterator, that yields matches of the current object against a string.

For more information, see [`RegExp.prototype[Symbol.matchAll]()`](/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/Symbol.matchAll) and {{jsxref("String.prototype.matchAll()")}}.

{{InteractiveExample("JavaScript Demo: Symbol.matchAll")}}

```js interactive-example
const re = /\d+/g;
const str = "2016-01-02|2019-03-07";
const result = re[Symbol.matchAll](str);

console.log(Array.from(result, (x) => x[0]));
// Expected output: Array ["2016", "01", "02", "2019", "03", "07"]
```

## Value

The well-known symbol `Symbol.matchAll`.

{{js_property_attributes(0, 0, 0)}}

## Examples

### Using Symbol.matchAll

```js
const str = "2016-01-02|2019-03-07";

const numbers = {
  *[Symbol.matchAll](str) {
    for (const n of str.matchAll(/\d+/g)) yield n[0];
  },
};

console.log(Array.from(str.matchAll(numbers)));
// ["2016", "01", "02", "2019", "03", "07"]
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [Polyfill of `Symbol.matchAll` in `core-js`](https://github.com/zloirock/core-js#ecmascript-symbol)
- [es-shims polyfill of `Symbol.matchAll`](https://www.npmjs.com/package/string.prototype.matchall)
- {{jsxref("Symbol.match")}}
- {{jsxref("Symbol.replace")}}
- {{jsxref("Symbol.search")}}
- {{jsxref("Symbol.split")}}
- {{jsxref("String.prototype.matchAll()")}}
- [`RegExp.prototype[Symbol.matchAll]()`](/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/Symbol.matchAll)
