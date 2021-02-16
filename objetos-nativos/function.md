# _Function_

_Function_ é uma função nativa destinada para funções.

_Function_ pode ser utilizada como função construtora.

```javascript
typeof Function; // "function"

typeof new Function(); // "object"
```

## Atributos de instância

O atributo _length_ é um _number_ com a quantidade de parâmetros da função.

```javascript
function funcao(parametro) {
  return "isso é uma função";
}

funcao.length; // 1
```

O atributo _name_ é uma _string_ contendo o nome da função.

```javascript
function funcao(parametro) {
  return "isso é uma função";
}

funcao.name; // "funcao"
```

## Métodos de instância

Instâncias de _Function_ herdam métodos de _Function.prototype_.

- [Método _apply_](#método-apply)
- [Método _bind_](#método-bind)
- [Método _call_](#método-call)
- [Método _toString_](#método-toString)

### Método apply

O método _apply_ executa a função com as ocorrências de _this_ modificadas para o objeto passado como argumento.

Como segundo argumento, o método _apply_ pode receber um vetor de argumentos para a função.

```javascript
function falarNacionalidadeEIdade(nacionalidade, idade) {
  return `${this.nome} é ${nacionalidade} e tem ${idade} anos`;
}

let pessoa = {
  nome: "Júlia",
};

falarNacionalidadeEIdade.apply(pessoa, ["brasileira", 27]); // Júlia é brasileira e tem 27 anos
```

### Método bind

O método _bind_ retorna a função com as ocorrências de _this_ modificadas para o objeto passado como argumento.

```javascript
function falarNacionalidade(nacionalidade) {
  return `${this.nome} é ${nacionalidade}`;
}

let pessoa = {
  nome: "Júlia",
};

let pessoaFalarNacionalidade = falarNacionalidade.bind(pessoa);

pessoaFalarNacionalidade("brasileira"); // "Júlia é brasileira"
```

Como segundo argumento, o método pode receber os argumentos que serão fixos na função modificada.

```javascript
function falarNacionalidade(nacionalidade) {
  return `${this.nome} é ${nacionalidade}`;
}

let pessoa = {
  nome: "Júlia",
};

let pessoaFalarNacionalidade = falarNacionalidade.bind(pessoa, "brasileira");

pessoaFalarNacionalidade(); // "Júlia é brasileira"
```

### Método call

O método _call_ executa a função com as ocorrências de _this_ modificadas para o objeto passado como argumento.

Como segundo argumento, o método _call_ pode receber os argumentos da função.

```javascript
function falarNacionalidadeEIdade(nacionalidade, idade) {
  return `${this.nome} é ${nacionalidade} e tem ${idade} anos`;
}

let pessoa = {
  nome: "Júlia",
};

falarNacionalidadeEIdade.call(pessoa, "brasileira", 27); // Júlia é brasileira e tem 27 anos
```

### Método toString

O método _toString_ retorna uma _string_ com a expressão da função.

```javascript
funcao.toString(); // "function funcao(parametro) { return "isso é uma função" }"
```
