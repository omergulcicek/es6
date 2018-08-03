# concat()'den spread operatörlere

Spread operatörü ayrıca (non-destructively) işleneninin içeriğini Array elementlerine dönüştürebilir. Bu, Array yöntemi `concat()` için bir alternatif anlamına gelir.

ES5'te concat():

```js
var arr1 = ['a', 'b'];
var arr2 = ['c'];
var arr3 = ['d', 'e'];

console.log(arr1.concat(arr2, arr3));
// [ 'a', 'b', 'c', 'd', 'e' ]
```

ES6'da spread operatör:

```js
const arr1 = ['a', 'b'];
const arr2 = ['c'];
const arr3 = ['d', 'e'];

console.log([...arr1, ...arr2, ...arr3]);
// [ 'a', 'b', 'c', 'd', 'e' ]
```

*İlerleyen konularda spread operatörler daha detaylı olarak ele alınacaktır.*

<a href="https://omergulcicek.github.io/es6/es6-temel-ozellikleri/constructorsden-classlara">Sıradaki Konu: constructorsden classlara</a>
