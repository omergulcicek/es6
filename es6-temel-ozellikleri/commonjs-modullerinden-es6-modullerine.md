# CommonJS Modüllerinden ES6 Modüllerine

ES6, modüller için yerleşik desteğe sahiptir. Ne yazık ki, hiçbir JavaScript motoru henüz yerel olarak desteklememektedir. Ancak **browserify**, **webpack** veya **jspm** gibi araçlar, modüller oluşturmak için ES6 sözdizimini kullanmanıza izin verir.

## Birden çok export

### CommonJS ile birden çok export

CommonJS'te birden çok export'u şu şekilde yaparsınız:

```js
//------ lib.js ------
var sqrt = Math.sqrt;
function square(x) {
    return x * x;
}
function diag(x, y) {
    return sqrt(square(x) + square(y));
}
module.exports = {
    sqrt: sqrt,
    square: square,
    diag: diag,
};

//------ main1.js ------
var square = require('lib').square;
var diag = require('lib').diag;

console.log(square(11)); // 121
console.log(diag(4, 3)); // 5
```

Alternatif olarak, tüm modülü bir nesne olarak import edebilir ve karesine erişebilir ve bunun üzerinden arama yapabilirsiniz:

```js
//------ main2.js ------
var lib = require('lib');
console.log(lib.square(11)); // 121
console.log(lib.diag(4, 3)); // 5
```

### ES6 ile birden çok export

ES6'da ise aynı işlemler aşağıdaki gibi yapılabilir:

```js
//------ lib.js ------
export const sqrt = Math.sqrt;
export function square(x) {
    return x * x;
}
export function diag(x, y) {
    return sqrt(square(x) + square(y));
}

//------ main1.js ------
import { square, diag } from 'lib';
console.log(square(11)); // 121
console.log(diag(4, 3)); // 5
```

Modüllerin nesne olarak içe aktarılması için kullanılan syntax aşağıdaki gibidir (satır A)

```js
//------ main2.js ------
import * as lib from 'lib'; // (A)
console.log(lib.square(11)); // 121
console.log(lib.diag(4, 3)); // 5
```

## Tekli export

### CommonJS ile tek export

```js
//------ myFunc.js ------
module.exports = function () { ··· };

//------ main1.js ------
var myFunc = require('myFunc');
myFunc();
```

### ES6 ile tek export

```js
//------ myFunc.js ------
export default function () { ··· } // no semicolon!

//------ main1.js ------
import myFunc from 'myFunc';
myFunc();
```

<a href="https://omergulcicek.github.io/es6/yeni-tam-sayi-degismezleri/">Sıradaki Konu: Yeni Tam Sayı Değişmezleri</a>
