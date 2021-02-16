# _Object_

_Object_ é uma função nativa destinada para objetos.

_Object_ pode ser utilizada como função construtora.

```javascript
typeof Object; // "function"

typeof new Object(); // "object"
```

## Métodos estáticos

- [Método _assign_](#método-assign)
- [Método _create_](#método-create)
- [Método _defineProperties_](#método-defineProperties)
- [Método _defineProperty_](#método-defineProperty)
- [Método _entries_](#método-entries)
- [Método _freeze_](#método-freeze)
- [Método _is_](#método-is)
- [Método _isExtensible_](#método-isExtensible)
- [Método _isFrozen_](#método-isFrozen)
- [Método _isSealed_](#método-isSealed)
- [Método _getOwnPropertyDescriptor_](#método-getOwnPropertyDescriptor)
- [Método _getOwnPropertyDescriptors_](#método-getOwnPropertyDescriptors)
- [Método _getOwnPropertyNames_](#método-getOwnPropertyNames)
- [Método _getPrototypeOf_](#método-getPrototypeOf)
- [Método _keys_](#método-keys)
- [Método _preventExtensions_](#método-preventExtensions)
- [Método _seal_](#método-seal)
- [Método _setPrototypeOf_](#método-setPrototypeOf)
- [Método _values_](#método-values)

### Método _assign_

O método _assign_ modifica e retorna o primeiro argumento com a adição das propriedades do segundo.

```javascript
let objetoAlvo = {
  propriedade1: "valor 1",
  propriedade2: "valor2",
};

let objetoFonte = {
  propriedade2: "esse valor irá sobrescrever o da outra propriedade",
  propriedade3: "valor 3",
};

Object.assign(objetoAlvo, objetoFonte);
```

### Método _create_

O método _create_ retorna um objeto com o argumento como seu protótipo.

```javascript
let objetoPrototipo = {};

let objetoHerdeiro = Object.create(objetoPrototipo);

objetoPrototipo.isPrototypeOf(objetoHerdeiro); // true
```

### Método _defineProperties_

O método _defineProperties_ define ou modifica as propriedades de um objeto e o retorna.

Como primeiro argumento, o método deve receber o objeto a ter as propriedades definidas ou modificadas.

Como segundo argumento, o método deve receber um objeto com propriedades e suas configurações.

Nesse objeto, as chaves devem ser os nomes das propriedades a serem definidas ou modificadas. Os valores das chaves devem ser objetos contendo informações sobre a propriedade.

- _configurable_ define se a propriedade pode ser deletada ou ter suas características _enumerable_ e _writable_ modificadas. O valor dessa opção é um _boolean_, sendo o padrão falso.
- _enumerable_ define se a propriedade é enumerável. O valor dessa opção é um _boolean_, sendo o padrão falso.
- _value_ define o valor da propriedade. O valor padrão é _undefined_.
- _writable_ define se a propriedade pode ou não ser reescrita com o operador de atribuição. O valor dessa opção é um _boolean_, sendo o padrão falso.

```javascript
let objeto = {};

let propriedades = {
  propriedade1: {
    value: "valor",
    enumerable: true,
  },
  propriedade2: {
    value: "valor",
    enumerable: true,
  },
};

Object.defineProperties(objeto, propriedades); // { propriedade1: "valor", propriedade2: "valor" }
```

### Método _defineProperty_

O método _defineProperty_ define ou modifica uma propriedade de um objeto e o retorna.

Como primeiro argumento, o método deve receber o objeto a ter a propriedade definida ou modificada.

Como segundo argumento, o método deve receber uma _string_ com o nome da propriedade a ser definida ou modificada.

Como terceiro argumento, o método pode receber um objeto com configurações para a propriedade.

- _configurable_ define se a propriedade pode ser deletada ou ter suas características _enumerable_ e _writable_ modificadas. O valor dessa opção é um _boolean_, sendo o padrão falso.
- _enumerable_ define se a propriedade é enumerável. O valor dessa opção é um _boolean_, sendo o padrão falso.
- _value_ define o valor da propriedade. O valor padrão é _undefined_.
- _writable_ define se a propriedade pode ou não ser reescrita com o operador de atribuição. O valor dessa opção é um _boolean_, sendo o padrão falso.

```javascript
let objeto = {};

let opcoesParaPropriedade = {
  configurable: false,
  enumerable: true,
  writable: true,
  value: "valor",
};

Object.defineProperty(objeto, "nomeDaPropriedade", opcoesParaPropriedade); // { nomeDaPropriedade: "valor" }
```

### Método _entries_

O método _entries_ retorna um vetor com vetores de pares propriedade-valor.

```javascript
let objeto = {
  propriedade1: "valor 1",
  propriedade2: "valor 2",
};

Object.entries(objeto); // [ ["propriedade1", "valor 1"], ["propriedade2", "valor 2"] ]
```

### Método _freeze_

O método _freeze_ define um objeto como congelado e o retorna.

Objetos congelados não podem ter propriedades adicionadas, modificadas ou removidas. Além disso, as características das propriedades também não podem ser alteradas.

```javascript
let objeto = {};

let objetoCongelado = Object.freeze(objeto);

Object.isFrozen(objeto); // true

Object.isFrozen(objetoCongelado); // true
```

### Método _is_

O método _is_ checa se os argumentos referenciam o mesmo objeto e retorna um _boolean_.

```javascript
let objetoA = {};
let objetoB = objetoA;

Object.is(objetoA, objetoB); // true
```

### Método _isExtensible_

O método _isExtensible_ checa se o objeto é inextensível e retorna um _boolean_.

```javascript
Object isExtensible(objetoInextensivel) // true
```

### Método _isFrozen_

O método _isFrozen_ checa se o objeto é congelado e retorna um _boolean_.

```javascript
Object isFrozen(objetoCongelado) // true
```

### Método _isSealed_

O método _isSealed_ checa se o objeto é selado e retorna um _boolean_.

```javascript
Object isSealed(objetoSelado) // true
```

### Método _getOwnPropertyDescriptor_

O método _getOwnPropertyDescriptor_ retorna um objeto com as características de uma propriedade.

Como primeiro argumento, o método deve receber o objeto a ser identificado.

Como segundo argumento, o método deve receber uma _string_ com o nome da propriedade.

```javascript
let objeto = {
  propriedade: "valor",
};

Object.getOwnPropertyDescriptor(objeto, "propriedade"); // { value: "valor", writable: true, enumerable: true, configurable: true }
```

### Método _getOwnPropertyDescriptors_

O método _getOwnPropertyDescriptors_ retorna um objeto com as características de todas as propriedades do próprio objeto passado como argumento.

```javascript
let objeto = {
  prop: "valor",
};

Object.getOwnPropertyDescriptors(objeto); // { prop: { value: "valor", writable: true, enumerable: true, configurable: true } }
```

### Método _getOwnPropertyNames_

O método _getOwnPropertyNames_ retorna um vetor com os nomes das propriedades enumeráveis e não-enumeráveis do objeto passado como argumento.

```javascript
let objeto = {
  propriedade1: "valor 1",
  propriedade2: "valor 2",
};

Object.getOwnPropertyNames(objeto); // ["propriedade1", "propriedade2"]
```

### Método _getPrototypeOf_

O método _getPrototypeOf_ retorna o objeto protótipo do argumento.

```javascript
let objeto = {};

Object.getPrototypeOf(objeto); // Object.prototype
```

### Método _keys_

O método _keys_ retorna um vetor com os nomes das propriedades enumeráveis do argumento.

```javascript
let objeto = {
  propriedade1: "valor 1",
  propriedade2: "valor 2",
};

Object.keys(objeto); // ["propriedade1", "propriedade2"]
```

### Método _preventExtensions_

O método _preventExtensions_ define um objeto como inextensível e o retorna.

Objetos inextensíveis não podem receber novas propriedades.

```javascript
let objeto = {};

let objetoInextensivel = Object.preventExtensions(objeto);

Object.isExtensible(objeto); // false

Object.isExtensible(objetoInextensivel); // false
```

### Método _seal_

O método _seal_ define um objeto como selado e o retorna.

Objetos selados não podem ter propriedades adicionadas ou deletadas. Além disso, os valores das propriedades podem ser modificados, mas as características não.

```javascript
let objeto = {};

let objetoSelado = Object.seal(objeto);

Object.isSealed(objeto); // true

Object.isSealed(objetoSelado); // true
```

### Método _setPrototypeOf_

O método _setPrototypeOf_ define ou modifica o protótipo de um objeto e o retorna. O primeiro argumento é objeto protótipo, e o segundo o objeto herdeiro.

```javascript
let objetoHerdeiro = {};

let objetoPrototipo = {};

Object.setPrototypeOf(objetoPrototipo, objetoHerdeiro); // {}
```

### Método _values_

O método _values_ retorna um vetor com os valores do objeto passado como argumento.

```javascript
let objeto = {
  propriedade1: "valor 1",
  propriedade2: "valor 2",
};

Object.values(objeto); // ["valor 1", "valor 2"]
```

## Atributos de instância

Atributo _constructor_ é a função construtora do objeto.

```javascript
let objeto = {};

objeto.constructor; // Function: Object
```

## Métodos de instância

Instâncias de _Object_ herdam métodos de _Object.prototype_.

- [Método _hasOwnProperty_](#métodos-hasOwnProperty)
- [Método _isPrototypeOf_](#métodos-isPrototypeOf)
- [Método _propertyIsEnumerable_](#métodos-propertyIsEnumerable)
- [Método _toString_](#métodos-toString)
- [Método _valueOf_](#métodos-valueOf)

### Método _hasOwnProperty_

O método _hasOwnProperty_ checa se o objeto possui a propriedade e retorna um _boolean_.

```javascript
let objeto = {
  propriedade: "valor",
};

objeto.hasOwnProperty("propriedade"); // true
```

### Método _isPrototypeOf_

O método _isPrototypeOf_ checa se o objeto é o protótipo do argumento e retorna um _boolean_.

```javascript
let objeto = {};

Object.prototype.isPrototypeOf(objeto); // true
```

### Método _propertyIsEnumerable_

O método _propertyIsEnumerable_ checa se o argumento é uma propriedade enumerável e retorna um _boolean_.

```javascript
let objeto = {
  propriedade: "valor",
};

objeto.propertyIsEnumerable("propriedade"); // true
```

### Método _toString_

O método _toString_ retorna uma _string_ com o objeto.

```javascript
let objeto = {
    propriedade: "valor"
}

objeto.toString()) // "[object Object]"
```

### Método _valueOf_

O método _valueOf_ retorna o próprio objeto.

```javascript
let objeto = {
  propriedade: "valor",
};

objeto.valueOf(); // { propriedade: "valor" }
```
