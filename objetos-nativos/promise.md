# _Promise_

_Promise_ é uma função nativa destinada para representar o eventual sucesso ou falha de uma operação assíncrona.

_Promise_ pode ser utilizada como função construtora.

```javascript
typeof Promise; // "function"

typeof new Promise(); // "object"
```

## Função construtora

A função construtora _Promise_ recebe uma função _callback_ que será executada com a construção do objeto. Para organização, essa função _callback_ será chamada de _executor_.

```javascript
let promessa = new Promise(function executor() {});
```

A função _executor_ pode ter dois parâmetros, comumente chamados de _resolve_ e _reject_.

Os parâmetros _resolve_ e _reject_ representarão duas funções que podem ser chamadas dentro do código de _executor_.

```javascript
let promessa = new Promise(function executor(resolve, reject) {});
```

A função _resolve_ deve ser chamada quando as operações feitas dentro da função _executor_ derem certo.

O argumento recebido por _resolve_ será amarrado ao objeto _Promise_. Esse valor poderá ser pego no futuro pelo método de instância _then_.

```javascript
let promessa = new Promise(function executor(resolve, reject) {
  resolve("valor de sucesso da operação assíncrona");
});
```

A função _reject_ deve ser chamada quando as operações feitas dentro da função _executor_ derem errado.

O argumento recebido por _reject_ será amarrado ao objeto _Promise_. Esse valor poderá ser pego no futuro pelo método de instância _catch_.

```javascript
let promessa = new Promise(function executor(resolve, reject) {
  reject("valor de falha da operação assíncrona");
});
```

As funções _resolve_ e _reject_ finalizam a execução da função _executor_. Ou seja, funcionam como a instrução _return_.

```javascript
let promessa = new Promise(function executor(resolve, reject) {
  resolve("valor de sucesso da operação assíncrona");

  console.log("essa instrução não será executada");
});
```

## Métodos estáticos

- [Método _all_](#método-all)
- [Método _race_](#método-race)

### Método _all_

O método _all_ recebe um vetor de objetos _Promise_ e espera todas as funções _executor_ serem finalizadas.

O método _all_ retorna um objeto _Promise_.

A _promise_ retornada por _all_ conterá um vetor com todos os valores das _promises_ passadas no argumento.

Se qualquer _promise_ for rejeitada, o método _all_ irá retornar um objeto _Promise_ com o valor de rejeição.

```javascript
let promesssa1 = new Promise(function executor(resolve, reject) {
  resolve("primeira promessa");
});

let promessa2 = new Promise(function executor(resolve, reject) {
  resolve("segunda promessa");
});

Promise.all([promessa1, promessa2]).then(function onFulfilled(resultado) {
  return resultado; // [ "primeira promessa", "segunda promessa" ]
});
```

### Método _race_

O método _race_ recebe um vetor de objetos _Promise_ e espera apenas uma função _executor_ ser finalizada.

O método _race_ retorna um objeto _Promise_.

A _promise_ retornada por _race_ conterá o valor de sucesso ou falha da primeira _promise_ completa.

```javascript
let promessa1 = new Promise(function executor(resolve, reject) {
  setTimeout(resolve, 500, "primeira promessa");
});

let promessa2 = new Promise(function executor(resolve, reject) {
  resolve("segunda promessa");
});

Promise.race([promessa1, promessa2]).then(function onFulfilled(resultado) {
  return resultado; // "segunda promessa"
});
```

## Métodos de instâncias

Instâncias de _Promise_ herdam métodos de _Promise.prototype_.

- [Método _catch_](#método-catch)
- [Método _finally_](#método-finally)
- [Método _then_](#método-then)

### Método _catch_

O método _catch_ pode ser chamado para manipular o valor de falha de um objeto _Promise_.

Como argumento, _catch_ pode receber uma função _callback_, comumente chamada de _onRejected_.

A função _onRejected_ deve ter um parâmetro que representa o valor de falha da promessa.

O retorno de _onRejected_ será amarrado a nova _promise_ retornada por _catch_.

```javascript
let promessa = new Promise(function executor(resolve, reject) {
  reject("problema da promessa");
});

let promessaComProblema = promessa.catch(function onRejected(problema) {
  return problema; // "problema da promessa"
});
```

### Método _finally_

O método _finally_ retorna um novo objeto _Promise_.

Como argumento, _finally_ pode receber uma função _callback_, comumente chamada de _onFinally_.

O método _finally_ pode ser útil no final de cadeias de promessas, finalizando os processos realizados.

```javascript
let promessa = new Promise(function executor(resolve, reject) {
  resolve("string");
});

let novaPromessa = promessa.then(function onFulfilled(valor) {
  return valor + " nova parte da string"; // "string + nova parte da string"
});

novaPromessa.finally(function onFinally() {
  console.log("final das promises");
});
```

### Método _then_

O método _then_ pode ser chamado para manipular o valor de sucesso de um objeto _Promise_.

Como argumento, _then_ pode receber uma função _callback_, comumente chamada de _onFulfilled_.

A função _onFulfilled_ deve ter um parâmetro que representa o valor de sucesso da promessa.

O retorno de _onFulfilled_ será amarrado a nova _promise_ retornada por _then_.

Como o método _then_ retorna um novo objeto _Promise_, é possível criar encadeamentos.

```javascript
let promessa = new Promise(function executor(resolve, reject) {
  resolve("valor");
});

let novaPromessa = promessa.then(function onFulfilled(valorSucesso) {
  return valorSucesso + " + esse valor é um sucesso"; // "valor + esse valor é um sucesso"
});

let ultimaPromessa = novaPromessa.then(function onFulfilled(valor) {
  return valor + " + e chegou aqui"; // "bom + esse valor é um sucesso + e chegou aqui"
});
```

## Uso de promessas

Promessas são objetos destinados para lidar com funções assíncronas.

Ao utilizar o construtor _Promise_, a função _callback_ passada como argumento será executada junto com a criação do objeto _Promise_. É nessa função que devem ser passadas operações assíncronas, como _setTimeout_ ou buscas em servidores.

```javascript
console.log("primeira parte síncrona");

let promessa = new Promise(function executor(resolve, reject) {
  console.log("segunda parte síncrona");
});

console.log("terceira parte síncrona");

// "primeira parte síncrona"
// "segunda parte síncrona"
// "terceira parte síncrona"
```

As funções _callback_ passadas como argumento dos métodos _then_ e _catch_ só serão executadas com a conclusão da _promise_ através de _resolve_ ou _reject_.

As funções _callback_ passadas como argumento dos métodos _then_ e _catch_ também só serão executadas com a conclusão do código síncrono no _loop_ de eventos.

```javascript
let promessa = new Promise(function executor(resolve, reject) {
  resolve("valor resolvido da promessa");
});

promessa.then(function onFulfilled(valorSucesso) {
  console.log(valorSucesso);
});

console.log("código síncrono");

// "código síncrono"
// "valor resolvido da promessa"
```

## Encadeamento

Como os métodos _then_ e _catch_ retornam objetos _Promise_, é possível encadeá-los. Com isso, um método _catch_ pode receber e tratar qualquer exceção na cadeia.

```javascript
new Promise(function executor(resolve, reject) {
  resolve(new Error("valor de falha"));
})
  .then(function onFulfilled(valor) {
    return "valor qualquer de sucesso";
  })
  .catch(function onReject(problema) {
    console.log(problema); // Error: valor de falha
  });
```
