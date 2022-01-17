## :first-child

É quando queremos selecionar o primeiro filho de um grupo de elementos.

HTML

<ul>
<h3>palavras bonitas</h3><!-- se tiver esse h3 aqui ele será o primeiro filho da tag ul.. então o código :first-child aplicado ao li não vai funcionar mais -->
  <li>Gratidão</li>
  <li>Esperança</li>
  <li>Fé</li>
</ul>

```CSS

ul li:first-child {
  font-weight: bold;
}
```