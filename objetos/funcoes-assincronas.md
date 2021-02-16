# Funções assíncrona

Funções assíncronas são como [funções](funcoes.md) normais, mas possibilitam uma forma simplificada de trabalhar com promessas.

## Declaração

Funções assíncronas devem ser declaradas com a instrução _async function_.

```javascript
async function funcaoAssincrona() {}
```

## Expressões

Funções assíncronas podem ser manipuladas como expressões, ou seja, tratadas como valores.

```javascript
(async function expressao() {
  return "isso é uma expressão de função assíncrona";
});
```

Expressões de funções assíncronas podem ser anônimas.

```javascript
(async function () {
  return "isso é uma expressão de função assíncrona anônima";
});
```

## Retorno

Funções assíncronas retornam objetos _Promise_.

O valor indicado na instrução _return_ será amarrado a um objeto _Promise_, e esse será retornado.

```javascript
async function funcaoAssincrona() {
  return "valor";
}

funcaoAssincrona(); // Promise {<fulfilled>: "valor"}
```

Caso nenhum valor seja retornado pela função, será amarrado _undefined_ ao objeto _Promise_ retornado.

```javascript
async function funcaoAssincrona() {}

funcaoAssincrona(); // Promise {<fulfilled>: undefined}
```

## Erros

Funções assíncronas retornam uma promessa rejeitada quando um erro é disparado.

O valor indicado pelo erro será amarrado ao objeto _Promise_ rejeitado, e esse será retornado.

```javascript
async function funcaoAssincrona() {
  throw "valor rejeitado";
}

funcaoAssincrona(); // Promise {<rejected>: "valor rejeitado"}
```

## Operador _await_

Em funções assíncronas, é possível utilizar o operador _await_.

O operador _await_ define que a execução do código da função só continuará quando a promessa indicada finalizar.

No exemplo a seguir, a função assíncrona não utiliza o _await_.

Com isso, a função assíncrona executará a _callback_ _onFulfilled_ depois do resto do código.

```javascript
async function funcaoAssincronaSemAwait() {
  Promise.resolve(1).then(function onFulfilled() {
    console.log("código no método then");
  });

  console.log("código na função");
}

funcaoAssincronaSemAwait();

// "código na função"
// "código no método then"
```

Neste outro exemplo, a função assíncrona utiliza o _await_.

Com isso, a função assíncrona executará a _callback_ _onFulfilled_ antes do resto do código.

```javascript
async function funcaoAssincronaComAwait() {
  await Promise.resolve(1).then(function onFulfilled() {
    console.log("código do método then");
  });

  console.log("código da função");
}

funcaoAssincronaComAwait();

// "código no método then"
// "código na função"
```

Com _await_, os valores das promessas podem ser manipulados sem o método _then_ ou _catch_.

```javascript
async function funcaoAssincronaComAwait() {
  let valorDaPromessa = await Promise.resolve(10);

  valorDaPromessa + 5; // 15
}
```
