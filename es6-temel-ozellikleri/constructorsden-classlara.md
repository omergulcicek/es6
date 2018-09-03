# constructorsden classlara

ES5'te classları aşağıdaki gibi oluşturursunuz:

```js
function Person(name) {
  this.name = name;
}
Person.prototype.describe = function () {
  return this.name + ' kişisi çağrıldı.';
};
```

ES6'da biraz daha okunaklı bir syntaxı vardır.

```js
class Person {
  constructor(name) {
    this.name = name;
  }
  describe() {
    return this.name + ' kişisi çağrıldı.';
  }
}
```

ES6 classının sonuna noktalı virgül konulmadığını unutmayınız.

<a href="https://omergulcicek.github.io/es6/es6-temel-ozellikleri/objelerden-maplere">Sıradaki Konu: objelerden Map'lere</a>
