# Declarações

Declarações definem identificadores e suas propriedades.

Declarações são feitas com instruções.

```javascript
var variavel;
```

## Inicialização

Identificadores podem receber valores em sua declaração. Isso é chamado de inicialização.

```javascript
var variavel = "valor da variável";
```

Caso uma variável não seja inicializada assim que declarada, ela receberá o valor _undefined_.

```javascript
var variavel;

variavel; // undefined
```

## Sobrescrita

Alguns identificadores podem ser declarados novamente em outros trechos de código. Isso é chamado de sobrescrita.

```javascript
var variavel;

var variavel = "a variável foi sobrescrita";
```

## Instrução _async function_

A instrução _async function_ declara uma função assíncrona.

Funções assíncronas podem ser sobrescritas.

Funções assíncronas respeitam apenas escopos de funções.

```javascript
async function funcaoAssincrona() {}
```

## Instrução _class_

A instrução _class_ declara uma classe.

Classes não podem ser sobrescritas.

```javascript
class Classe {}
```

## Instrução _const_

A instrução _const_ declara constantes.

Constantes precisam ser inicializadas e não podem ser sobrescritas.

Constantes respeitam escopos de bloco e de funções.

```javascript
const constante = "valor da constante";
```

## Instrução _function_

A instrução _function_ declara uma função.

Funções podem ser sobrescritas.

Funções respeitam apenas escopos de funções.

```javascript
function funcao() {}
```

## Instrução _let_

A instrução _let_ declara variáveis.

Variáveis declaradas com _let_ não precisam ser inicializadas e não podem ser sobrescritas.

Variáveis declaradas com _let_ respeitam escopos de bloco e de funções.

```javascript
let variavel;
```

## Instrução _var_

A instrução _var_ declara variáveis.

Variáveis declaradas com _var_ não precisam ser inicializadas e podem ser sobrescritas.

Variáveis declaradas com _var_ respeitam apenas escopos de funções.

```javascript
var variavel;
```

## _Hoisting_

_Hoisting_ implica que declarações utilizando _var_ e _function_ são processadas antes da execução do restante do código.

_Hoisting_ possibilita o uso de variáveis declaradas com _var_ e funções antes de suas declarações no código.

```javascript
varHoisting = "essa variável pode ser manipulada antes de sua declaração";

var varHoisting;

funcaoHoisting(); // "essa função foi chamada antes de sua declaração"

function funcaoHoisting() {
  return "essa função foi chamada antes de sua declaração";
}
```

## Constantes e objetos

Objetos são atribuídos através da referência ao seu endereço na memória.

Com isso, mesmo que um objeto seja atribuído à uma constante, suas propriedades poderão ser modificadas.

```javascript
const objeto = {
  cor: "amarelo",
};

objeto.cor = "laranja";

objeto.cor; // "laranja"
```

Como vetores são objetos, os seus elementos também podem ser alterados.

```javascript
const vetorConstante = ["árvore", "casa", "bicicleta"];

vetorConstante.push("quintal");

vetorConstante[1] = "cadeira";

vetorConstante; // [ "árvore", "cadeira", "bicicleta", "quintal" ]
```
