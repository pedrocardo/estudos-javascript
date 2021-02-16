# Objeto _console_

_Browsers_ e o _Node_ implementam o objeto não nativo _console_.

O objeto _console_ é destinado para exibir informações no _console_.

O objeto _console_ não possui função construtora e é inicializado junto com o programa.

```javascript
typeof console; // "object"
```

## Métodos

- [Método _count_](#método-count)
- [Método _countReset_](#método-countreset)
- [Método _error_](#método-error)
- [Método _log_](#método-log)
- [Método _table_](#método-table)
- [Método _time_](#método-time)
- [Método _timeEnd_](#método-timeend)
- [Método _timeLog_](#método-timelog)
- [Método _warn_](#método-warn)

### Método _count_

O método _count_ cria e/ou adiciona uma unidade a um contador. Ao ser chamado, o método também exibe a contagem no _console_.

Como argumento, o método deve receber uma _string_ com o nome do contador a ser criado ou incrementado.

```javascript
console.count("counter");
```

### Método _countReset_

O método _countReset_ reseta a contagem de um contador.

Como argumento, o método deve receber uma _string_ com o nome do contador a ser resetado.

```javascript
console.countReset("counter");
```

### Método _error_

O método _error_ exibe os argumentos em formato de erro no _console_.

```javascript
console.error("string", 41, true, { cor: "amarelo" }, [1, 2, 3]);
```

### Método _log_

O método _log_ exibe os argumentos no _console_.

```javascript
console.log("string", 41, true, { cor: "amarelo" }, [1, 2, 3]);
```

### Método _table_

O método _table_ exibe objetos passados como argumento em formato de tabela no _console_.

```javascript
console.table([1, 2, 3]);

console.table({ nome: "morcego", classe: "mammalia" });
```

### Método _time_

O método _time_ inicia um _timer_.

Como argumento, o método pode receber uma _string_ que define o nome do _timer_.

```javascript
console.time("clock");
```

### Método _timeEnd_

O método _timeEnd_ encerra um _timer_ e exibe seu tempo no _console_.

Como argumento, o método pode receber uma _string_ com o nome de um _timer_.

```javascript
console.timeEnd("clock");
```

### Método _timeLog_

O método _timeLog_ exibe o tempo de um _timer_ no console.

Como argumento, o método pode receber uma _string_ com o nome de um _timer_.

```javascript
console.timeLog("clock");
```

### Método _warn_

O método _warn_ exibe os argumentos em formato de aviso no _console_.

```javascript
console.warn("string", 41, true, { cor: "amarelo" }, [1, 2, 3]);
```
