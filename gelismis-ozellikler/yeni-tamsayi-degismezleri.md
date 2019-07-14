# Yeni Tamsayı ve Math Özellikleri

## Yeni tamsayı değişmezleri

Artık tam sayıları ikili ve sekizli notasyonlarla belirtebilirsiniz:

```js
> 0xFF // ES5: hexadecimal
255
> 0b11 // ES6: binary
3
> 0o10 // ES6: octal
8
```

## Yeni Number özellikleri

Global bir nesne olan `Number` birkaç yeni özellik kazandı:

* `Number.isInteger(num)`, `num` değişkeninin bir tamsayı olup olmadığını kontrol eder (ondalık kesirsiz bir sayı)

```js
> Number.isInteger(1.05)
false
> Number.isInteger(1)
true

> Number.isInteger(-3.1)
false
> Number.isInteger(-3)
true
```

* Bir JavaScript tamsayısının güvenli olup olmadığını belirlemek için bir yöntem:

```js
Number.isSafeInteger(number)
Number.MIN_SAFE_INTEGER
Number.MAX_SAFE_INTEGER
```

* `Number.isNaN(num)`, `num` değişkeninin `NaN` olup olmadığını kontrol eder. Global fonksiyonunun aksine `isNaN()`, bağımsız değişkenini bir sayıya zorlamaz ve bu nedenle sayı olmayanlar için daha güvenlidir:

```js
> isNaN('???')
true
> Number.isNaN('???')
false
```

* 3 ek yöntem eklendi: `Number.isFinite`, `Number.parseFloat`, `Number.parseInt`.

## Yeni Math yöntemleri

`Math.sign` sayının negatif yada pozitif olduğunu return eder:

```js
> Math.sign(-8)
-1
> Math.sign(0)
0
> Math.sign(3)
1
```

`Math.trunc` sayının küsüratını siler:

```js
> Math.trunc(3.1)
3
> Math.trunc(3.9)
3
> Math.trunc(-3.1)
-3
> Math.trunc(-3.9)
-3
```

> NOT
>
> `trunc` fonksiyonu aslında `sign`, `floor` ve `abs` metodlarından yardım alır.

```js
function trunc(x) {
    return Math.sign(x) * Math.floor(Math.abs(x));
}
```

`Math.log10()` logaritmayı 10 tabanında hesaplar

```js
> Math.log10(100)
2
```

> NOT
>
> 2 tabanında logaritma hesaplamak için `Math.log2(x)` kullanabilirsiniz.

`Math.hypot()` parametre olarak aldığı 2 sayının karelerinin toplamının karekökünü hesaplar (Pythagoras teoremi):

```js
> Math.hypot(3, 4)
5
```

`Math.cbrt(x)` sayının küp kökünü return eder: x(∛x) 

```js
> Math.cbrt(8)
2
```

### Trigonometrik Yöntemler

* `Math.sinh(x)`
X'in hiperbolik sinüsünü hesaplar

* `Math.cosh(x)`
X'in hiperbolik kosinüsünü hesaplar

* `Math.tanh(x)`
X'in hiperbolik tanjantını hesaplar

* `Math.asinh(x)`
X'in ters hiperbolik sinüsünü hesaplar

* `Math.acosh(x)`
X'in ter hiperbolik kosinüsünü hesaplar

* `Math.atanh(x)`
X'in ters hiperbolik tanjantını hesaplar

<a href="https://omergulcicek.github.io/es6/yeni-sayi-ve-math-ozellikleri/yeni-statik-number-ozellikleri">Sıradaki Konu: Yeni statik Number özellikleri</a>
