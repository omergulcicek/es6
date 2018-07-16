# Arrow fonksiyonları

Mevcut ES5 kodunda, `_this` değişkenini (*A satırında*) oluşturduk, böylece `UiComponent` elementi B satırından erişilebilir.

```js
function UiComponent() {
  var _this = this; // (A)
  var button = document.getElementById('myButton');
  button.addEventListener('click', function () {
    console.log('CLICK');
    _this.handleClick(); // (B)
  });
}
UiComponent.prototype.handleClick = function () {
  ···
};
```

ES6'da, arrow (*ok*) fonksiyonlarını kullanabiliriz :

```js
function UiComponent() {
  var button = document.getElementById('myButton');
  button.addEventListener('click', () => {
    console.log('CLICK');
    this.handleClick(); // (A)
  });
}
```

Arrow fonksiyonları, ifadelerin sonuçlarını return eden kısa kullanımlar için kullanışlıdır.

ES5'te, bu tür kodlar nispeten ayrıntılıdır:

```js
var arr = [1, 2, 3];
var squares = arr.map(function (x) { return x * x });
```

ES6'da, arrow fonksiyonları ile çok daha kısa:

```js
const arr = [1, 2, 3];
const squares = arr.map(x => x * x);
```

Parametreler yalnızca tek bir değişken ise, parantezleri kullanmayabilirsiniz. Yani: `(x) => x * x` ve `x => x * x` aynıdır.

*İlerleyen konularda arrow fonksiyonları data detaylı olarak ele alınacaktır.*

<a href="https://omergulcicek.github.io/es6/es6-temel-ozellikleri/birden-cok-deger-return-etmek">Sıradaki Konu: Birden çok değer return etmek</a>
