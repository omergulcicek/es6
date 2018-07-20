# for & forEach'ten for-of'a

ES5'ten önce, dizileri aşağıdaki gibi yinelerdik:

```js
var arr = ['a', 'b', 'c'];
for (var i=0; i<arr.length; i++) {
    var elem = arr[i];
    console.log(elem);
}
```

ES5 ile birlikte ise, opsiyon olarak `forEach()` döngüsünü kullanmaya başladık:

```js
arr.forEach(function (elem) {
    console.log(elem);
});
```

ES6'da ise for-of döngüsü ile önceki döngü kullanımlarındaki avantajlar birleştirilmiş oldu:

```js
const arr = ['a', 'b', 'c'];
for (const elem of arr) {
    console.log(elem);
}
```

Eğer döngüde hem index hemde array elementinin değerini istersek aşağıdaki gibi kullanabiliriz.

```js
for (const [index, elem] of arr.entries()) {
    console.log(index+'. '+elem);
}
```

*İlerleyen konularda for-of döngüsü detaylı olarak ele alınacaktır.*

<a href="https://omergulcicek.github.io/es6/es6-temel-ozellikleri/parametreleri-varsayilan-degerleriyle-kullanmak">Sıradaki Konu: Parametreleri varsayılan değerleriyle kullanmak</a>
