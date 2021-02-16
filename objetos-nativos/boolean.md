# _Boolean_

_Boolean_ é uma função nativa que funciona como objeto empacotador para o primitivo _boolean_.

_Boolean_ pode ser utilizada como função construtora.

```javascript
typeof Boolean; // "function"

typeof new Boolean(); // "object"
```

## Conversão de tipos

A função _Boolean_ pode ser utilizada para converter valores de outros tipos para o primitivo _boolean_.

Números diferentes de zero, _strings_ não vazias e objetos são convertidos para _true_.

```javascript
Boolean(1); // true
Boolean("string"); // true
Boolean({}); // true
```

Números iguais a zero, _strings_ vazias, _NaN_, _undefined_ e _null_ são convertidos para _false_.

```javascript
Boolean(0); // false
Boolean(NaN); // false
Boolean(""); // false
Boolean(undefined); // false
Boolean(null); // false
```

## Métodos de instância

Valores _boolean_ são encapsulados implicitamente, herdando métodos de _Boolean.prototype_.

- [Método _toString_](#método-toString)
- [Método _valueOf_](#método-valueOf)

### Método _toString_

O método _toString_ retorna uma _string_ com o valor booleano do objeto.

```javascript
true.toString(); // "true"
```

### Método _valueOf_

O método _valueOf_ retorna um _boolean_ com o valor booleano do objeto.

```javascript
true.valueOf(); // true
```
