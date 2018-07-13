# var'dan const-let'e

ES5'te değişkenleri `var` (**var**iable) ile tanımlarız. Bu değişkenler fonksiyon scopedtur (fonksiyon kapsamlıdır). `var`ın davranışı zaman zaman kafa karıştırıcı olabilir. Örneğin:

```js
var x = 3;
function func(randomize) {
  if (randomize) {
    var x = Math.random(); // (A) scope: tüm fonksiyon
    return x;
  }
  return x; // A satırından x'e erişir
}
func(false); // undefined
```

`func()` fonksiyonunun `undefined` çıktısını vermesi şaşırtıcı olabilir. Kodu şu şekilde yeniden yazarsak bunun sebebini daha iyi anlayabiliriz:

```js
var x = 3;
function func(randomize) {
  var x;
  /*
    'var' ile oluşturulan değişkenler fonksiyon kapsamlı olduğundan
    x değişkeni 'func()' fonksiyonu içerisinde tanınır.
    return x yapıldığında x'e değer atanmamış olduğundan 'undefined' sonucu döner.
    Fonksiyon dışında tanımlanmış olan ´var x = 3;´ değerini okuyamaz.
  */
  if (randomize) {
    x = Math.random();
    return x;
  }
  return x;
}
func(false); // undefined
```

ES6'da, değişkenleri `let` ve `const` aracılığı ile oluşturabiliriz. Bu değişkenler block-scopedtur (blok kapsamlıdır). `const`, `var` gibi çalışır fakat değeri değiştirilemezdir.

```js
let x = 3;
function func(randomize) {
  if (randomize) {
    let x = Math.random();
    return x;
  }
  return x; // (A)
}
func(false); // 3

/*
  ´funk()´ fonksiyonunda (A) ile işaretlenmiş satırda return x ifadesi çalışır.
  ´let´ ile tanımlanmış olan x değişkeni fonksiyon içerisinde de tanınır.
  Bu yüzden 3 sonucunu return edebilir.
*/
```

Kodda `var` ile tanımladığınız değişkenleri refactoring sırasında `let` yada `const`a düzenlerken dikkatli olmalısınız.

* Değerleri asla değişmeyecek değişkenler için `const` kullanın.
* Değeri değişebilecek değişkenler için ise `let` kullanın.
* `var` kullanmaktan kaçının.

<a href="https://omergulcicek.github.io/es6/es6-temel-ozellikleri/iifes-den-blocklara">Sıradaki Konu: IIFEs'den blocklara</a>
