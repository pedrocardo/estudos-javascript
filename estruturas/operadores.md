# Operadores

Operadores executam ações e retornam valores.

## Lista de operadores

Esse _markdown_ contêm descrições sobre os seguintes operadores:

- [Operador _await_](#operador-await)
- [Operador de agrupamento](#operador-de-agrupamento)
- [Operador de atribuição](#operador-de-atribuição)
- [Operador de atribuição ternária](#operador-de-atribuição-ternária)
- [Operador de desestruturação](#operador-de-desestruturação)
- [Operador _delete_](#operador-delete)
- [Operador _in_](#operador-in)
- [Operador _instanceof_](#operador-instanceof)
- [Operador lógico _and_](#operador-lógico-and)
- [Operador lógico de coalescência nula](#operador-lógico-de-coalescência-nula)
- [Operador lógico de negação](#operador-lógico-de-negação)
- [Operador lógico _or_](#operador-lógico-or)
- [Operador _new_](#operador-new)
- [Operador _rest_](#operador-rest)
- [Operador _spread_](#operador-spread)
- [Operador _typeof_](#operador-typeof)
- [Operadores aritméticos](#operadores-aritméticos)
- [Operadores comparativos](#operadores-comparativos)
- [Operadores de igualdade e desigualdade](#operadores-de-igualdade-e-desigualdade)
- [Operadores de incremento e decremento](#operadores-de-incremento-e-decremento)

## Operador _await_

O operador _await_ só pode ser utilizado em funções assíncronas.

O operador _await_ indica que a execução do código deve esperar o retorno de uma promessa.

O operador _await_ retorna o valor amarrado com a promessa.

```javascript
async function funcaoAssincrona() {
  let valor = await Promise.resolve("valor da promessa");

  valor; // "valor da promessa"
}
```

## Operador de agrupamento

O operador de agrupamento prioriza operações, sobrepondo a precedência de operadores.

O operador de agrupamento são parênteses que envolvem as operações a serem priorizadas.

```javascript
2 * (4 + 2); // 12
```

## Operador de atribuição

O operador de atribuição armazena um valor em uma variável ou constante.

```javascript
variavel = 1;
```

O operador de atribuição pode ser atecedido por qualquer operador aritmético.

Com isso, será realizada a operação aritmética com o valor da variável e o indicado.

O resultado da operação aritmética será atribuído como novo valor da variável.

```javascript
let variavel = 1;

variavel += 2;

variavel; // 3
```

## Operador de atribuição ternária

O operador de atribuição ternária checa uma condição.

Caso a condição seja verdadeira, será atribuído o primeiro valor.

Caso a condição seja falsa, será atribuído o segundo valor.

```javascript
let idade = 20;

let maiorDeIdade = idade >= 18 ? "Sim" : "Não";

maiorDeIdade; // "Sim"
```

## Operador de desestruturação

O operador de desestruturação atribui os valores de propriedades de objetos à variáveis ou constantes.

```javascript
let treinador = {
  nome: "Ethan",
};

let { nome } = treinador;

nome; // "Ethan"
```

Variáveis e constantes podem receber nomes diferentes das propriedades do objeto.

```javascript
let cidade = {
  nome: "New Bark Town",
};

let { nome: newBarkTown } = cidade;

newBarkTown; // "New Bark Town"
```

Variáveis e constantes podem receber valores padrão caso seus nomes não correspondam a uma propriedade do objeto.

```javascript
let pokemon = {
  nome: "Chikorita",
};

let { tipo = "não identificado" } = pokemon;

tipo; // "não identificado"
```

O operador de desestruturação pode ser utilizado em vetores.

```javascript
let frutas = ["maçã", "banana", "laranja"];

let [primeiraFruta, , terceiraFruta] = frutas;

primeiraFruta; // "maçã"

terceiraFruta; // "laranja"
```

## Operador _delete_

O operador _delete_ exclui uma propriedade de um objeto. Essa operação retorna um _boolean_.

Caso a operação tenha sido realizada com sucesso, _delete_ retornará _true_.

Caso a operação não tenha sido realizada com sucesso, _delete_ retornará _false_.

```javascript
let treinador = {
  nome: "Ethan",
  cidade: "New Bark Town",
};

delete treinador.cidade; // true

treinador; // { nome: "Ethan" }
```

## Operador _in_

O operador _in_ checa se um valor é propriedade de um objeto. Essa operação retorna um _boolean_.

```javascript
let computador = {
  processador: "Intel",
};

"processador" in computador; // true
```

## Operador _instanceof_

O operador _instanceof_ checa se um objeto é instância de uma função. Essa operação retorna um _boolean_.

```javascript
let palavras = ["verbete", "diferente", "ênfase"];

palavras instanceof Array; // true

palavras instanceof Object; // true
```

## Operador lógico _and_

O operador lógico _and_ avalia duas expressões.

Caso o primeiro valor avaliado seja verdadeiro, o segundo será retornado.

Caso o primeiro valor avaliado seja falso, ele será retornado.

```javascript
true && true; // true

true && false; // false

false && false; // false
```

Os valores _false_, _NaN_, _null_, _strings_ vazias, _undefined_ e zero são considerados falsos.

```javascript
false && "o primeiro valor é falso"; // false

0 && "o primeiro valor é falso"; // 0

"" && "o primeiro valor é falso"; // ""
```

## Operador lógico de coalescência nula

O operador lógico de coalescência nula avalia duas expressões.

Caso o primeiro valor avaliado seja verdadeiro, ele será retornado.

Caso o primeiro valor avaliado seja falso, o segundo valor será retornado.

Os valores _false_, _NaN_, _undefined_ e _null_ são considerados falsos.

```javascript
true ?? "o primeiro valor é verdadeiro"; // true

false ?? "o primeiro valor é falso"; // "o primeiro valor é falso"

undefined ?? "o primeiro valor é falso"; // "o primeiro valor é falso"

null ?? "o primeiro valor é falso"; // "o primeiro valor é falso"
```

## Operador lógico de negação

O operador lógico de negação avalia um valor e retorna o _boolean_ contrário.

```javascript
!true; // false

!false; // true
```

## Operador lógico _or_

O operador lógico _or_ avalia duas expressões.

Caso o primeiro valor avaliado seja verdadeiro, ele será retornado.

Caso o primeiro valor avaliado seja falso, o segundo será retornado.

```javascript
true || true; //  true

true || false; // true

false || false; // false
```

Os valores _false_, _NaN_, _null_, _strings_ vazias, _undefined_ e zero são considerados falsos.

```javascript
true || "o primeiro valor é verdadeiro"; // true

false || "o primeiro valor é falso"; // "o primeiro valor é falso"

0 || "o primeiro valor é falso"; // "o primeiro valor é falso"

"" || "o primeiro valor é falso"; // "o primeiro valor é falso"
```

## Operador _new_

O operador _new_ cria um objeto a partir de uma função construtora. Essa operação retorna um _objeto_.

```javascript
let objetoNumero = new Number(23);
```

## Operador _rest_

O operador _rest_ define o parâmetro de uma função como um vetor.

Os argumentos passados para a função serão agrupados como elementos do vetor.

```javascript
function funcao(...parametros) {
  return parametros;
}

funcao(10, 20, 30, "palavra"); // [ 10, 20, 30, "palavra" ]
```

## Operador _spread_

O operador _spread_ distribui as propriedades de um objeto.

```javascript
let estado = {
  nome: "São Paulo",
};

let estadoComDetalhes = {
  ...estado,
  pais: "Brasil",
};

estadoComDetalhes; // {nome: "São Paulo", pais: "Brasil"}
```

O operador _spread_ pode ser utilizado com vetores e _strings_.

```javascript
let filmes = ["Titanic", "Mad Max"];

let maisFilmes = ["E.T.", ...filmes];

maisFilmes; // [ "Titanic", "Mad Max", "E.T" ]
```

O operador _spread_ pode ser utilizado com vetores.

```javascript
function somar(a, b, c) {
  return a + b + c;
}

let numeros = [1, 2, 3];

somar(...numeros); // 6
```

## Operador _typeof_

O operador _typeof_ indica o tipo de um valor. Essa operação retorna uma _string_.

O operador _typeof_ pode indicar _number_, _string_, _boolean_, _undefined_, _object_ ou _function_.

```javascript
typeof 1; // "number"
```

## Operadores aritméticos

Operadores aritméticos realizam operações matemáticas e retornam um _number_.

No código a seguir, os operadores são respectivamente soma, subtração, divisão, multiplicação, exponenciação e resto de divisão.

```javascript
10 + 2; // 12
10 - 2; // 8
10 / 2; // 5
10 * 2; // 20
10 ** 2; // 100
10 % 2; // 0
```

O operador de soma também pode ser utilizado para concatenação de _strings_. Essa operação retorna uma _string_.

```javascript
"10" + "2"; // "102"
```

## Operadores comparativos

Operadores comparativos checam a relação entre dois valores. Essas operações retornam um _boolean_.

No código a seguir, os operadores são respectivamente maior que, menor que, maior ou igual que e menor ou igual que.

```javascript
2 > 1; // true
2 < 1; // false
2 >= 1; // true
2 <= 1; // false
```

## Operadores de igualdade e desigualdade

O operador de igualdade checa se dois valores são iguais e retorna um _boolean_.

```javascript
"1" == 1; // true
```

O operador de igualdade estrita checa se dois valores são em iguais, considerando seus tipos. Essa operação retorna um _boolean_.

```javascript
1 === 1; // true

"1" === 1; // false
```

O operador de desigualdade checa se valores não são iguais e retorna um _boolean_.

```javascript
"1" != 1; // false
```

O operador de desigualdade estrita checa se dois valores são em diferentes, considerando seus tipos. Essa operação retorna um _boolean_.

```javascript
1 !== 1; // false

"1" !== 1; // true
```

## Operadores de incremento e decremento

O operador de incremento soma uma unidade ao valor especificado. Essa operação retorna um _number_.

O operador de incremento pode ser utilizado como sufixo ou prefixo, retornando o valor antes de incrementá-lo ou não.

```javascript
let variavel = 1;

variavel++; // 1

variavel; // 2

++variavel; // 3

variavel; // 2
```

O operador de decremento pode ser utilizado como sufixo ou prefixo.

O operador de decremento pode ser utilizado como sufixo ou prefixo, retornando o valor antes de decrementá-lo ou não.

```javascript
let variavel = 3;

variavel--; // 3

variavel; // 2

--variavel; // 1

variavel; // 1
```
