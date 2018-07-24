# Parametreleri varsayılan değerleriyle kullanmak

ES5'te default değeri bunun gibi belirtebilirsiniz:

```js
function add(x, y) {
  x = x || 15;
  y = y || 20;
  return x+y;
}
```

ES6 daha güzel bir syntaxa sahiptir.

```js
function add(x=15, y=20) {
  return x+y;
}
```

Bu kullanımda, fonksiyona `y` parametresini göndermeseniz bile varsayılan olarak belirlediğiniz değeri (*örnekte 20 değerini*) alır.

Örneğin `add` fonksiyonunu `add()` şeklinde direkt çağırırsak, herhangi bir parametre göndermediğimiz için varsayılan değerler kullanılır ve toplam `35` olacaktır.

`add(7)` şeklinde kullandığımızda `x=7` olacaktır, fakat `y` parametresini belirtmediğimiz için default olan değeri alacaktır (`y=20`) ve sonuç `27` olacaktır.

Her iki değeride set edersek belirlediğimiz değerler toplanacaktır. `add(5,6)` durumunda `11` return edilecektir.

<a href="https://omergulcicek.github.io/es6/es6-temel-ozellikleri/parametre-isimlerini-kullanmak">Sıradaki Konu: Parametre isimlerini kullanmak</a>
