# Escopos

Escopos determinam a visibilidade de elementos no programa, ou seja, em quais locais eles poderão ser acessados.

## Escopo léxico

_JavaScript_ é uma linguagem com escopo léxico. Ou seja, a visibilidade de elementos é determinada pela escrita do código.

Com escopo léxico, elementos em uma estrutura externa são visíveis em estruturas aninhadas.

```javascript
{
  const constante = "constante visível em estrutura aninhada";
  {
    constante; // "constante visível em estrutura aninhada"
  }
}
```

## Escopos de bloco

Escopos de bloco são criados por chaves e normalmente usados em instruções.

```javascript
{
  let variavel = "variável local";
}
```

## Escopos de funções

Funções criam seu próprio escopo.

Qualquer elemento declarado dentro de uma função só poderá ser acessado dentro dessa.

```javascript
function funcao() {
  var variavel = "variável local";
}
```

## Visibilidade

A visibilidade de um elemento é determinada pelo local e instrução utilizada em sua declaração.

Caso um elemento seja referenciado fora do seu escopo, será lançado um _ReferenceError_.

Variáveis declaradas com _let_ e constantes declaradas com _const_ respeitam escopos de bloco e de funções.

```javascript
{
  let variavelLocal = "essa variável só é visível nesse escopo";

  const constanteLocal = "essa constante só é visível nesse escopo";
}
```

Funções e variáveis declaradas com _var_ respeitam apenas escopos de funções.

```javascript
function funcao() {
  async function funcaoAssicronaInterna() {
    return "essa função assíncrona só é visível nesse escopo";
  }

  function funcaoInterna() {
    return "essa função só é visível nesse escopo";
  }

  var variavelLocal = "essa variável só é visível nesse escopo";
}
```

```

```
