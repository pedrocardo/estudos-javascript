# JSON

JSON é um acrônimo para _JavaScript Object Notation_ - um padrão de escrita de texto utilizado para transferência de dados entre sistemas.

JSON é baseado na notação literal de objetos do JavaScript.

A extensão de arquivos de texto com a notação JSON é _.json_.

JSON pode ser manipulado como uma _string_.

## Tipos de dados

JSON suporta dados dos tipo _boolean_, _number_, _string_, _null_, _object_ e _array_.

```json
{
  "boolean": true,
  "number": 2601,
  "string": "texto",
  "null": null,
  "objeto": {
    "nome": "Bell",
    "sobrenome": "Hooks"
  },
  "vetor": ["maçã", "banana", "melancia"]
}
```

## Objeto _JSON_

Textos com a notação JSON e objetos podem ser manipulados a partir do objeto [_JSON_](../objetos-nativos/objeto-json.md).

```javascript
JSON.parse('{"nome":"Daniel","sobrenome":"Sloss"}'); // { nome: "Daniel", sobrenome: "Sloss" }

JSON.stringify({ nome: "Taiga", sobrenome: "Aisaka" }); // "{"nome":"Taiga","sobrenome":"Aisaka"}"
```
