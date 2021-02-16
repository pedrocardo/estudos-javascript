# Instruções

Instruções são códigos que executam operações e não retornam valores.

## Expressões

Algumas instruções dependem da avaliação de expressões.

Algumas instruções avaliarão expressões como verdadeiras ou falsas com base nos valores retornados.

Expressões serão avaliadas como verdadeiras se retornarem um dos seguintes valores:

- _boolean_ _true_;
- _number_ diferente de zero e _NaN_;
- _object_;
- _string_ não vazia.

Expressões serão avaliadas como falsas se retornarem um dos seguintes valores:

- _boolean_ _false_;
- _null_;
- _number_ _NaN_;
- _number_ zero;
- _string_ vazia;
- _undefined_.

Por exemplo, a instrução _if_ avalia uma expressão como verdadeira ou falsa e, a partir disso, executa ou não um bloco de código.

```javascript
let expressao = "string não vazia, portanto verdadeira";

if (expressao) {
  // os códigos nesse bloco serão executados
}
```

## Lista de instruções

Esse _markdown_ contêm descrições sobre as seguintes instruções:

- [Instrução _async function_](#instrução-async-function)
- [Instrução _break_](#instrução-break)
- [Instrução _class_](#instrução-class)
- [Instrução _const_](#instrução-const)
- [Instrução _do while_](#instrução-do-while)
- [Instrução _export_](#instrução-export)
- [Instrução _for_](#instrução-for)
- [Instrução _for in_](#instrução-for-in)
- [Instrução _for of_](#instrução-for-of)
- [Instrução _function_](#instrução-function)
- [Instrução _import_](#instrução-import)
- [Instrução _let_](#instrução-let)
- [Instrução _return_](#instrução-return)
- [Instrução _switch_](#instrução-switch)
- [Instrução _throw_](#instrução-throw)
- [Instrução _var_](#instrução-var)
- [Instrução _while_](#instrução-while)
- [Instruções _if_ e _else_](#instruções-if-e-else)
- [Instruções _try_, _catch_ e _finally_](#instruções-try-catch-e-finally)

## Instrução _async function_

A instrução _async function_ declara uma função assíncrona.

```javascript
async function funcaoAssincrona() {}
```

## Instrução _break_

A instrução _break_ encerra o _loop_ ou _switch_ em que foi escrita.

```javascript
while (true) {
  break;
}
```

## Instrução _class_

A instrução _class_ declara uma classe.

```javascript
class Classe {}
```

A instrução _class_ pode ser combinada com a _keyword_ _extends_.

A _keyword_ _extends_ indica uma classe que será estendida pela declarada.

```javascript
class Classe extends ClasseEstendida {}
```

## Instrução _const_

A instrução _const_ declara constantes.

```javascript
const constante = "valor da constante";
```

## Instrução _do while_

A instrução _do while_ define um _loop_ que será executado enquanto a expressão avaliada for verdadeira.

O _loop_ será executado antes da avaliação da expressão.

```javascript
let expressao = false;

do {} while (expressao);
```

## Instrução _export_

A instrução _export_ define elementos exportados pelo módulo.

```javascript
let variavel = "valor da variável";

export { variavel };
```

## Instrução _for_

A instrução _for_ define um _loop_ que considera três expressões separadas por ponto e vírgula.

A primeira expressão é executada antes do _loop_ começar e, normalmente, é utilizada para criar uma variável de controle para as iterações.

A segunda expressão é uma condição avaliada a cada iteração do _loop_.

O _loop_ será executado enquanto a segunda expressão for verdadeira.

A terceira expressão é executada no final de cada iteração do _loop_.

```javascript
for (let contador = 0; contador < 10; contador++) {}
```

## Instrução _for in_

A instrução _for of_ define um _loop_ que será executado para cada propriedade enumerável de um objeto.

Nessa instrução, é possível identificar uma palavra para tratar genericamente as propriedades do objeto como _strings_.

```javascript
let objeto = {
  propriedade1: "valor da propriedade 1",
  propriedade2: "valor da propriedade 2",

for (propriedade in objeto) {
}
```

## Instrução _for of_

A instrução _for of_ define um _loop_ que será executado para cada elemento de um objeto iterável.

Nessa instrução, é possível identificar uma palavra para tratar genericamente os elementos do objeto.

```javascript
let vetor = ["elemento 1", "elemento 2"];

for (elemento of vetor) {
}
```

## Instrução _function_

A instrução _function_ declara uma função.

```javascript
function funcao() {}
```

## Instrução _import_

A instrução _import_ define elementos importados de outro módulo.

```javascript
import { variavel } from "./modulo.js";

variavel; // "valor da variável"
```

## Instrução _let_

A instrução _let_ declara variáveis.

```javascript
let variavel;
```

## Instrução _return_

A instrução _return_ define o valor a ser retornado pela função e encerra sua execução.

```javascript
function funcao() {
  return "retorno da função";
}
```

## Instrução _switch_

A instrução _switch_ avalia uma expressão, procura pelo valor correspondente em uma cláusula _case_ e executa os códigos a partir dessa.

A cláusula _default_ define códigos que serão executadas caso nenhuma cláusula _case_ corresponda a expressão avaliada por _switch_.

Para separar os blocos _case_, é necessário utilizar a instrução _break_.

```javascript
let expressao = 1;

switch (expressao) {
  case 1:
    break;
  case 2:
  case 3:
    break;
  default:
    break;
}
```

## Instrução _throw_

A instrução _throw_ lança uma exceção.

```javascript
throw new Error("mensagem da exceção");
```

## Instrução _var_

A instrução _var_ declara variáveis.

```javascript
var variavel;
```

## Instrução _while_

A instrução _do while_ define um _loop_ que será executado enquanto a expressão avaliada for verdadeira.

O _loop_ será executado depois da avaliação da expressão.

```javascript
let expressao = false;

while (expressao) {}
```

## Instruções _if_ e _else_

A instrução _if_ define um bloco de código que será executado caso a expressão avaliada seja verdadeira.

```javascript
let expressao = true;

if (expressao) {
}
```

A instrução _else_ define um bloco de código que será executado caso a expressão avaliada por _if_ seja falsa.

As instruções _if_ e _else_ podem ser combinadas, criando encadeamentos de condições.

```javascript
let expressao1 = false,
  expressao2 = true;

if (expressao1) {
} else if (expressao2) {
} else {
}
```

## Instruções _try_, _catch_ e _finally_

A instrução _try_ define um bloco de código que será executado, podendo ser complementado por _catch_ e _finally_.

A instrução _catch_ define um bloco de código que será executado caso ocorra uma exceção no bloco _try_.

Na instrução _catch_, é possível identificar uma palavra para manipular a exceção esperado.

```javascript
try {
} catch (excecao) {}
```

A instrução _finally_ define um bloco com código que será executado independentemente de exceções.

```javascript
try {
} catch (excecao) {
} finally {
}
```
