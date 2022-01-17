## Flexbox

A caixa se torna flex, fazendo com que o elementos internos possam 'receber melhor:

- Alinhamento
- Ordenação
- Tamanhos flexíveis

```html
<div class="flexbox">
  <div class="item">A</div>
  <div class="item">B</div>
  <div class="item">C</div>
</div>
```

```css
.flexbox{
  display: flex; /* torna as caixas flexíveis. e agora dá pra mexer em várias coisas das caixas */
  justify-content: space-around; 
  flex-direction: column;
}

.item:nth-child(1) {
  order: 1; /* faz o primeiro item receber a ordem 1 e os outros são zero. então o A vai pra baixo.. */
}