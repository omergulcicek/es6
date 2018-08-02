# Parametre isimlerini kullanmak

Javascript'te parametrelerin yaygın olarak isimlendirilmesi, nesne değişmezleri aracılığıyla yapılır:

```js
selectEntries({ start: 0, end: -1 });
```

Bu yaklaşımın iki avantajı vardır: Kod kendi kendini daha tanımlayıcı hale gelir ve keyfi parametrelerin atlanması daha kolaydır.

ES5'te `selectEntries()` öğesini aşağıdaki gibi uygulayabilirsiniz:

```js
function selectEntries(options) {
  var start = options.start || 0;
  var end = options.end || -1;
  var step = options.step || 1;
  ···
}
```

ES6'da, parametre tanımlarında destructuring kullanabilirsiniz ve kod daha basit hale gelir:

```js
function selectEntries({ start=0, end=-1, step=1 }) {
    ···
}
```

## İsteğe bağlı parametreler

ES5'te isteğe bağlı parametre seçeneklerini yapmak için, koda (A) satırını eklersiniz:

```js
function selectEntries(options) {
  options = options || {}; // (A)
  var start = options.start || 0;
  var end = options.end || -1;
  var step = options.step || 1;
  ···
}
```

Yani, `selectEntries()` fonksiyonunu kullanırken parametre kullanmak zorunda değilsiniz. Eğer parametre olarak içerisinde `start`, `step`, `end` gibi propertyleri bulunduran bir obje atarsak, parametre olarak atılan obje kullanılır. Herhangi bir parametre yada property kullanmazsak belirttiğimiz değerler kullanılır.

Fakat bunu ES6'da çok daha kolay şekilde yapabiliriz.

```js
function selectEntries({ start=0, end=-1, step=1 } = {}) {
    ···
}
```

<a href="https://omergulcicek.github.io/es6/es6-temel-ozellikleri/applyden-spread-operatorlere">Sıradaki Konu: apply()'den spread operatörlere</a>
