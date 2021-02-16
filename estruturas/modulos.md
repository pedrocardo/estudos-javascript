# Módulos

Módulos são arquivos _.js_ ou _.mjs_.

Módulos podem exportar e importar elementos entre si.

Exportações e importações são feitas com instruções.

## Instrução _export_

A instrução _export_ define elementos exportados pelo módulo.

```javascript
let variavel = "árvore";

let objeto = {};

function funcao() {}

export { variavel, objeto, funcao };
```

## Instrução _import_

A instrução _import_ define elementos importados de outro módulo.

Não é necessário importar todos os elementos do módulo exportador.

```javascript
import { variavel, funcao } from "./modulo.js";

variavel; // "árvore"

funcao; // Function
```

## Palavra reservada _as_

A palavra reservada _as_ pode nomear elementos exportados pelo módulo.

```javascript
let variavel = "árvore";

export { variavel as arvore };
```

A palavra reservada _as_ também pode nomear elementos importados de outro módulo.

```javascript
import { arvore as arvoreImportada } from "./modulo.js";

arvoreImportada; // "árvore"
```

## Palavra reservada _default_

Utilizando a palavra reservada _default_, é possível exportar um elemento como padrão do módulo.

```javascript
let variavel = "árvore";

export default variavel;
```

Para importar um elemento exportado como padrão de um módulo, não é necessário utilizar o nome correto e chaves.

```javascript
import arvore from "./modulo.js";

arvore; // "árvore";
```

## Importação de todos os elementos

Um módulo pode exportar vários elementos.

```javascript
let a = "A",
  b = "B",
  c = "C";

export { a, b, c };
```

Utilizando asterisco e a palavra reservada _as_, serão importados todos os elementos de um módulo exportador.

Os elementos importados serão propriedades de um objeto com o nome definido por _as_.

```javascript
import * as importacoes from "./modulo.js";

importacoes; // { a: 'A', b: 'B', c: 'C' }

importacoes.a; // "A"
```

## Importação de vários módulos

O mesmo módulo pode importar elementos de vários outros.

```javascript
import { elemento1 } from "./modulo1.js";

import { elemento2 } from "./modulo2.js";

import { elemento3 } from "./modulo3.js";
```
