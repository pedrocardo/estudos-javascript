# _This_

_This_ é uma _keyword_ para se referir ao objeto executante de uma parte do código.

O valor de _this_ varia de acordo com o elemento em que ele está associado.

_This_ é normalmente utilizada em funções, classes e objetos.

Para ler esse _markdown_, considere que os códigos foram executados por um _browser_, em que _Window_ é o objeto global.

## Em métodos

Em métodos, _this_ se refere ao próprio objeto.

```javascript
let objeto = {
  metodo: function () {
    return this;
  },
};

objeto.metodo(); // {metodo: ƒ}
```

## Em funções

Em funções, _this_ se refere ao objeto que executa a função.

```javascript
function funcao() {
  return this;
}

funcao(); // Window
```

## Em funções de seta

Em funções de seta, _this_ irá sempre se referir ao objeto determinado na escrita da função.

```javascript
let funcaoDeSeta = () => this;

let objeto = {
  mostrarThis: funcaoDeSeta,
};

objeto.mostrarThis(); // Window
```

## Em funções construtoras e classes

Em funções construtoras e classes, _this_ pode ser utilizado para definir as propriedades dos objetos futuramente criados.

```javascript
function Pessoa(nome, sobrenome) {
  this.nome = nome;
  this.sobrenome = sobrenome;
}

let objetoPessoa = new Pessoa("Oliver", "Sykes");
```

## Sozinho

Sozinho, _this_ se refere ao objeto global.

```javascript
let objetoGlobal = this;

objetoGlobal === Window; // true
```
