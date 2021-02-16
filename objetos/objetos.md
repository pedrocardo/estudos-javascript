# Objetos

Objetos são coleções de propriedades - valores nomeados.

Com exceção dos primitivos (_boolean_, _null_, _number_, _string_ e _undefined_), todos os dados são objetos.

## Notação literal

A notação literal de objetos é uma lista de pares chave-valor separados por vírgula. Essa lista deve ser envolvida por chaves.

```javascript
let objeto = {
  chave1: "valor 1",
  chave2: "valor 2",
};
```

## Propriedades e valores

As chaves de objetos são comumente chamadas de propriedades e podem receber valores primitivos, funções ou outros objetos.

```javascript
let objeto = {
  atributo: "primitivo",

  metodo: function () {
    return "isso é um método";
  },

  objetoInterno: {
    atributo: "primitivo",
  },
};
```

## Facilidades na escrita

A notação literal de objetos possibilita algumas facilidades na escrita.

Por exemplo, é possível escrever o nome de uma variável declarada, e ela se tornará uma propriedade do objeto.

```javascript
let nome = "Gilles Deleuze";

let objeto = {
  nome,
};

objeto.nome; // "Gilles Deleuze"
```

Para escrever uma propriedade com o valor sendo uma função, não é necessário utilizar a palavra reservada _function_.

```javascript
let objeto = {
  metodo() {
    return "isso é um método";
  },
};

objeto.metodo(); // "isso é um método"
```

## Manipulação de propriedades

Para acessar as propriedades de um objeto, é possível utilizar a notação ponto ou colchetes com _string_.

```javascript
objeto.nome; // "rinoceronte"

objeto["nome"]; // "rinoceronte"
```

Ao tentar acessar uma propriedade inexistente de um objeto, será retornado _undefined_.

```javascript
objeto.propriedadeIndefinida; // undefined
```

Para adicionar ou modificar uma propriedade de um objeto, basta utilizar a notação ponto ou colchetes.

```javascript
objeto.nome = "leão";

objeto["nome"] = "flamingo";
```

Para deletar uma propriedade de um objeto, basta utilizar o operador _delete_.

O operador _delete_ exclui uma propriedade de um objeto. Essa operação retorna um _boolean_.

Caso tenha sido realizada com sucesso, a operação retornará _true_.

Caso não tenha sido realizada com sucesso, a operação retornará _false_.
```javascript
delete objeto.nome; // true
```

## Referência

Diferente dos tipos primitivos, objetos são atribuídos e comparados através da referência ao local da memória em que estão.

Por exemplo, ao atribuir um objeto a uma variável, será armazenado nela apenas o local na memória em que o objeto está.

Isso impossibilita fazer cópias de objetos utilizando o operador de atribuição.

```javascript
let objeto = {
  nome: "girafa",
};

let objetoCopia = objeto;

objetoCopia.nome = "rinoceronte";

objeto.nome; // "rinoceronte"
objetoCopia.nome; // "rinoceronte"
```

Outra forma de visualizar essa característica é comparando formas literais iguais atribuídas a variáveis diferentes.

Apesar da igualdade, os dois objetos serão armazenados em locais na memória diferentes.

```javascript
let objeto1 = {};

let objeto2 = {};

objeto1 === objeto2; // false
```

## Funções construtoras

Objetos podem ser criados a partir de funções construtoras.

```javascript
function Animal(nome) {
  this.nome = nome;
}

let objetoAnimal = new Animal("girafa");

objetoAnimal instanceof Animal; // true

objetoAnimal instanceof Object; // true
```

## Classes

Objetos podem ser criados a partir de classes.

```javascript
class Animal {
  constructor(nome) {
    this.nome = nome;
  }
}

let objetoAnimal = new Animal("flamingo");

objetoAnimal instanceof Animal; // true

objetoAnimal instanceof Object; // true
```

## Iteração

Para iterar as propriedades de um objeto, é possível utilizar a instrução _for in_.

Essa instrução percorrerá todas as propriedades enumeráveis do objeto e tratará os nomes dessas propriedades como uma _string_.

```javascript
let objeto = {
  nome: "Carl",
  sobrenome: "Jung",
};

for (propriedade in objeto) {
  console.log(`propriedade ${propriedade} e valor ${objeto[propriedade]}`);
}

// "propriedade nome e valor Carl"
// "propriedade sobrenome e valor Jung"
```

## _Getters_ e _setters_

Objetos podem ter métodos de acesso e modificação, nomeados como _getters_ e _setters_. Esses métodos garantem a qualidade dos dados.

Métodos _getter_ facilitam o acesso às propriedades.

```javascript
let objeto = {
  _nomePrivado: "Michel",
  _sobrenomePrivado: "Foucault",

  get nomeCompleto() {
    return `${this._nomePrivado} ${this._sobrenomePrivado}`;
  },
};

objeto.nomeCompleto; // "Michel Foucault"
```

Métodos _setter_ facilitam a modificação das propriedades.

```javascript
let objeto = {
  _idadePrivada: 10,

  set idade(valor) {
    if (valor > 0) this._idadePrivada = valor;
  },
};

objetoComSet.idade = 22;
objetoComSet.idade = -5;

objeto._idadePrivada; // 22
```

## Objeto _Object_

Objetos são instâncias de [_Object_](../objetos-nativos/objeto-object.md).

```javascript
let objeto = {
  chave: "valor",
};

objeto instanceof Object; // true
```

Objetos herdam propriedades de _Object.prototype_.

```javascript
let objeto = {
  chave: "valor",
};

funcao.toString(); // "[object Object]"
```
