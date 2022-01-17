## Adjacent sibling combinator e General sibling combinator

# Adjacent sibling combinator (+)

* Identificado pelo sinal + entre dois seletores
* Seleciona somente o elemento do lado direito que é irmão direto na hierarquia

HTML

<h1>
  Título
</h1>
<p>
  Esse é um parágrafo
</p>
<p>
  Mais um parágrafo
</p>

```CSS

h1 + p {
	color: red;
}
/* nesse caso, só o primeiro parágrafo fia vermelho.. pq ele é o p que vem logo após o h1 */

```
outro exemplo no dia a dia:

<button> um botão </button>
<button> outro botão </button>

```css
button + button {
  margin-left: 32px;
}
```

# General sibling combinator (~)

* Identificado pelo sinal ~ entre dois seletores
* Seleciona todos os elementos irmãos

HTML:

<h1>
  Título
</h1>
<p>
  Esse é um parágrafo
</p>
<button> botão</button>
<p>
  Mais um parágrafo
</p>

```CSS

h1 ~ p {
	color: red;
}