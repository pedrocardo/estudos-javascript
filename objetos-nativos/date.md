# _Date_

_Date_ é uma função nativa destinada para datas.

_Date_ pode ser utilizada como função construtora.

```javascript
typeof Date; // "function"

typeof new Date(); // "object"
```

Um objeto _Date_ armazena uma data de acordo com a quantidade de milissegundos entre ela e o dia 01/01/1970.

```javascript
let data = new Date("2015-03-25");

data.getTime();

```

## Função construtora

A função construtora _Date_ pode receber uma _string_ com uma data formatada.

```javascript
let data = new Date("2015-03-25");

data; // Tue Mar 24 2015 21:00:00 GMT-0300
```

A função construtora _Date_ pode receber um _number_ com uma quantidade de milissegundos desde 01/01/1970.

```javascript
let data = new Date(951582430010);

data; // Sat Feb 26 2000 14:27:10 GMT-0200
```

A função construtora _Date_ pode receber _numbers_ com ano, mês, dia, horas, minutos, segundos e milissegundos.

```javascript
let data = new Date(2020, 06, 12, 20, 07, 26, 4);

data; // Sun Jul 12 2020 20:07:26 GMT-0300
```

A função construtora _Date_ sem argumentos irá retornar um objeto com a data de sua criação.

```javascript
let data = new Date();

data; // Sun Oct 11 2020 23:51:01 GMT-0300
```

## Strings formatadas

A função construtora _Date_ pode receber vários formatos de _string_ com datas.

```javascript
new Date("2015-03-25");
new Date("2015-03");
new Date("2015");
new Date("2015-03-25T12:00:00-06:30");
new Date("03/25/2015");
new Date("Jan 25 2015");
new Date("25 Jan 2015");
new Date("25 January 2015");
```

## Métodos estáticos

O método _parse_ retorna um _number_ com a quantidade de milissegundos do argumento.

```javascript
Date.parse("2015-03-25"); // 1427241600000
```

O método _now_ retorna um _number_ com a quantidade de milissegundos da data do sistema.

```javascript
Date.now(); // 1602471598938
```

## Métodos de instância

Instâncias de _Date_ herdam métodos de _Date.prototype_.

Os métodos de _Date.prototype_ podem ser classificados nas seguintes categorias:

- Métodos conversores, que retornam uma forma representativa da data
  - [Método _toDateString_](#método-toDateString)
  - [Método _toISOString_](#método-toISOString)
  - [Método _toJSON_](#método-toJSON)
  - [Método _toLocaleString_](#método-toLocaleString)
  - [Método _toString_](#método-toString)
  - [Método _toTimeString_](#método-toTimeString)
  - [Método _valueOf_](#método-valueOf)
- Métodos _getters_, que retornam um _number_ com um determinado valor da data
  - [Método _getDate_](#método-getDate)
  - [Método _getDay_](#método-getDay)
  - [Método _getFullYear_](#método-getFullYear)
  - [Método _getHours_](#método-getHours)
  - [Método _getMilliseconds_](#método-getMilliseconds)
  - [Método _getMinutes_](#método-getMinutes)
  - [Método _getMonth_](#método-getMonth)
  - [Método _getSeconds_](#método-getSeconds)
  - [Método _getTime_](#método-getTime)
- Métodos _setters_, que definem valores da data e retornam um _number_ com a quantidade de milissegundos da nova data
  - [Método _setDate_](#método-setDate)
  - [Método _setFullYear_](#método-setFullYear)
  - [Método _setHours_](#método-setHours)
  - [Método _setMilliseconds_](#método-setMilliseconds)
  - [Método _setMinutes_](#método-setMinutes)
  - [Método _setMonth_](#método-setMonth)
  - [Método _setSeconds_](#método-setSeconds)
  - [Método _setTime_](#método-setTime)

### Método _getDate_

O método _getDate_ retorna o dia do mês.

```javascript
data.getDate(); // 26
```

### Método _getDay_

O método _getDay_ retorna o dia da semana como um número entre zero a seis.

```javascript
data.getDay(); // 3
```

### Método _getFullYear_

O método _getFullYear_ retorna o ano.

```javascript
data.getFullYear(); // 2000
```

### Método _getHours_

O método _getHours_ retorna a hora como um número entre zero e vinte e três.

```javascript
data.getHours(); // 13
```

### Método _getMilliseconds_

O método _getMilliseconds_ retorna o milissegundo como um número entre zero e novecentos e noventa e nove.

```javascript
data.getMilliseconds(); // 0
```

### Método _getMinutes_

O método _getMinutes_ retorna o minuto como um número zero e cinquenta e nove.

```javascript
data.getMinutes(); // 27
```

### Método _getMonth_

O método _getMonth_ retorna mês como um número entre zero e onze.

```javascript
data.getMonth(); // 0
```

### Método _getSeconds_

O método _getSeconds_ retorna o segundo como um número entre zero e cinquenta e nove.

```javascript
data.getSeconds(); // 0
```

### Método _getTime_

O método _getTime_ retorna a quantidade de milissegundos entre a data e o dia 01/01/1970.

```javascript
data.getTime(); // 948900420000
```

### Método _setDate_

O método _setDate_ define o dia da data.

```javascript
data.setDate(12);
```

### Método _setFullYear_

O método _setFullYear_ define o ano da data.

```javascript
data.setFullYear(2010);
```

### Método _setHours_

O método _setHours_ define a hora da data, podendo receber como argumento um _number_ entre zero e vinte e três.

```javascript
data.setHours(4);
```

### Método _setMilliseconds_

O método _setMilliseconds_ define o milissegundo da data.

```javascript
data.setMilliseconds(16);
```

### Método _setMinutes_

O método _setMinutes_ define o minuto da data.

```javascript
data.setMinutes(22);
```

### Método _setMonth_

O método _setMonth_ define o mês da data, podendo receber um número entre zero e onze.

```javascript
data.setMonth(5);
```

### Método _setSeconds_

O método _setSeconds_ define o segundo da data.

```javascript
data.setSeconds(48);
```

### Método _setTime_

O método _setTime_ define a quantidade de milissegundos entre a data e o dia 01/01/1970.

```javascript
data.setTime(132189);
```

### Método _toDateString_

O método _toDateString_ retorna uma _string_ com a data.

```javascript
data.toDateString(); // "Mon Oct 12 2020"
```

### Método _toISOString_

O método _toISOString_ retorna uma _string_ com a data no formato ISO 8601.

```javascript
data.toISOString(); // "2020-10-12T06:03:32.671Z"
```

### Método _toJSON_

O método _toJSON_ retorna uma _string_ com a data no formato JSON.

```javascript
data.toJSON(); // "2020-10-12T06:03:32.671Z"
```

### Método _toLocaleString_

O método _toLocaleString_ retorna uma _string_ com a data no formato do país passado como argumento.

```javascript
data.toLocaleDateString("it-IT"); // "2020-10-12"
```

### Método _toString_

O método _toString_ retorna uma _string_ com a data e horário.

```javascript
data.toString(); // "Mon Oct 12 2020 03:03:32 GMT-0300 (GMT-03:00)"
```

### Método _toTimeString_

O método _toTimeString_ retorna uma _string_ com o horário.

```javascript
data.toTimeString(); // "03:03:32 GMT-0300 (GMT-03:00)"
```

### Método _valueOf_

O método _valueOf_ retorna um _number_ com os milissegundos da data.

```javascript
data.valueOf(); // 1602482612671
```
