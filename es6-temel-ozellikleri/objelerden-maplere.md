# objelerden Map'lere

Dil yapı nesnesini stringlerden rasgele değerlere (bir veri yapısı) `map` olarak kullanmak JavaScript'te her zaman geçici bir çözüm olmuştur. Bunu yapmanın en güvenli yolu, prototipi `null` olan bir nesne oluşturmaktır. O zaman hala hiçbir anahtarın `__proto__` string'i olmadığından emin olmalısınız, çünkü bu özellik anahtarı birçok JavaScript motorunda özel fonksiyonlar tetikler.

Aşağıdaki ES5 kodu, `dict` nesnesini bir `map` olarak kullanan `countWords` fonksiyonunu içerir:

```js
var dict = Object.create(null);
function countWords(word) {
    var escapedWord = escapeKey(word);
    if (escapedWord in dict) {
        dict[escapedWord]++;
    } else {
        dict[escapedWord] = 1;
    }
}
function escapeKey(key) {
    if (key.indexOf('__proto__') === 0) {
        return key+'%';
    } else {
        return key;
    }
}
```

ES6'da, yerleşik veri yapısı `Map` kullanabilir ve anahtarlardan kaçmanız gerekmez. Olumsuz bir yanı ise, `Map` içindeki değerleri artırmak için daha az uygundur.

```js
const map = new Map();
function countWords(word) {
    const count = map.get(word) || 0;
    map.set(word, count + 1);
}
```

`Map`in bir başka yararı da, yalnızca string değil, isteğe bağlı değerleri anahtar olarak kullanabilmenizdir.

<a href="https://omergulcicek.github.io/es6/es6-temel-ozellikleri/yeni-string-fonksiyonlari">Sıradaki Konu: Yeni string fonksiyonları</a>
