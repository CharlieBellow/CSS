# :nth-of-type()

Pega o elemento por tipo e posição

HTML

<article>
  <h3>Palavras bonitas</h3>
  <p>Gratidão</p>
  <p>Esperança</p>
  <p>Fé</p>
</article>

```CSS

article p:nth-of-type(2) {
  font-weight: bold;
}
```
<!-- com esse também dá pra pular a ordem dat tags e escolher a que quiser -->