# _Boolean_

_Boolean_ é um tipo de dado primitivo. 

Dados do tipo _boolean_ representam booleanos.

```javascript
typeof true; // "boolean"
```

_Boolean_ possui duas formas literais que representam verdadeiro e falso.

```javascript
true;
false;
```

## Objeto empacotador

O tipo primitivo _boolean_ possui um objeto empacotador chamado [_Boolean_](../objetos-nativos/objeto-empacotador-boolean.md).

Com esse objeto, dados _boolean_ são encapsulados implicitamente, tornando possível acessar métodos de _Boolean.prototype_.

```javascript
true.toString(); // "true"
```
