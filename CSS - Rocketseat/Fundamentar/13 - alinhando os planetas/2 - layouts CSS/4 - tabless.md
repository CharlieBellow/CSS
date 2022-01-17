## Tabless

Uso das propriedades `float`, `clear` para que os elementos possam mudar de posição na tela.

```html

<div style="float: left">
  esquerda <!-- joga a caixa pra esquerda e o que vem depois sobre pra mesma linha quebrando o fluxo de caixa -->
</div>

 <div style="float: right">
  direita <!-- joga a caixa pra direita -->
</div>

<div style="clear: both">
  normal flow <!-- volta ao fluxo normal -->
</div>
```