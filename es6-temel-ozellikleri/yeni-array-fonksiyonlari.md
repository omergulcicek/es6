# Yeni array fonksiyonları

## `Array.prototype.indexOf`tan `Array.prototype.findIndex`a:

`NaN`ın tespit edilebilmesi:

```js
const arr = ['a', NaN];

arr.indexOf(NaN); // -1
arr.findIndex(x => Number.isNaN(x)); // 1
```

Bunun yanı sıra, yeni `Number.isNaN()`, `NaN`ı saptamak için güvenli bir yoldur.

```js
> isNaN('abc')
true
> Number.isNaN('abc')
false
```

## `Array.prototype.slice()`tan `Array.from()`a:

ES5'te, Array benzeri nesneleri dizilere dönüştürmek için `Array.prototype.slice()` yöntemi kullanıldı. ES6'da `Array.from()` fonksiyonuna sahibiz:

```js
var arr1 = Array.prototype.slice.call(arguments); // ES5
const arr2 = Array.from(arguments); // ES6
```

Bir değer yinelenebilirse, spread operatörünü (...) bir Arraye dönüştürmek için de kullanabilirsiniz:

```js
const arr1 = [...'abc'];
    // ['a', 'b', 'c']
const arr2 = [...new Set().add('a').add('b')];
    // ['a', 'b']
```

## `apply()`tan `Array.prototype.fill()`a:

```js
var arr1 = Array.apply(null, new Array(2));
    // [undefined, undefined]
```

ES6'da `fill()` daha basit bir alternatiftir:

```js
const arr2 = new Array(2).fill(undefined);
    // [undefined, undefined]
```

`fill()` fonksiyonunun daha kullanışlı olduğu bir başka örnek:


```js
// ES5
var arr3 = Array.apply(null, new Array(2))
    .map(function (x) { return 'x' });
    // ['x', 'x']

// ES6
const arr4 = new Array(2).fill('x');
    // ['x', 'x']
```

<a href="https://omergulcicek.github.io/es6/es6-temel-ozellikleri/commonjs-modullerinden-es6-modullerine">Sıradaki Konu: CommonJS modüllerinden ES6 modüllerine</a>
