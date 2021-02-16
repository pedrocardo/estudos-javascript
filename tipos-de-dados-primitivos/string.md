# _String_

_String_ é um tipo de dado primitivo. 

Dados do tipo _string_ representam textos.

```javascript
typeof "texto"; // "string"
```

_String_ possui três formas literais.

```javascript
"string com aspas duplas";
'string com aspas simples';
`string com acentos grave`;
```

Para escrever caracteres especiais em uma _string_, é necessário utilizar a notação _escape_ com barra invertida.

```javascript
"\0 \" \' \\ \n \r \v \t \b \f";

```

Para acessar um caractere em uma _string_, é necessário utilizar a notação colchetes.

A primeira posição de caractere em uma _string_ é zero.

```javascript
"string"[4]; // "i"
```

## Template literals

_Strings_ com acentos grave são chamadas de _template literals_ e podem utilizar _placeholders_, pular linhas e espaçar o texto.

Em uma _template string_, os _placeholders_ são determinados por cifrão e chaves e podem receber qualquer valor ou expressão.

```javascript
let valor = 10;

`Com template literals é possível exibir valores de variáveis ${valor} e retornos de expressões ${5 + 4}.

Também é possível pular linhas e
  espaçar o texto.`;
```

## Objeto empacotador

O tipo primitivo _string_ possui um objeto empacotador chamado [_String_](../objetos-nativos/objeto-empacotador-string.md).

Com esse objeto, dados _string_ são encapsulados implicitamente, tornando possível acessar métodos de _String.prototype_.

```javascript
"string".toUpperCase(); // "STRING"
```
