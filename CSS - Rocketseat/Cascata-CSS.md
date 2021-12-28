# Cascata

A escolha do browser de qual regra aplicar, caso haja muitas regras para o mesmo elemento.

Seu estilo é lido de cima para baixo, ou seja, caso haja algum selector com informações conflitantes, o mais embaixo é o que será atribuído.
São levados em consideração 3 fatores:

## A origem do estilo;

Inline (estilo escrito na linha) > tag style > tag link (do mais forte para o mais fraco)

```css
Ex1:
No HTML:
<h1>título<h1
<p> parágrafo</p>

No CSS (aqui temos a tag link pq tá sendo importada de um arquivo CSS e não está dentro do HTML):

h1 {
	color: red;
}

h1 {
	color: blue;
}
```

Nesse caso vai ser considerada a cor azul, pq o efeito cascata faz o código ser lido de cima para baixo.

Ex2:
No HTML:
```css
<h1 style=”color: green”>título<h1
<p> parágrafo</p>

No CSS:
h1 {
color: red;
}

h1{
color: blue;
}
```
Nesse caso vai ser considerada a cor verde, pq a tag style é mais forte que o arquivo css importado com a tag link

Ex3:
No HTML:
```css
<style>
	h1{
color: grey
}
</style>
<h1 style=”color: green”>título<h1
<p> parágrafo</p>

No CSS:
h1 {
color: red;
}

h1{
color: blue;
}
```
Nesse caso ainda vai ser considerada a cor verde, pq a tag style escrita na linha do texto é mais forte que a tag style que está acima e é mais forte também do que o arquivo importado com CSS.

Ex4:
No HTML:
```css
<style>
	h1{
color: grey
}
</style>
<h1>título<h1
<p> parágrafo</p>

No CSS:
h1 {
color: red;
}

h1{
color: blue;
}
```
Nesse caso vai ser considerada a cor cinza, pq a tag style escrita no <head> do Html é mais forte que do que o arquivo importado com CSS.

Ex5:
No HTML:
```css
<style>
	h1{
color: grey
}
</style>
<h1>título<h1>
<p> parágrafo</p>
<style>
	h1{
color: red
}
</style>

No CSS:
h1 {
color: red;
}

h1{
color: blue;
}
```

Nesse caso vai ser considerada a cor vermelha, por causa do efeito cascata. a tag style é mais forte do que o arquivo importado com CSS. Mas por causa do efeito cascata, vai ser considerado o código que está embaixo.. como no arquivo html tem duas tags style (uma pedindo o cinza e outra pedindo vermelho) é considerada a que está mais embaixo que é o vermelho. e isso serve para todas as regras e opções de estilo (inline (código escrito na linha, tag style e tag link)

## A especificidade

É um cálculo matemático, onde cada tipo de seletor e origem do estilo possuem valores a serem considerados.

0. universal selector, combinators e negation pseudo-class (:not())
1. element type selector e pseudo-elements. (::before, ::after)
10. classes e attribute selectors ([type=radio”])
100. ID selector
1000. Inline

Os mais fracos são universal selector, combinators e negation pseudo-class, com o valor de 0. Em seguida, com valor de 1, são os element type selector e pseudo-elements.

Também temos os classes e attribute selectors, com valor de 10, ou seja, são mais fortes que os anteriores.

O segundo mais forte, ID selector, com um valor de 100, vence todos os selectors anteriores.

Por fim, temos o inline, com o valor 1000, quaisquer desses selectors anteriormente citado
exemplos:
ex.1:
No HTML:

<h1>título<h1>
<p> parágrafo</p>

No CSS:

-   {
    color: green;
    }
    h1 {
    color: red;
    }

h1{
color: blue;
}

Nesse caso a cor verde vai ser aplicada ao texto dentro de <p></p> e o texto da <h1> vai se manter na cor azul respeitando a ordem da cascata. o texto de <h1> não muda pq foi atribuído a essa tag

ex.2:
No HTML:

<h1>título<h1>
<p> parágrafo</p>

No CSS:

h1 {
color: red;
}

h1{
color: blue;
}

-   {
    color: green;
    }

Agora o seletor universal tá embaixo e mesmo assim nesse caso a cor verde vai ser aplicada ao texto dentro de <p></p> e o texto da <h1> vai se manter na cor azul respeitando a ordem da cascata. o texto de <h1> não muda pq foi atribuído a essa tag e elementos de qualquer tipo, como o <h1>, por exemplo, tem valor 1 e 1 é maior que 0, por isso prevalecesse a lei do <h1> e não do seletor universal.

ex.3:
No HTML:

<h1 class=”title”>título<h1>
<p> parágrafo</p>

No CSS:
.title {
color: red
}
h1 {
color: green;
}

h1{
color: blue;
}

Agora adicionamos uma classe no arquivo HTML na linha do titulo. e no arquivo css dissemos que o texto dessa classe tem a cor vermelha. Nesse caso, o texto da h1 vai ficar na cor vermelha e não azul. pq a classe tem valor 10 e 10 é maior que 1, por isso prevalecesse a lei do da classe e não do h1

ex.3:
No HTML:

<h1 class=”title” id=”my-title”>título<h1>
<p> parágrafo</p>

No CSS:
#my-title {
color: gray
}
.title {
color: red
}
h1 {
color: green;
}

h1{
color: blue;
}

Agora adicionamos um id no arquivo HTML na linha do titulo. e no arquivo css dissemos que o texto desse id tem a cor cinza. Nesse caso, o texto da h1 vai ficar na cor cinza e não azul (como mostra o código da h1 no arquvo css) e nem vermelho com mostra o código da classe do h1 no arquivo css). pq o id tem valor 100 e 100 é maior que 10, por isso prevalecesse a lei do id e não do h1 nem da classe.

ex.4:
No HTML:

<h1 class=”title” id=”my-title” style=”color: orange;”>título<h1>
<p> parágrafo</p>

No CSS:
#my-title {
color: gray
}
.title {
color: red
}
h1 {
color: green;
}

h1{
color: blue;
}

Agora adicionamos uma tag style na linha(inline) da tag h1 no arquivo HTML e no arquivo css não fizemos nada. Nesse caso, o texto da h1 vai ficar na cor laranja e não azul (como mostra o código da h1 no arquivo css) e nem vermelho com mostra o código da classe do h1 no arquivo css) e nem cinza como mostra o código do Id no CSS. pq a tag style escrita diretamente na linha tem valor 1000 e 1000 é maior que 100, por isso prevalecesse a lei da tag style e não do id nem do h1 nem da classe que estão escritas no arquivo css.

ex.5:
No HTML:

<h1 class=”title” id=”my-title”>título<h1>
<p> parágrafo</p>

No CSS:
#my-title {
color: gray
}
.title {
color: red
}
h1 {
color: green;
}

h1.title#my-title{
color: blue;
}

Nesse caso, no segundo h1 escrito no .CSS, eu somei os valores para que a segunda linha de código do h1 se sobressaísse. peguei o h1 que tem valor 1 + title que tem valor 100 + class que tem valor 10 = 121, nesse caso o segundo código do h1 prevaleceu em cima do id e da class

ex.5:
No HTML:

<h1 class=”title” id=”my-title”>título<h1>
<p> parágrafo</p>

No CSS:
#my-title {
color: gray
}
.title {
color: red
}
body h1 {
color: green;
}

h1{
color: blue;
}

Nesse caso, adicionei o body para ele procurar tudo que tivesse dentro do body com tag h1 ficasse na cor verde.. e essa junção de body com h1 vai valer 2 ponto (1 de cada elemento: body e h1). nesse caso, prevalece a cor cinza do id

ex.6:
No HTML:

<h1 class=”title” id=”my-title”>título <strong>alo</strong><h1>
<p> parágrafo</p>

No CSS:
#my-title,{
color: gray
}
.title {
color: red
}
body h1 {
color: green;
}

h1{
color: blue;
}

-   {
    color: orange;
    }

Aqui adicionei uma tag strong dentro da tag h1, e o texto da tag strong fica laranja, mas o resto do texto dentro da tag h1 recebe a cor cinza respeitando o id.

ex.6:
No HTML:

<h1 class=”title” id=”my-title”>título <strong>alo</strong><h1>
<p> parágrafo</p>

No CSS:
#my-title,
#my-title strong{
color: gray
}
.title {
color: red
}
body h1 {
color: green;
}

h1{
color: blue;
}

-   {
    color: orange;
    }

Para mudar a situação anterior, e deixar todo o texto na mesma cor, tem que concatenar a tag do id com a tag strong adicionando essa concatenação no arquivo .CSS. usando a vírgula posso colocar mais de uma propriedade e aplicar a regra para mais de um elemento dentro das tag que eu tô trabalhando.

## A importância;

sintaxe: !important

São raras as ocasiões nas quais se devem usar um important, pois é em geral uma má prática, visto que quebra o fluxo natural da cascata e pode acabar te atrapalhando caso você a deixe em algum lugar no seu código.

Portanto evite ao máximo seu uso.

A regra !important passa por cima de todas as outras regras. deve ser usada em último caso, tipo quando você tá tentando mudar uma coisa no código de alguém e não consegue

ex.:
No HTML:

<h1 class=”title” id=”my-title”>título <strong>alo</strong><h1>
<p> parágrafo</p>

No CSS:
```css
#my-title,
#my-title strong{
color: gray
}
.title {
color: red
}
body h1 {
color: green;
}

h1{
color: blue !Important;
}

-   {
    color: orange;
    }
```
