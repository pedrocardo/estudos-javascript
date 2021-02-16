# _Undefined_

_Undefined_ é um tipo de dado primitivo.

Dados do tipo _undefined_ representam valores indefinidos.

```javascript
typeof undefined; // "undefined"
```

_Undefined_ possui como forma literal a própria palavra.

```javascript
undefined;
```

## _Undefined_ e _null_

Ao comparar _undefined_ e _null_ com o operador de igualdade, será retornado verdadeiro.

```javascript
undefined == null; // true
```

Para evitar essa incoerência, é necessário utilizar o operador de igualdade estrita.

```javascript
undefined === null; // false
```

## Uso

Variáveis não inicializadas e acessos a propriedades inexistentes de um objeto são dois exemplos que retornam _undefined_.

```javascript
let variavelNaoInicializada;

variavelNaoInicializada; // undefined

let objeto = {};

objeto.propriedadeNaoDefinida; // undefined
```
