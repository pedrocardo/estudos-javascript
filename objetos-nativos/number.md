# _Number_

_Number_ é uma função nativa que funciona como objeto empacotador para o primitivo _number_.

_Number_ pode ser utilizada como função construtora.

```javascript
typeof Number; // "function"

typeof new Number(); // "object"
```

## Conversão de tipos

A função _Number_ pode ser utilizada para converter valores de outros tipos para o primitivo _number_.

```javascript
Number("26"); // 26
Boolean(true); // 1
Boolean(false); // 0
```

## Atributos estáticos

O atributo _MAX_VALUE_ é o maior _number_ possível na linguagem.

```javascript
Number.MAX_VALUE; // 1.7976931348623157e+308
```

O atributo _MIN_VALUE_ é o menor _number_ possível na linguagem.

```javascript
Number.MIN_VALUE; // 5e-324
```

O atributo _NaN_ é um _number_ acrônimo para _not a number_.

```javascript
Number.NaN; // NaN
```

O atributo _MAX_SAFE_INTEGER_ é um _number_ com o maior inteiro seguro na linguagem.

```javascript
Number.MAX_SAFE_INTEGER; // 9007199254740991
```

O atributo _MIN_SAFE_INTEGER_ é um _number_ com o menor inteiro seguro na linguagem.

```javascript
Number.MIN_SAFE_INTEGER; // -9007199254740991
```

## Métodos estático

- [Método _isFinite_](#método-isFinite)
- [Método _isInteger_](#método-isInteger)
- [Método _isNaN_](#método-isNaN)
- [Método _isSafeInteger_](#método-isSafeInteger)
- [Método _parseFloat_](#método-parseFloat)
- [Método _parseInt_](#método-parseInt)

### Método _isFinite_

O método _isFinite_ checa se o argumento é finito e retorna um _boolean_.

```javascript
Number.isFinite(1); // true
```

### Método _isInteger_

O método _isInteger_ checa se o argumento é inteiro e retorna um _boolean_.

```javascript
Number.isInteger(1); // true
```

### Método _isNaN_

O método _isNaN_ checa se o argumento é _NaN_ e retorna um _boolean_.

```javascript
Number.isNaN(NaN); // true
```

### Método _isSafeInteger_

O método _isSafeInteger_ checa se o argumento é um inteiro seguro e retorna um _boolean_.

```javascript
Number.isSafeInteger(1); // true
```

### Método _parseFloat_

O método _parseFloat_ converte o argumento e retorna um _number_ real.

O método _parseFloat_ converte todos os números da _string_ argumento até encontrar um caractere não numérico.

```javascript
Number.parseFloat("1.15"); // 1.15

Number.parseFloat("503.7 frase na string"); // 503.7
```

### Método _parseInt_

O método _parseInt_ converte o argumento e retorna um _number_ inteiro.

O método _parseInt_ converte todos os números da _string_ argumento até encontrar um caractere não numérico.

Como segundo argumento, o método pode receber um _number_ representando a base para conversão.

Caso não seja passado um segundo argumento, o número será convertido para a base decimal.

```javascript
Number.parseInt("503 frase na string"); // 503

Number.parseInt("15"); // 15

Number.parseInt("11", 2); // 3
```

## Métodos de instância

Valores _number_ são encapsulados implicitamente, herdando métodos de _Number.prototype_.

- [Método _toFixed_](#método-toFixed)
- [Método _toLocaleString_](#método-toLocaleString)
- [Método _toPrecision_](#método-toPrecision)
- [Método _toString_](#método-toString)
- [Método _valueOf_](#método-valueOf)

### Método _toFixed_

O método _toFixed_ retorna uma _string_ com o número objeto com a quantidade de casas decimais passada como argumento.

Caso não receba nenhum argumento, o método removerá todas as casas decimais.

```javascript
(26.012).toFixed(2); // "26.01"

(26.012).toFixed(); // "26"
```

### Método _toLocaleString_

O método _toLocaleString_ retorna uma _string_ com o número objeto em uma formatação específica de um país.

Como primeiro argumento, o método pode receber uma _string_ com o código do país para a formatação do número.

Como segundo argumento, o método pode receber um objeto com opções de formatação. Esse objeto pode ter os seguintes atributos:

- _style_ para definir o estilo de formatação do número. Os valores possíveis desse atributo são _"decimal"_, _"percent"_ ou _"currency"_;
- _currency_ define a moeda para a formatação do número. O valor desse atributo deve ser uma _string_ com um código monetário válido;
- _currencyDisplay_ define a forma de exibir a moeda. Os valores possíveis desse atributo são _"symbol"_, _"code"_ ou _"name"_.

```javascript
(26.012032).toLocaleString("en-US"); // "26.012"

let opcoes = {
  style: "currency",
  currency: "USD",
  currencyDisplay: "name",
};

(26.012032).toLocaleString("en-US", opcoes); // "26.01 US dollars"
```

### Método _toPrecision_

O método _toPrecision_ retorna uma _string_ com o número objeto com a quantidade de valores significantes passada como argumento.

Caso não receba nenhum argumento, o método retornará o número como está.

```javascript
(26.012).toPrecision(5); // "26.012"

(26.012).toPrecision(); // "26.012"
```

### Método _toString_

O método _toString_ retorna um _string_ com o valor numérico do objeto.

```javascript
(26.012).toString(); // "26.012"
```

### Método _valueOf_

O método _valueOf_ retorna um _number_ com o valor numérico do objeto.

```javascript
(26.012).valueOf(); // 26.012
```
