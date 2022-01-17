# Utilizando combinadores
HTML

<ul>
  <li>Alooo</li>
  <li class="red">Hey</li>
</ul>
```CSS

ul > li[class="red"] {
	color: red;
} 
<!-- nesse exemplo, ele pula a tag li e pega só o que está dentro de ul > li > e que tenha a classe red.. 
então assim dá pra pular elementos. é só procurar um caminho que seja exclusivo da tag que vc quer -->

```

Dica:
- Seletores muito específicos tendem a causar dificuldades no reuso das regras de estilização
- Muitas vezes, um simples uso de classes, torna o trabalho mais eficiente