# Global

O objeto global é inicializado junto com o _script_ e pode ter suas propriedades acessadas sem referenciá-lo.

```javascript
globalThis.isNaN === isNaN; // true
```

## Propriedades globais

A propriedade _NaN_ é do tipo _number_ e representa um resultado falho de operação matemática.

_NaN_ é um acrônimo para _not a number_ e só pode ser checado com a função global _isNaN_.

```javascript
NaN;

NaN === NaN; // false

isNaN(NaN); // true
```

A propriedade _Infinity_ é do tipo _number_ e representa números maiores que 1.79769313486231570e+308 ou menores que esse número negativo.

```javascript
Infinity;
-Infinity;
```

A propriedade _globalThis_ é do tipo _object_ e representa o objeto global.

```javascript
globalThis;
```

## Funções globais

Funções globais podem ser chamadas sem referenciar o objeto global.

- [Função _isFinite_](#função-isFinite)
- [Função _isNaN_](#função-isNaN)
- [Função _parseFloat_](#função-parseFloat)
- [Função _parseInt_](#função-parseInt)

### Função _isFinite_

A função _isFinite_ checa se o argumento é finito e retorna um _boolean_.

```javascript
isFinite(Infinity); // true
```

### Função _isNaN_

A função _isNaN_ checa se o argumento é _NaN_ e retorna um _boolean_.

```javascript
isNaN(1); // false
```

### Função _parseFloat_

A função _parseFloat_ converte o argumento e retorna um _number_ real.

A função _parseFloat_ converte todos os números da _string_ argumento até encontrar um caractere não numérico.

```javascript
parseFloat("1.15"); // 1.15

parseFloat("503.7 frase na string"); // 503.7
```

### Função _parseInt_

A função _parseInt_ converte o argumento e retorna um _number_ inteiro.

A função _parseInt_ converte todos os números da _string_ argumento até encontrar um caractere não numérico.

Como segundo argumento, a função pode receber um _number_ representando a base para conversão.

Caso não seja passado um segundo argumento, o número será convertido para a base decimal.

```javascript
parseInt("15"); // 15

parseInt("11", 2); // 3

parseInt("503 frase na string"); // 503
```
