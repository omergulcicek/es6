# IIFE'den blocklara

ES5'te, `tmp` adında bir değişkenin kapsamını bir bloğa sınırlamak istiyorsanız, IIFE (Immediately-Invoked Function Expression) adlı bir pattern kullanmanız gerekirdi:

```js
(function () {  // IIFE açılışı
  var tmp = ···;
  ···
}());  // IIFE kapanışı

console.log(tmp); // ReferenceError
```

ECMAScript 6'da ise sadece bir block ve `let` (veya `const`) kullanabilirsiniz.

```js
{  // block açılışı
  let tmp = ···;
  ···
}  // block kapanışı

console.log(tmp); // ReferenceError
```

[Önceki konuda](https://omergulcicek.github.io/es6/es6-temel-ozellikleri/var-dan-const-let-e) bahsettiğimiz gibi `var` ile oluşturulan değişkenler fonksiyon scoped olduğundan dolayı fonksiyon dışında tanınmaz, sadece fonksiyon içerisinde kullanılırdı. ES6 ile birlikte gelen `let` ve `const` değişkenleri ise block scopedtur, haliyle fonksiyon dışında da bu değişkenleri kullanabilirsiniz.

Fakat bu değişkenlere bir sınır belirlemek istiyorsak blocklardan yararlanabiliriz. Üstteki kod örneğinde görüldüğü gibi `let` (yada `const`) ile oluşturulmuş bir değişken olmasına rağmen, block dışarısında `console.log(tmp);` yapıldığında tmp değişkeninin tanımlı olmadığının uyarısını verecektir.

<a href="https://omergulcicek.github.io/es6/es6-temel-ozellikleri/arrow-fonksiyonlari">Sıradaki Konu: Arrow fonksiyonları</a>
