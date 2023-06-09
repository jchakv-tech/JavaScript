---
id: 5900f3941000cf542c50fea7
title: 'Problema 40: costante di Champernowne'
challengeType: 1
forumTopicId: 302066
dashedName: problem-40-champernownes-constant
---

# --description--

Una frazione decimale irrazionale è creata concatenando i numeri interi positivi:

0.12345678910**1**112131415161718192021...

Puoi vedere che la dodicesima cifra della parte frazionale è 1.

Se *d<sub>n</sub>* rappresenta l'*n*-esima cifra della parte decimale, trova il valore di questa espressione.

d<sub>1</sub> × d<sub>10</sub> × d<sub>100</sub> × d<sub>1000</sub> × d<sub>10000</sub> × d<sub>100000</sub> × d<sub>1000000</sub>

# --hints--

`champernownesConstant(100)` dovrebbe restituire un numero.

```js
assert(typeof champernownesConstant(100) === 'number');
```

`champernownesConstant(100)` dovrebbe restituire 5.

```js
assert.strictEqual(champernownesConstant(100), 5);
```

`champernownesConstant(1000)` dovrebbe restituire 15.

```js
assert.strictEqual(champernownesConstant(1000), 15);
```

`champernownesConstant(1000000)` dovrebbe restituire 210.

```js
assert.strictEqual(champernownesConstant(1000000), 210);
```

# --seed--

## --seed-contents--

```js
function champernownesConstant(n) {

  return true;
}

champernownesConstant(100);
```

# --solutions--

```js
function champernownesConstant(n) {
  let fractionalPart = '';
  for (let i = 0; fractionalPart.length <= n; i++) {
    fractionalPart += i.toString();
  }

  let product = 1;
  for (let i = 0; i < n.toString().length; i++) {
    const index = 10 ** i;
    product *= parseInt(fractionalPart[index], 10);
  }

  return product;
}
```
