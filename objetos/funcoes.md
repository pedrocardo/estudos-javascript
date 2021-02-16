# Funções

Funções são sub-rotinas que podem ser declaradas e executadas. Funções empacotam instruções e são definidas com um nome.

Quando declarada, uma função pode ser executada várias vezes e evitar repetição de código.

## Declaração

Funções podem ser declaradas com a instrução _function_.

```javascript
function funcao() {}
```

## Expressões

Funções podem ser manipuladas como expressões, ou seja, tratadas como valores.

```javascript
(function expressao() {
  return "isso é uma expressão de função";
});
```

Expressões de funções podem ser anônimas.

```javascript
(function () {
  return "isso é uma expressão de função anônima";
});
```

## Execução

Para executar uma função, basta escrever seu nome e parênteses.

```javascript
funcao();
```

## Parâmetros e argumentos

Funções podem ter parâmetros e manipulá-los em suas instruções.

Parâmetros são _placeholders_ de argumentos que a função pode receber.

```javascript
function somar(parametroUm, parametroDois) {
  parametroUm + parametroDois;
}
```

Argumentos são valores passados entre os parênteses na chamada da função.

```javascript
somar(3, 5); // 8
```

Não existe erro caso o número de argumentos não seja igual ao número de parâmetros.

Caso sejam passados mais argumentos, os extras serão ignorados.

Caso sejam passados menos argumentos, os faltantes receberão o valor _undefined_.

Para evitar o segundo caso, é possível atribuir valores padrões aos parâmetros.

```javascript
function somar(parametroUm = 10, parametroDois = 2) {
  return parametroUm + parametroDois;
}

subtrair(); // 12
```

## Retorno

Funções podem retornar um valor com a instrução _return_. Será retornado _undefined_ caso nada seja definido.

Após a instrução _return_, nada mais será executado na função. Isso pode ser utilizado para encerrar a subrotina.

```javascript
function somar(parametroUm, parametroDois) {
  return parametroUm + parametroDois;

  return "essa instrução não será executada";
}

let resultado = somar(4, 2);

resultado; // 6
```

## Primeira classe

Funções são de primeira classe, ou seja, podem ser tratadas como valores.

Funções podem ser atribuídas a variáveis.

```javascript
let variavel = function () {
  return "essa função foi atribuída a uma variável";
};
```

Funções podem ser passadas como argumento de outras funções.

```javascript
function funcao(funcaoParametro) {
  return funcaoParametro();
}

function funcaoArgumento() {
  return "essa função foi passada como argumento de outra função";
}

funcao(funcaoArgumento()); // "essa função foi passada como argumento de outra função"
```

Funções podem ser retornadas de outras funções.

```javascript
function funcao() {
  function funcaoInterna() {
    return "essa função foi retornada por outra função";
  }

  return funcaoInterna;
}

let funcaoInternaRecebida = funcao();

funcaoInternaRecebida(); // "essa função foi retornada de outra função"
```

## Expressões imediatamente invocadas

Expressões de funções podem ser imediatamente invocadas.

Essas funções são chamadas de _immediately invoked function expression_ (IIFE).

```javascript
(function (palavra) {
  return `IIFE: ${palavra}`;
})("immediately invoked function expression"); // "IIFE: immediately invoked function expression"
```

## Expressões funções de seta

Uma outra forma de utilizar expressões de funções são com setas.

Funções de seta são anônimas, têm uma sintaxe reduzida e _this_ fixo.

```javascript
let funcaoDeSeta = () => {
  return "olá";
};

let funcaoDeSeta = (nome) => {
  return `olá, ${nome}`;
};
```

Quando a única instrução da função é o _return_, é possível omiti-lo.

```javascript
let funcaoDeSeta = () => "olá";

let funcaoDeSeta = (numero1, numero2) => numero1 + numero2;
```

Para retornar um objeto, é necessário envolvê-lo por parênteses.

```javascript
let funcaoDeSeta = () => ({
  nome: "George",
  sobrenome: "Boole",
});
```

## _Closure_

Funções podem acessar o escopo em que foram declaradas mesmo quando chamadas fora deles.

As funções que realizam esse acesso são chamadas de _closures_.

```javascript
function funcaoExterna() {
  let variavel = "variável no escopo externo da função";

  let funcaoInterna = function () {
    return variavel;
  };

  return funcaoInterna;
}

let funcaoInternaRecebida = funcaoExterna();

funcaoInternaRecebida(); // "variável no escopo externo da função"
```

É possível combinar IIFE com _closures_ para criar funções com variáveis privadas.

```javascript
let contar = (function () {
  let numero = 0;

  return function () {
    numero += 1;
    return `${numero}`;
  };
})();

contar(); // 1
contar(); // 2
contar(); // 3
```

Também é possível retornar objetos com variáveis privadas criadas nas funções.

```javascript
function criarObjeto() {
  let numero = 0;

  let objeto = {
    somar() {
      numero += 1;
      return numero;
    },
  };

  return objeto;
}

let objeto = criarObjeto();

objeto.somar(); // 1
objeto.somar(); // 2
objeto.somar(); // 3
```

## Funções construtoras

Funções construtoras são moldes para criar objetos. Por convenção, os nomes dessas funções devem começar com letra maiúscula.

```javascript
function Pessoa(nomeParametro, sobrenomeParametro) {
  this.nome = nome;
  this.sobrenome = sobrenome;

  this.saudar = function () {
    return `olá, meu nome é ${this.nome} ${this.sobrenome}`;
  };
}
```

Para instanciar um objeto a partir de uma função construtora, basta utilizar o operador _new_.

```javascript
let objetoPessoa = new Pessoa("Andrew", "Garfield");

objetoPessoa.saudar(); // "olá, meu nome é Andrew Garfield"
```

Funções construtoras podem utilizar _closures_ para criar variáveis privadas para os objetos.

```javascript
function Pessoa(segredoParametro) {
  let segredo = segredoParametro;

  this.contarSegredo = function () {
    return segredo;
  };
}

let pessoaObjeto = new Pessoa("segredo só pode ser acessado com contarSegredo");

pessoaObjeto.segredo; // undefined
pessoaObjeto.contarSegredo(); // "segredo só pode ser acessado com contarSegredo"
```

É possível utilizar a função construtora sem o operador _new_, fazendo com que sejam criadas variáveis no escopo global.

Para evitar esse problema, basta utilizar uma instrução condicional.

```javascript
function Animal(nome) {
  if (this instanceof Animal) {
    this.nome = nome;
  } else {
    return new Animal(nome);
  }
}

let objetoAnimal = Animal("girafa");

objetoAnimal; // { nome: "girafa" }
```

## Objeto _Function_

Funções, declaradas ou expressões, são objetos instâncias de [_Function_](../objetos-nativos/objeto-function.md).

```javascript
function funcao(parametro) {
  return "isso é uma função";
}

funcao instanceof Function; // true
funcao instanceof Object; // true
```

Funções herdam propriedades de _Function.prototype_.

```javascript
function funcao(parametro) {
  return "isso é uma função";
}

funcao.toString(); // "function funcao(parametro) { return "isso é uma função" }"
```
