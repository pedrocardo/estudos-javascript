# Funções globais

_Browsers_ e o _Node_ implementam funções globais não nativas.

Funções globais podem ser acessadas sem referenciar o objeto global.

```javascript
globalThis.setTimeout === setTimeout; // true
```

## Funções

- [Função _clearInterval_](#função-clearinterval)
- [Função _clearTimeout_](#função-cleartimeout)
- [Função _setInterval_](#função-setinterval)
- [Função _setTimeout_](#função-settimeout)

### Função _clearInterval_

A função _clearInterval_ cancela a execução de uma função _setInterval_.

Como argumento, a função deve receber o objeto retornado por uma função _setInterval_.

```javascript
let interval = setInterval(console.log, 1000, "isso não será executado");

clearInterval(interval);
```

### Função _clearTimeout_

A função _clearTimeout_ cancela a execução de uma função _setTimeout_.

Como argumento, a função deve receber o objeto retornado por uma função _setTimeout_.

```javascript
let timeout = setTimeout(console.log, 1000, "isso não será executado");

clearTimeout(timeout);
```

### Função _setInterval_

A função _setInterval_ define uma função _callback_ para ser executada a cada quantidade de milissegundos.

Como primeiro argumento, a função deve receber a função _callback_ que será executada.

Como segundo argumento, a função deve receber a quantidade de milissegundos.

Como argumentos seguintes, a função pode receber os argumentos para a função _callback_.

A função _setInterval_ retorna um _object_ que pode ser usado na função _clearInterval_.

```javascript
let funcaoCallback = function (frase) {
  console.log(frase);
};

let quantidadeMilissegundos = 1000;

setInterval(funcaoCallback, quantidadeMilissegundos, "um segundo e repetição");

// "um segundo e repetição"

// "um segundo e repetição"

// ...
```

### Função _setTimeout_

A função _setTimeout_ define uma função _callback_ para ser executada depois de uma quantidade de milissegundos.

Como primeiro argumento, a função deve receber a função _callback_ que será executada.

Como segundo argumento, a função deve receber a quantidade de milissegundos.

Como argumentos seguintes, a função pode receber os argumentos para a função _callback_.

A função _setTimeout_ retorna um _object_ que pode ser usado na função _clearTimeout_.

```javascript
let funcaoCallback = function (frase) {
  console.log(frase);
};

let quantidadeMilissegundos = 1000;

setTimeout(funcaoCallback, quantidadeMilissegundos, "um segundo para executar");

// "um segundo para executar"
```
