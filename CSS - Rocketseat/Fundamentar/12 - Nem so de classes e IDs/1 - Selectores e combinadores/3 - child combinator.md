## Child combinator

* Identificado pelo sinal > entre dois seletores
* seleciona somente o elemento que é filho direto do pai
* Elementos depois do filho direto serão desconsiderados

HTML:

<body>
  <ul>
    <li>Item 1</li>
    <ul>
      <li>Item 2</li>
    </ul>
  </ul>
</body>

```css
body > ul > li {
	color: blue;
}
/* nesse exempo, só o primeiro item vai ficar azul */
/* pergunta: mas e se eu quiser pular o primeiro e pegar só o segundo item? */
```