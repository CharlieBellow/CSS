## :nth-child()

É quando queremos selecionar o primeiro filho de um grupo de elementos.

HTML

<article>
	<h3>Palavras bonitas</h3>
  <p>Gratidão</p>
  <p>Esperança</p>
  <p>Fé</p>
</article>

``` CSS

article p:nth-child(2) {
  font-weight: bold;
  font-size: 18px;
}
/* nesse exemplo, ele tá considerando que o h3 é o primeiro filho. então se quero pegar o primeiro p, devo considerar que ele está na segunda posição.. então estou dizendo, pegue a tag p que é filha de article e que  está na segunda posição*/

```

