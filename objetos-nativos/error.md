# _Error_

_Error_ é uma função nativa destinada para erros.

_Error_ pode ser utilizada como função construtora.

```javascript
typeof Error; // "function"

typeof new Error(); // "object"
```

## Função construtora

A função construtora _Error_ pode receber uma _string_ com a mensagem do erro.

```javascript
let erro = new Error("mensagem do erro");

erro; // Error: mensagem do erro
```

## Atributos de instância

O atributo _name_ é uma _string_ contendo o nome do erro.

```javascript
erro.name; // "Error"
```

O atributo _message_ é uma _string_ contendo a mensagem do erro.

```javascript
erro.message; // "mensagem do erro"
```

## Métodos de instância

O método _toString_ retorna uma _string_ com informações do erro.

```javascript
erro.toString(); // "Error: mensagem do erro"
```
