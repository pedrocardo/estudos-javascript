# _Array_

_Array_ é uma função nativa destinada para vetores.

_Array_ pode ser utilizada como função construtora.

```javascript
typeof Array; // "function"

typeof new Array(); // "object"
```

## Atributo de instância

O atributo _length_ é do tipo _number_ e indica a quantidade de elementos do vetor.

```javascript
let vetor = ["substantivo", "verbo", "adjetivo"];

vetor.length; // 3
```

## Métodos de instância

Instâncias de _Array_ herdam métodos de _Array.prototype_.

Os métodos de _Array.prototype_ podem ser classificados nas seguintes categorias:

- Métodos modificadores, que alteram o vetor objeto
  - [Método _copyWithin_](#método-copyWithin)
  - [Método _fill_](#método-fill)
  - [Método _pop_](#método-pop)
  - [Método _push_](#método-push)
  - [Método _reverse_](#método-reverse)
  - [Método _shift_](#método-shift)
  - [Método _sort_](#método-sort)
  - [Método _splice_](#método-splice)
  - [Método _unshift_](#método-unshift)
- Métodos de acesso, que não alteram o vetor objeto e retornam uma nova forma de representação
  - [Método _concat_](#método-concat)
  - [Método _includes_](#método-includes)
  - [Método _indexOf_](#método-indexOf)
  - [Método _join_](#método-join)
  - [Método _lastIndexOf_](#método-lastIndexOf)
  - [Método _slice_](#método-slice)
  - [Método _toString_](#método-toString)
- Métodos de iteração, que percorrem os elementos do vetor, executando funções _callback_ em cada iteração
  - [Método _every_](#método-every)
  - [Método _filter_](#método-filter)
  - [Método _find_](#método-find)
  - [Método _findIndex_](#método-findIndex)
  - [Método _forEach_](#método-forEach)
  - [Método _map_](#método-map)
  - [Método _reduce_](#método-reduce)
  - [Método _some_](#método-some)

### Método _concat_

O método _concat_ retorna um vetor com a concatenação do vetor objeto e os argumentos.

```javascript
let vetor1 = ["verde", "azul"];
let vetor2 = ["vermelho", "amarelo"];
let vetor3 = ["preto", "branco"];

vetor1.concat(vetor2, vetor3); // [ "verde", "azul", "vermelho", "amarelo", "preto", "branco" ]
```

### Método _copyWithin_

O método _copyWithin_ copia um elemento do vetor e o cola em outro índice.

Como primeiro argumento, o método deve receber o índice em que será colado o elemento.

Como segundo argumento, o método deve receber o índice do elemento a ser copiado.

```javascript
let vetor = ["melancia", "maçã", "banana"];

vetor.copyWithin(0, 2);

vetor; // [ "banana", "maçã", "banana" ]
```

### Método _every_

O método _every_ checa se todos os elementos do vetor satisfazem a condição de uma função _callback_.

Como argumento, o método deve receber uma função _callback_. Para organização, essa função será chamada de _check_.

A função _check_ deve ter um parâmetro que representa o elemento do vetor.

A função _check_ pode ter um parâmetro que representa o índice do elemento no vetor.

A função _check_ pode ter um parâmetro que representa o próprio vetor.

A função _check_ deve retornar um _boolean_.

O método _every_ só retornará _true_ caso a função _check_ retorne _true_ para todos os elementos do vetor.

```javascript
let vetor = [103, 157, 123, 187];

let check = function (elemento) {
  if (elemento > 100 && elemento < 200) {
    return true;
  } else {
    return false;
  }
};

vetor.every(check); // true
```

### Método _fill_

O método _fill_ substitui os elementos do vetor.

Como primeiro argumento, o método deve receber o valor que substituirá os elementos.

Como segundo argumento, o método pode receber o índice inicial para as substituições.

Como terceiro argumento, o método pode receber o índice final para as substituições.

```javascript
let vetor = ["melancia", "maçã", "banana", "maracujá", "laranja"];

vetor.fill("substituição", 1, 3);

vetor; // ["melancia", "substituição", "substituição", "maracujá", "laranja"];
```

### Método _filter_

O método _filter_ retorna um vetor com os elementos que satisfazem a condição de uma _callback_.

Como argumento, o método deve receber uma função _callback_. Para organização, essa função será chamada de _check_.

A função _check_ deve ter um parâmetro que representa o elemento do vetor.

A função _check_ pode ter um parâmetro que representa o índice do elemento no vetor.

A função _check_ pode ter um parâmetro que representa o próprio vetor.

A função _check_ deve retornar um _boolean_.

O método _filter_ retornará um vetor com todos os elementos que fazem com que _check_ retorne _true_.

```javascript
let vetor = [103, 50, 123, 187];

let check = function (elemento) {
  if (elemento < 120) {
    return true;
  } else {
    return false;
  }
};

let elementos = vetor.find(check); // [ 103, 50 ]
```

### Método _find_

O método _find_ procura pelo elemento que satisfaça a condição de uma função _callback_.

Como argumento, o método deve receber uma função _callback_. Para organização, essa função será chamada de _check_.

A função _check_ deve ter um parâmetro que representa o elemento do vetor.

A função _check_ pode ter um parâmetro que representa o índice do elemento no vetor.

A função _check_ pode ter um parâmetro que representa o próprio vetor.

O método _find_ retornará o primeiro elemento que faz com que _check_ retorne _true_.

O método _find_ retornará _undefined_ caso nenhum elemento retorne _true_ em _check_.

```javascript
let vetor = [103, 50, 123, 187];

let check = function (elemento) {
  if (elemento < 100) {
    return true;
  } else {
    return false;
  }
};

let elemento = vetor.find(check); // 50
```

### Método _findIndex_

O método _findIndex_ procura pelo índice do primeiro elemento que satisfaça a condição de uma função _callback_.

Como argumento, o método deve receber uma função _callback_. Para organização, essa função será chamada de _check_.

A função _check_ deve ter um parâmetro que representa o elemento do vetor.

A função _check_ pode ter um parâmetro que representa o índice do elemento no vetor.

A função _check_ pode ter um parâmetro que representa o próprio vetor.

O método _findIndex_ retornará o índice do primeiro elemento que faz com que _check_ retorne _true_.

O método _findIndex_ retornará -1 caso nenhum elemento retorne _true_ em _check_.

```javascript
let vetor = [103, 50, 123, 187];

let check = function (elemento) {
  if (elemento < 100) {
    return true;
  } else {
    return false;
  }
};

vetor.findIndex(); // 1
```

### Método _forEach_

O método _forEach_ executa uma função _callback_ para cada elemento do vetor e retorna _undefined_.

Como argumento, o método pode receber uma função _callback_. Para organização, essa função será chamada de _executor_.

A função _executor_ deve ter um parâmetro que representa o elemento do vetor.

A função _executor_ pode ter um parâmetro que representa o índice do elemento no vetor.

A função _executor_ pode ter um parâmetro que representa o próprio vetor.

```javascript
let vetor = ["zero", "um", "dois"];

let fraseComElementos = "";

let executor = function (elemento) {
  fraseComElementos = fraseComElementos + elemento + " ";
};

vetor.forEach(executor);

fraseComElementos; // "zero um dois "
```

### Método _includes_

O método _includes_ checa se o vetor objeto possui o argumento e retorna um _boolean_.

Como segundo argumento, o método pode receber o índice inicial para checagem.

```javascript
let vetor = ["verde", "azul", "vermelho", "amarelo"];

vetor.includes("azul"); // true

vetor.includes("azul", 1); // true
```

### Método _indexOf_

O método _indexOf_ retorna um _number_ com o índice da primeira ocorrência do argumento no vetor objeto.

Caso o método não encontre o argumento, será retornado -1.

Como segundo argumento, o método pode receber o índice inicial para checagem.

```javascript
let vetor = ["laranja", "laranja", "laranja", "laranja"];

vetor.indexOf("laranja"); // 0

vetor.indexOf("laranja", 1); // 1

vetor.indexOf("azul"); // -1
```

### Método _join_

O método _join_ retorna uma _string_ com todos os elementos do vetor concatenados.

Como argumento, o método pode receber a _string_ que separará os elementos.

```javascript
let vetor = ["verde", "azul", "vermelho", "amarelo"];

vetor.join(); // verde,azul,vermelho,amarelo

vetor.join("-"); // verde-azul-vermelho-amarelo
```

### Método _lastIndexOf_

O método _lastIndexOf_ retorna um _number_ com o índice da última ocorrência do argumento no vetor objeto.

Caso o método não encontre o argumento, será retornado -1.

Como segundo argumento, o método pode receber o último índice a ser considerado.

```javascript
let vetor = ["amarelo", "amarelo", "amarelo", "amarelo"];

vetor.lastIndexOf("amarelo"); // 3

vetor.lastIndexOf("amarelo", 1); // 1

vetor.lastIndexOf("verde"); // -1
```

### Método _map_

O método _map_ retorna um vetor com os valores retornados por uma função _callback_.

Como argumento, o método deve receber uma função _callback_. Para organização, essa função será chamada de _populate_.

A função _populate_ deve ter um parâmetro que representa o elemento do vetor.

A função _populate_ pode ter um parâmetro que representa o índice do elemento no vetor.

A função _populate_ pode ter um parâmetro que representa o próprio vetor.

```javascript
let vetor = [100, 110, 120, 130];

let populate = function (elemento) {
  return elemento + 100;
};

vetor.map(populate, 100); // [ 200, 210, 220, 230 ]
```

### Método _pop_

O método _pop_ remove e retorna o último elemento do vetor.

```javascript
let vetor = ["melancia", "maçã", "banana"];

let elementoRemovido = vetor.pop();

vetor; // [ "melancia", "maçã" ]

elementoRemovido; // "banana"
```

### Método _push_

O método _push_ adiciona um ou mais elementos no final do vetor.

O método _push_ retorna um _number_ com o novo tamanho do vetor.

```javascript
let vetor = ["melancia", "maçã", "banana"];

let novoTamanho = vetor.push("maracujá", "laranja");

vetor; // [ "melancia", "maçã", "banana", "maracujá", "laranja" ]

novoTamanho; // 5
```

### Método _reduce_

O método _reduce_ retorna um valor acumulado por uma função _callback_.

Como argumento, o método deve receber uma função _callback_. Para organização, essa função será chamada de _acumulate_.

A função _acumulate_ deve ter um parâmetro que representa o valor acumulado.

A função _acumulate_ deve ter um parâmetro que representa o elemento do vetor.

A função _acumulate_ pode ter um parâmetro que representa o índice do elemento no vetor.

A função _acumulate_ pode ter um parâmetro que representa o próprio vetor.

A função _acumulate_ deve retornar um novo valor acumulado.

Como segundo argumento, o método pode receber um valor inicial para o acúmulo.

```javascript
let vetor = [10, 20, 30, 40];

let acumulate = function (acumulo, elemento) {
  return acumulo + elemento;
};

vetor.reduce(acumulate, 100); // 200
```

### Método _reverse_

O método _reverse_ inverte os elementos do vetor.

```javascript
let vetor = ["um", "dois", "três"];

vetor.reverse();

vetor; // [ "três", "dois", "um" ]
```

### Método _shift_

O método _shift_ remove e retorna o primeiro elemento do vetor.

```javascript
let vetor = ["melancia", "maçã", "banana"];

let elementoRemovido = vetor.shift();

vetor; // [ "maçã", "banana" ]

elementoRemovido; // "melancia"
```

### Método _slice_

O método _slice_ retorna um vetor que está entre os índices passados como argumento no vetor objeto.

Caso o segundo argumento não seja passado, será considerado o tamanho do vetor.

```javascript
let vetor = ["verde", "azul", "vermelho", "amarelo"];

vetor.slice(1, 3); // [ "azul", "vermelho" ]

vetor.slice(1); // [ "azul", "vermelho", "amarelo" ]
```

### Método _some_

O método _some_ checa se pelo menos um elemento do vetor satisfaz a condição de uma função _callback_.

Como argumento, o método deve receber uma função _callback_. Para organização, essa função será chamada de _check_.

A função _check_ deve ter um parâmetro que representa o elemento do vetor.

A função _check_ pode ter um parâmetro que representa o índice do elemento no vetor.

A função _check_ pode ter um parâmetro que representa o próprio vetor.

A função _check_ deve retornar um _boolean_.

O método _every_ só retornará _true_ caso a função _check_ retorne _true_ para pelo menos um elemento do vetor.

```javascript
let vetor = [103, 50, 123, 187];

let check = function (elemento) {
  if (elemento < 100) {
    return true;
  } else {
    return false;
  }
};

vetor.some(check); // true
```

### Método _sort_

O método _sort_ ordena os elementos do vetor.

Sem nenhum argumento, o método tratará os elementos do vetor como _strings_ e os ordenará de acordo com os códigos UTF-16.

Como argumento, o método pode receber uma função _callback_. Para organização, essa função será chamada de _compare_.

A função _compare_ deve possuir dois parâmetros. O primeiro representará um elemento, e o segundo o elemento seguinte no vetor.

Caso a função _compare_ retorne um número menor que zero, o primeiro argumento será colocado antes do segundo no vetor.

Caso a função _compare_ retorne um número maior que zero, o primeiro argumento será colocado depois do segundo no vetor.

Caso a função _compare_ retorne zero, os dois argumentos serão considerados iguais.

```javascript
let vetor = [4, 2, 10, 5, 8, 3];

let compare = function (elemento, elementoSeguinte) {
  if (elemento < elementoSeguinte) {
    return -1;
  }

  if (elemento > elementoSeguinte) {
    return 1;
  }

  return 0;
};

vetor.sort(compare); // [ 2, 3, 4, 5, 8, 10 ]
```

### Método _splice_

O método _splice_ adiciona, substitui ou remove elementos em qualquer posição do vetor.

Como primeiro argumento, o método deve receber o índice inicial para as operações.

Como segundo argumento, o método deve receber a quantidade de elementos que serão substituídos ou removidos a partir do índice inicial.

Como argumentos seguintes, o método pode receber os valores a serem adicionados ou substituídos no vetor.

O método _splice_ retorna um vetor com os elementos removidos.

```javascript
let vetor = ["melancia", "maçã", "banana", "kiwi"];

let itensRemovidos = vetor.splice(1, 2, "maracujá", "laranja");

vetor; // [ "melancia", "maracujá", "laranja", "kiwi" ]

itensRemovidos; // [ "maçã", "banana" ]
```

### Método _toString_

O método _toString_ retorna uma _string_ com os elementos do vetor separados por vírgula.

```javascript
let vetor = ["verde", "azul", "vermelho", "amarelo"];

vetor.toString(); // "verde,azul,vermelho,amarelo"
```

### Método _unshift_

O método _unshift_ adiciona um ou mais elementos no início vetor.

O método _unshift_ retorna um _number_ com o novo tamanho do vetor.

```javascript
let vetor = ["melancia", "maçã", "banana"];

let novoTamanho = vetor.unshift("maracujá", "laranja");

vetor; // [ "maracujá", "laranja", "melancia", "maçã", "banana" ]

novoTamanho; // 5
```
