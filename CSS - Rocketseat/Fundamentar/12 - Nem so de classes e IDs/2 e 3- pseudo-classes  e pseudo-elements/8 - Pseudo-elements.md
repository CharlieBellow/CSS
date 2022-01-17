## Pseudo-elements (::)

Com pseudo-elements nós podemos adicionar elementos HTML pelo próprio CSS

`::pseudo-element-name`

## Exemplos

  * ::before
  * ::after 
  * ::first-line 

# ::before 

adiciona um pseudo-elemento antes do elemento selecionado.

HTML

<ul>
  <li>Gratidão</li>
  <li>Esperança</li>
  <li>Fé</li>
  <li>Liberdade</li>
</ul>

```CSS

li::before {
  content: "> "/* precisa do content pra funcionar */
}
```

# ::after 

adiciona um pseudo-elemento depois do elemento selecionado.

```css
li {
  position: relative;
}

li::after{
  content: ";"
  width: 10px;
  height:1px;
  background-color: blue;
  position:absolute;button: 0px;
}
```

Tanto para o ::before quanto para o ::after é preciso adicionar o content, mesmo que ele seja vazio content = "";

# ::first-line 

pega a primeira linha de um texto.

```css

p:nth-of-type(2)::first-line {
	font-weight: bold;
}
/* juntando pseudo-elementos com pseudo-classes */
```

# Referência
https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements