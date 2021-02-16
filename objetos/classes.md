# Classes

Classes são moldes para criação de objetos e funcionam como funções construtoras.

## Declaração

Classes são declaradas com a instrução _class_.

```javascript
class Poligono {}
```

## Expressões

Classes podem ser manipuladas como expressões, ou seja, tratadas como valores.

```javascript
(class Animal {});
```

Expressões de classes podem ser anônimas.

```javascript
(class {});
```

## Funções

Classes são funções, ou seja, objetos instâncias de [_Function_](../objetos-nativos/objeto-function.md).

```javascript
class Classe {}

Classe instanceof Function; // true

Classe instanceof Object; // true
```

## Método _constructor_

Classes podem implementar o método _constructor_.

O método _constructor_ é responsável por criar e inicializar objetos a partir da classe.

```javascript
class Poligono {
  constructor() {}
}
```

Classes podem definir as propriedades dos objetos instanciados.

Isso deve ser feito dentro do método _constructor_ e utilizando a palavra reservada _this_.

```javascript
class Poligono {
  constructor(altura, largura) {
    this.altura = altura;
    this.largura = largura;
  }
}

let retangulo = new Poligono(2, 4);

retangulo.altura; // 2

retangulo.largura; // 4
```

## Propriedades do protótipo

Classes são funções e possuem a propriedade _prototype_.

Objetos herdarão as propriedades do protótipo da classe.

As propriedades do protótipo da classe devem ser escritas no corpo da classe.

```javascript
class Poligono {
  constructor(largura, altura) {
    this.largura = largura;
    this.altura = altura;
  }

  calcularArea() {
    return this.largura * this.altura;
  }

  sobre = "é uma figura fechada por lados";
}

let retangulo = new Poligono(4, 2);

retangulo.calcularArea(); // 8

retangulo.sobre; // "é uma figura fechada por lados"
```

## Propriedades estáticas

Classes podem ter atributos e métodos estáticos.

Propriedades estáticas devem ser escritas no corpo da classe e marcadas com a palavra reservada _static_.

```javascript
class Matematica {
  static pi = 3.14;
  static quadrado(numero) {
    return numero * numero;
  }
}

Matematica.pi; // 3.14

Matematica.quadrado(2); // 4
```

## Herança

Classes podem ser extendidas por outras. Para isso, deve ser utilizada a instrução _extends_.

```javascript
class Poligono {
  constructor() {}
}

class Retangulo extends Poligono {
  constructor() {}
}
```

Classes herdam as propriedades da classe extendida.

```javascript
class Poligono {
  constructor() {}

  calcularArea(largura, altura) {
    return largura * altura;
  }
}

class Retangulo extends Poligono {
  constructor() {
    super();
  }
}

let retangulo = new Retangulo();

retangulo.calcularArea(10, 2); // 20
```

## _Super_

_Super_ é a palavra reservada para se referir a classe extendida.

No método construtor da classe herdeira, é necessário chamar a função _super_ passandos os argumentos de _constructor_ da classe extendida.

```javascript
class Poligono {
  constructor(altura, largura) {
    this.altura = altura;
    this.largura = largura;
  }
}

class Retangulo extends Poligono {
  constructor(altura, largura) {
    super(altura, largura);
  }
}
```

As propriedades da classe estendida podem ser acessadas através da palavra reservada _super_.

```javascript
class Poligono {
  constructor(altura, largura) {
    this.altura = altura;
    this.largura = largura;
  }

  calcularArea() {
    return this.altura * this.largura;
  }
}

class Retangulo extends Poligono {
  constructor(altura, largura) {
    super(altura, largura);
  }

  calcularAreaFormatada() {
    return super.calcularArea() + " metros";
  }
}

let retangulo = new Retangulo(2, 6);

retangulo.calcularAreaFormatada(2, 6); // "12 metros"
```

## Sobrescrita

As propriedades de uma classe extendida podem ser sobrescritas.

```javascript
class Poligono {
  constructor(altura, largura) {
    this.altura = altura;
    this.largura = largura;
  }

  calcularArea() {
    return this.altura * this.largura;
  }
}

class Quadrado extends Poligono {
  constructor(largura) {
    super(largura, largura);
  }

  calcularArea() {
    return this.largura ** 2;
  }
}
```
