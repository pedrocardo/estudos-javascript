# _JSON_

_JSON_ é um objeto nativo destinado para manipulação de textos JSON.

As propriedades de _JSON_ são acessadas estaticamente.

```javascript
typeof JSON; // "object"
```

## Métodos estáticos

- [Método _parse_](#método-parse)
- [Método _stringify_](#método-stringify)

### Método _parse_

O método _parse_ retorna um objeto a partir da conversão de uma _string_ JSON.

```javascript
JSON.parse('{"nome":"Jake","sobrenome":"Peralta"}'); // { nome: "Jake", sobrenome: "Peralta" }
```

### Método _stringify_

O método _stringify_ retorna uma _string_ JSON a partir da conversão de um objeto.

```javascript
JSON.stringify({ nome: "Jake", sobrenome: "Peralta" }); // '{"nome":"Jake","sobrenome":"Peralta"}'
```
