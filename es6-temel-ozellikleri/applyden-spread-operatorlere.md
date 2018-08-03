# apply()'den spread operatörlere

ES5'te, arrayleri `apply()` aracılığıyla parametrelere dönüştürürsünüz. ES6 bunun için spread operatörünü kullanır.

## Math.max()

`Math.max()`, argümanlarının sayısal olarak en yüksek değerini return eder.

ES5'te apply():

```js
Math.max.apply(Math, [-1, 5, 11, 3])
// 11
```

ES6'da spread operatör:

```js
Math.max(...[-1, 5, 11, 3])
// 11
```

## Array.prototype.push()

`Array.prototype.push()` parametre olarak aldığı arrayleri birleştirir.

ES5'te apply():

```js
var arr1 = ['a', 'b'];
var arr2 = ['c', 'd'];

arr1.push.apply(arr1, arr2);
// arr1 is now ['a', 'b', 'c', 'd']
```

ES6'da spread operatör:

```js
const arr1 = ['a', 'b'];
const arr2 = ['c', 'd'];

arr1.push(...arr2);
// arr1 is now ['a', 'b', 'c', 'd']
```

*İlerleyen konularda spread operatörler daha detaylı olarak ele alınacaktır.*

<a href="https://omergulcicek.github.io/es6/es6-temel-ozellikleri/concatden-spread-operatorlere">Sıradaki Konu: concat()'den spread operatörlere</a>
