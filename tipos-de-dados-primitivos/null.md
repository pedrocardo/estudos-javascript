# _Null_

_Null_ é um tipo de dado primitivo.

Dados do tipo _null_ representam nulo.

Por causa de um _bug_ nativo da linguagem, o operador _typeof_ indica _null_ como um objeto.

```javascript
typeof null; // "object"
```

_Null_ possui como forma literal a própria palavra.

```javascript
null;
```

## _Null_ e _undefined_

Ao comparar _null_ e _undefined_ com o operador de igualdade, será retornado verdadeiro.

```javascript
null == undefined; // true
```

Para evitar essa incoerência, é necessário utilizar o operador de igualdade estrita.

```javascript
null === undefined; // false
```
