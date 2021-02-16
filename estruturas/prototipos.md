# Protótipos

Protótipos são o mecanismo para heranças entre objetos.

## Funções

Funções são objetos. Assim, podem ter propriedades.

```javascript
function Funcao() {}

Funcao instanceof Object; // true

Funcao.propriedade = "propriedade de uma função";
```

## Propriedade _prototype_

Funções possuem a propriedade _prototype_ do tipo _object_.

```javascript
function Funcao() {}

Funcao.prototype; // {constructor: ƒ Funcao(), __proto__: Object}
```

Como é um objeto, _prototype_ pode receber propriedades.

```javascript
function Funcao() {}

Funcao.prototype.atributo = "propriedade de prototype";

Funcao.prototype.atributo; // "propriedade de prototype"
```

Como é um objeto, _prototype_ possui a propriedade _constructor_.

A propriedade _constructor_ de _prototype_ é a própria função objeto.

```javascript
function Funcao() {}

Funcao.prototype.constructor === Funcao; // true
```

## Propriedade _proto_

Objetos possuem a propriedade _proto_ do tipo _object_.

```javascript
let objeto = {};

objeto.__proto__; // {constructor: f Object()}
```

Objetos são instâncias de funções construtoras.

```javascript
let objeto = new Object();

objeto instanceof Object; // true
```

A propriedade _proto_ de um objeto é igual a _prototype_ da função construtora que o construiu.

```javascript
let objeto = new Object();

objeto.__proto__ === Object.prototype; // true
```

Funções também são objetos, então possuem a propriedade _proto_.

```javascript
function Funcao() {}

Funcao.__proto__ === Function.prototype; // true
```

_Prototype_ também é um objeto, então possui a propriedade _proto_.

```javascript
Function.prototype.__proto__ === Object.prototype; // true
```

O único objeto que não possui a propriedade _proto_ é _Object.prototype_.

```javascript
Object.prototype.__proto__; // null
```

## Funções construtoras

Qualquer função pode ser utilizada para construir objetos. Para isso, deve ser utilizado o operador _new_.

Ao criar um objeto, a propriedade _prototype_ da função é relacionada a propriedade _proto_ do objeto.

```javascript
function Funcao() {}

let objeto = new Funcao();

objeto.__proto__ === Funcao.prototype; // true
```

## Operador _new_

Para criar um objeto, o operador _new_ realiza as seguintes operações com a função construtora:

1. Um objeto vazio é criado;
2. A propriedade _proto_ do objeto é relacionado à propriedade _prototype_ da função construtora;
3. A função construtora é executada com as ocorrências de _this_ modificadas para o objeto;
4. O objeto é retornado.

Essas operações podem ser simuladas com uma função.

```javascript
function simularNew(funcaoConstrutora, ...parametros) {
  let objeto = {};

  objeto.__proto__ = funcaoConstrutora.prototype;

  funcaoConstrutora.apply(objeto, parametros);

  return objeto;
}
```

## Herança

A propriedade _proto_ possibilita que objetos herdem propriedades de um protótipo.

Ao tentar acessar uma propriedade, ela sempre será procurada primeiro no próprio objeto.

Caso a propriedade não seja encontrada, ela será procurada no objeto atribuído a _proto_.

```javascript
function Funcao() {}

Funcao.prototype.atributo = "propriedade de prototype";

let objeto = new Funcao();

objeto.atributo; // "propriedade de prototype"
```

Como a propriedade _prototype_ de uma função também tem a propriedade _proto_, é possível formar cadeias de protótipos.

```javascript
function FuncaoPai() {}

FuncaoPai.prototype.atributo = "propriedade de prototype da função pai";

function FuncaoFilha() {}

FuncaoFilha.prototype.__proto__ = FuncaoPai.prototype;

let objeto = new FuncaoFilha();

objeto.atributo; // "propriedade de prototype da função pai"
```
