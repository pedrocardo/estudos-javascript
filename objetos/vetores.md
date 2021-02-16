# Vetores

Vetores são listas de valores referenciados por índices, começando em zero.

Um mesmo vetor pode ter dados de diferentes tipos.

## Notação literal

A notação literal de vetores é uma lista de valores separados por vírgula. Essa lista deve ser envolvida por colchetes.

```javascript
let vetor = ["string", 4, true];
```

## Valores

Vetores também são objetos, e suas propriedades são índices começando em zero.

Para acessar as propriedades de um vetor, é necessário utilizar a notação colchetes com _number_.

```javascript
let vetor = ["maçã", "banana", "melancia"];

vetor[0]; // "maçã"
vetor[1]; // "banana"
vetor[2]; // "melancia"
```

Para atribuir uma nova propriedade a um vetor, basta utilizar a notação colchetes com um índice ainda não preenchido.

```javascript
let vetor = ["tesoura"];

vetor[1] = "lápis";

vetor; // [ "tesoura", "lápis" ]
```

## Atributo _length_

Vetores possuem um atributo de instância chamado _length_. Esse atributo é do tipo _number_ e indica a quantidade de elementos do vetor.

```javascript
let vetor = ["maçã", "banana", "melancia"];

vetor.length; // 3
vetor["length"]; // 3
```

## Iteração

Vetores são objetos iteráveis e podem ser percorridos pela instrução _for of_.

```javascript
let palavras = ["verbo", "substantivo", "adjetivo"];

let resultado = "";

for (nome of palavras) {
  resultado = resultado + " " + nome;
}

resultado; // "verbo substantivo adjetivo"
```

## Objeto _Array_

Vetores são objetos instâncias de [_Array_](../objetos-nativos/objeto-array.md).

```javascript
let vetor = [];

vetor instanceof Array; // true

vetor instanceof Object; // true
```

Vetores herdam propriedades de _Array.prototype_.

```javascript
let vetor = ["substantivo", "verbo", "adjetivo"];

vetor.toString(); // "substantivo,verbo,adjetivo"
```
