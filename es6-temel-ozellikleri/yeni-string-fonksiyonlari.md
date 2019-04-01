# Yeni string fonksiyonları

ECMAScript 6 standart kütüphanesi stringler için birkaç yeni yöntem sunar.

`indexOf`tan `startsWith`e:

```js
if (str.indexOf('x') === 0) {} // ES5
if (str.startsWith('x')) {} // ES6
```

`indexOf`tan `endsWith`e:

```js
function endsWith(str, suffix) { // ES5
  var index = str.indexOf(suffix);
  return index >= 0
    && index === str.length-suffix.length;
}
str.endsWith(suffix); // ES6
```

`indexOf`tan `includes`a:

```js
if (str.indexOf('x') >= 0) {} // ES5
if (str.includes('x')) {} // ES6
```

`join`den `repeat`e:

```js
new Array(3+1).join('#') // ES5
'#'.repeat(3) // ES6
```

<a href="https://omergulcicek.github.io/es6/es6-temel-ozellikleri/yeni-array-fonksiyonlari">Sıradaki Konu: Yeni array fonksiyonları</a>
