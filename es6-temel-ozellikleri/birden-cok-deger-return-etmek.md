# Birden çok değer return etmek

Bazı fonksiyon birden çok değer return edebilir. ES5'te, bu değerlere erişmek istiyorsanız her zaman ara değişkenler oluşturmanız gerekir. ES6'da, ara değişkenleri destructuring yoluyla önleyebilirsiniz.

## Arrayler üzerinden çoklu değer return etmek

`exec()`, yakalanmış grupları Array benzeri bir nesneyle return eder. ES5'te, yalnızca gruplarla ilgilenseniz bile bir ara değişkene (aşağıdaki örnekte `matchObj`) ihtiyacınız vardır:

```js
var matchObj =
  /^(\d\d\d\d)-(\d\d)-(\d\d)$/
  .exec('2999-12-31');
  
var year = matchObj[1];
var month = matchObj[2];
var day = matchObj[3];
```

ES6'da, destructuring bu kodu daha basit hale getirir:

```js
const [, year, month, day] =
  /^(\d\d\d\d)-(\d\d)-(\d\d)$/
  .exec('2999-12-31');
```

4.5.2 Multiple return values via objects 
The method Object.getOwnPropertyDescriptor() returns a property descriptor, an object that holds multiple values in its properties.

In ES5, even if you are only interested in the properties of an object, you still need an intermediate variable (propDesc in the example below):

## Objeler ile çoklu return değişkenleri

`Object.getOwnPropertyDescriptor()` fonksiyonu, özelliklerinde birden çok değer barındıran bir property descriptor (*özellik tanımlayıcısı*) return eder.

ES5'te, yalnızca bir nesnenin propertyleriyle ilgilenseniz bile, hala bir ara değişkene ihtiyacınız vardır (aşağıdaki örnekte `propDesc`):

```js
var obj = { foo: 123 };

var propDesc = Object.getOwnPropertyDescriptor(obj, 'foo');
var writable = propDesc.writable;
var configurable = propDesc.configurable;

console.log(writable, configurable); // true true
```

ES6'da destructuring kullanabilirsiniz.

```js
const obj = { foo: 123 };

const {writable, configurable} =
  Object.getOwnPropertyDescriptor(obj, 'foo');

console.log(writable, configurable); // true true
```

`{writable, configurable}` kullanımı bir kısaltmadır, orijinali şu şekildedir:

```js
{ writable: writable, configurable: configurable }
```

*İlerleyen konularda destructuring daha detaylı olarak ele alınacaktır.*

<a href="https://omergulcicek.github.io/es6/es6-temel-ozellikleri/for-foreach-ten-for-of-a">Sıradaki Konu: for-forEach'ten for-of'a</a>
