# _String_

_String_ é uma função nativa que funciona como objeto empacotador para o primitivo _string_.

_String_ pode ser utilizada como função construtora.

```javascript
typeof String; // "function"

typeof new String(); // "object"
```

## Conversão de tipos

A função _String_ pode ser utilizada para converter valores de outros tipos para o primitivo _string_.

```javascript
String(10); // "10"
String(true); //"true"
```

## Atributos de instância

Valores _string_ são encapsulados implicitamente, fazendo com que tenham atributos de instância.

O atributo _length_ é do tipo _number_ e indica a quantidade de caracteres na _string_.

```javascript
"string".lenght; // 6
```

## Métodos de instância

Valores _string_ são encapsulados implicitamente, herdando métodos de _String.prototype_.

- [Método _charAt_](#método-charAt)
- [Método _charCodeAt_](#método-charCodeAt)
- [Método _concat_](#método-concat)
- [Método _endsWith_](#método-endsWith)
- [Método _includes_](#método-includes)
- [Método _indexOf_](#método-indexOf)
- [Método _lastIndexOf_](#método-lastIndexOf)
- [Método _match_](#método-match)
- [Método _padEnd_](#método-padEnd)
- [Método _padStart_](#método-padStart)
- [Método _repeat_](#método-repeat)
- [Método _replace_](#método-replace)
- [Método _search_](#método-search)
- [Método _slice_](#método-slice)
- [Método _split_](#método-split)
- [Método _startsWith_](#método-startsWith)
- [Método _substr_](#método-substr)
- [Método _substring_](#método-substring)
- [Método _toLowerCase_](#método-toLowerCase)
- [Método _toUpperCase_](#método-toUpperCase)
- [Método _trim_](#método-trim)
- [Método _trimEnd_](#método-trimEnd)
- [Método _trimStart_](#método-trimStart)
- [Método _valueOf_](#método-valueOf)

### Método _charAt_

O método _charAt_ retorna uma _string_ com o caractere que está no índice do argumento.

```javascript
"string".charAt(1); // "t"
```

### Método _charCodeAt_

O método _charCodeAt_ retorna um _number_ com o código UTF-16 do caractere que está no índice do argumento.

```javascript
"string".charCodeAt(0); // 115
```

### Método _concat_

O método _concat_ retorna uma _string_ com a concatenação da _string_ objeto e os argumentos.

```javascript
"string".concat(" outra string", " outra string")); // "string outra string outra string"
```

### Método _endsWith_

O método _endsWith_ checa se a _string_ objeto termina com o argumento e retorna um _boolean_.

Como segundo argumento, o método pode receber o tamanho da _string_ a ser considerado para a checagem.

```javascript
"string".endsWith("g"); // true

"string".endsWith("t", 2); // true
```

### Método _includes_

O método _includes_ checa se a _string_ objeto possui o argumento e retorna um _boolean_.

Como segundo argumento, é possível passar o índice inicial para checagem.

```javascript
"string".includes("trin"); // true

"string".includes("trin", 1); // true
```

### Método _indexOf_

O método _indexOf_ retorna um _number_ com o índice da primeira ocorrência do argumento na _string_ objeto.

Caso não encontre, será retornado -1.

Como segundo argumento, o método pode receber o índice inicial para checagem.

```javascript
"stringstring".indexOf("i"); // 3

"stringstring".indexOf("n", 4); // 4
```

### Método _lastIndexOf_

O método _lastIndexOf_ retorna um _number_ com o índice da última ocorrência do argumento na _string_ objeto.

Caso não encontre, será retornado -1.

Como segundo argumento, o método pode receber o índice do último caractere a ser considerado.

```javascript
"stringstring".lastIndexOf("i")) // 9

"stringstring".lastIndexOf("i", 8) // 3
```

### Método _match_

O método _match_ retorna um _array_ com as ocorrências do argumento na _string_ objeto.

```javascript
"stringstringstring".match(/str/g); // [ "str", "str", "str" ]
```

### Método _padEnd_

O método _padEnd_ retorna uma _string_ com o caractere _" "_ adicionado no final da _string_ objeto até que essa atinja o tamanho do argumento.

Como segundo argumento, o método pode receber os caracteres que serão adicionados a _string_ objeto.

```javascript
"string".padEnd(10); // "string    "

"string".padEnd(10, "."); // "string...."
```

### Método _padStart_

O método _padStart_ retorna uma _string_ com o caractere _" "_ adicionado no início da _string_ objeto até que essa atinja o tamanho do argumento.

Como segundo argumento, o método pode receber os caracteres que serão adicionados a _string_ objeto.

```javascript
"string".padStart(10); // "    string"

"string".padStart(10, "."); // "....string"
```

### Método _repeat_

O método _repeat_ retorna uma _string_ com a repetição da _string_ objeto na quantidade de vezes especificada como argumento.

```javascript
"string".repeat(3); // "stringstringstring"
```

### Método _replace_

O método _replace_ retorna uma _string_ com a troca das ocorrências do primeiro argumento pelo segundo na _string_ objeto.

```javascript
"string".replace(/i/g, "e"); // "streng"
```

### Método _search_

O método _search_ retorna um _number_ com o índice da ocorrência do argumento na _string_ objeto.

Caso não encontre, retorna -1.

```javascript
"string".search(/str/g); // 0
```

### Método _slice_

O método _slice_ retorna uma _string_ que está entre os índices passados como argumento na _string_ objeto.

Caso o segundo argumento não seja passado, será considerado o tamanho da _string_.

```javascript
"string".slice(1, 3); // "tr"

"string".slice(1); // "tring"
```

### Método _split_

O método _split_ divide a _string_ objeto nas ocorrências do argumento e retorna um _array_ de _substrings_.

Como segundo argumento, o método pode receber o limite de _substrings_ a serem incluídas no _array_.

```javascript
"s t r i n g".split(" "); // [ "s", "t", "r", "i", "n", "g" ]

"s t r i n g".split(" ", 2); // [ "s", "t" ]
```

### Método _startsWith_

O método _startsWith_ checa se a _string_ objeto começa com o argumento e retorna um _boolean_.

Como segundo argumento, o método pode receber o índice inicial para checagem.

```javascript
"string".startsWith("s"); // true

"string".startsWith("i", 3); // true
```

### Método _substr_

O método _substr_ retorna uma _string_ a partir do índice do primeiro argumento.

Como segundo argumento, o método pode receber quantos caracteres serão adicionados a _string_.

Caso o segundo argumento não seja passado, será considerado o tamanho da _string_ objeto.

```javascript
"string".substr(1, 3); // "tri"

"string".substr(1); // "tring"
```

### Método _substring_

O método _substring_ retorna uma _string_ que está entre os índices passados como argumento na _string_ objeto.

Caso o segundo argumento não seja passado, será considerado o tamanho da _string_.

```javascript
"string".substring(1, 3); // "tr"

"string".substring(1); // "tring"
```

### Método _toLowerCase_

O método _toLowerCase_ retorna a _string_ objeto com todos os caracteres em minúsculo.

```javascript
"STRING".toLowerCase(); // "string"
```

### Método _toUpperCase_

O método _toUpperCase_ retorna a _string_ objeto com todos os caracteres em maiúsculo.

```javascript
"string".toUpperCase(); // "STRING"
```

### Método _trim_

O método _trim_ retorna a _string_ objeto sem espaçamento no início e fim.

```javascript
"   string   ".trim(); // "string"
```

### Método _trimEnd_

O método _trimEnd_ retorna a _string_ objeto sem espaçamento no fim.

```javascript
"string   ".trimEnd(); // "string"
```

### Método _trimStart_

O método _trimStart_ retorna a _string_ objeto sem espaçamento no início.

```javascript
"   string".trimStart(); // "string"
```

### Método _valueOf_

O método _valueOf_ retorna uma _string_ com o valor _string_ do objeto.

```javascript
"string".valueOf(); // "string"
```
