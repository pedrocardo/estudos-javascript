# _Number_

_Number_ é um tipo de dado primitivo. 

Dados do tipo _number_ representam números.

```javascript
typeof 45; // "number"
```

_Number_ possui formas literais para representar números reais, binários, octais e hexadecimais.

```javascript
12.24;
0b11;
015;
0x1123;
```

Como _number_ é implementado em _64-bit floating point_, todos os números são reais.

```javascript
3 === 3.0; // true
```

_Number_ é preciso até quinze dígitos e dezesseis casas decimais.

```javascript
9999999999999999; // 10000000000000000

1.55555555555555555; // 1.5555555555555556
```

## Propriedades globais

Existem duas propriedades globais nativas do tipo _number_.

A propriedade _NaN_ representa um resultado falho de operação matemática.

_NaN_ é um acrônimo para _not a number_ e só pode ser checado com a função global _isNaN_.

```javascript
typeof NaN; // "number"

NaN === NaN; // false

isNaN(NaN); // true
```

A propriedade _Infinity_ representa números maiores que 1.79769313486231570e+308 ou menores que esse número negativo.

```javascript
typeof Infinity; // "number"

typeof -Infinity; // "number"
```

## Objeto empacotador

O tipo primitivo _number_ possui um objeto empacotador chamado [_Number_](../objetos-nativos/objeto-empacotador-number.md).

Com esse objeto, dados _number_ são encapsulados implicitamente, tornando possível acessar métodos de _Number.prototype_.

```javascript
(26.012).toFixed(); // "26"
```
