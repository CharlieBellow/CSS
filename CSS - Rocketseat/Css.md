# Introdução

    ## O que significa CSS?
    * Cascading Style Sheet
    * Código para criar estilos no HTML
    * HTML 'a estrutura, e o CSS é a beleza
    * não é uma linguagem de programação
    * É uma linguagem style sheet (folha de estilo)

    ## Vamos ao exemplo
    (abriu o site codepen.io), mas eu fiz no sublime text um arquivo Css-exemplo.html e coloquei os exemplos do CSS dentro da tag style
```css
	h1 {
		color: red; /* os comentários no CSS são com barra e asterísticos (/* comentário * /), os comentário servem para dizer algo a respeito do código ou desabilitar úma parte do código  */
	}
```
# Anatomia

```css
	h1 {
		color: red;
        font-size: 60px;
        background: gray
	}
    /* o código no CSS começa com o elemento que queremos mexer, seguido de abre e fecha chaves `{}` e dentro das chaves colocamos o que queremos mudar, ou seja, a propriedade (dizer se é a cor, o fundo, a fonte... ) > em seguida coloca dois ponto '';'' e depois o valor (se é cor, qual cor vc quer, se é fonte qual tipo de fonte, ou tamanho...) seguido de ; para dizer que terminou a instrução */
	
```
    * Seletor - o Seletor tem a função de: procurar no HTML a tag a que me referi, qd vc achar, aplica essas propriedades citadas no código CSS. Geralmente o seletor é a tag que escrevemos primeiro no código
    * Declaration - a declaração é tudo que eu digo que é pra ser feito, ou seja, tudo que tá dentro das chaves

    * Properties - as propriedades são o que você quer mudar (ex.: cor, font, plano de fundo (background), etc...)

    * Property Value - os valores das propriedades é para qual valor você quer mudar aquela propriedade (ex: se quero mudar a cor, quero que a cor seja qual? esse qual é o valor, quero que a cor seja azul, então o valor é blue)
    
    *OBS 1: quanto mais propriedades eu conheço, mais eu consigo mexer nos meus documentos

    #Selectors (Seletores)

    conecta um elemento HTML com o CSS

  ## Tipos:
    * global selector `*`
    * Element (ou) Type selector `h1, h2, p, div`
    * ID Selector `#box, #conteiner`
    * Class Selector `red, .m-4`
    * attribute selector, Pseudo0class, Pseudo-element, e outros

(abre o site do codepen.io pra mostrar)

para mudar a propriedade de um seletor, devo escrever ele no CSS

#ex.:

No HTML:
    <div id="container" class="m-40"> <!-- aqui criei o id "container" e a classe "m-40"-->
  <h1>título</h1>
  <h2>subtítulo</h2>
</div>

```css
* { /* o seletor universal aplica as propriedades a todos os elementos no código*/
  margin: 0;
}

#container {      /*aqui tô especificando que quero aplicar essas propriedades no ID "container" que foi criado no HTML*/
  width: 200px;
}

.m-40 {       /*aqui tô especificando que quero aplicar essas propriedades na classe "m-40" que foi criada no HTML*/
  margin: 40px;
}

h1, h2 {    /*aqui tô aplicando as mesmas propriedades a dois seletores diferentes, nesse caso a duas tag: h1 e h2 */
  color: green;
  font-size: 60px;
  background: gray;
}
``` 
# Box model:
   
   O CSS trabalha com a ideia de caixas.. então a maioria das coisas no CSS são caixas.
   *toda caixa tem algo dentro, tem conteúdo, tem espaço dentro delas, espaços entre elas...

    * você irá perceber que (quase tudo são caixas no CSS
    * posicionamentos, tamanhos, espaçamentos, bordas, cores
    * caixas podem ficar ao lado uma da outra, ou acima
    * elementos HTML são caixas


   ## Ex.:
   
<html>
    <h1>evolua rápido</h1>
    <p>decrição</p>
    <button>embarcar</buttonn>
</html>

```css
h1 {
  border: 1px solid red; /* borda da caixa*/
  margin: 200px; /*espaço por fora da caixa */
  padding: 60px;
}
```
   
# Origem do CSS

    # Adicionando CSS (existem 4 formas)

    ##inline (coloca as modificações de cores direto na linha de código desejada do HTML)

    * atribuindo 'style'
<html>
      <h1 style="color: blue;"> <!--coloca o código em linha direto no elemento que quero */-->
        título
        <strong style="color: red;" ;>alo</strong>
    </h1>
</html>
    
## <style> (com a tag style)

    * tag html que irá conter o CSS coloca uma tag <style> no arquivo html
<html>
    <head>
        <style>
                h1 {
                    color: red;
                }
                strong {
                    color: blue;
                }
        </style>
    </head>
</html>

    ## <link>

    *arquivo css externo - nesse caso, é necessário criar um arquivo .css e escrever o css lá - (esse é o mais indicado)
<html>
    <head>
     <link rel="stylesheet" href="style.css"> <!--faz referencia a um arquivo css que contem as informações de estilo-->
     </head>
</html>

```css
    /*Aí no arquivo CSS fica assim:*/
h1 {
    color: red; /* lembrando que assim o preview do VS code não funciona, nesse cso usa a extensão live server pra abrir no navegador e atualizar automaticamente */
}



    ## @import  (regra CSS)

    *arquivo css externo - usa só no CSS ou dentro da tag <style>

vai no site google.fonts.com e escolhe uma fonte para importar. aí procurar a fonte que quer, seleciona o estilo da fonte (clica no selecione esse estilo) depois clica em "ver suas famílias selecionadas"
e clica pra marcar a opção @importar

```css
@import url ('https://fonts.googleapis.com/css2? family = Lato: ital, wght @ 1.100 & family = Montserrat: wght @ 100 & display = swap');

ou pode usar sem a função URL:
@import'https://fonts.googleapis.com/css2? family = Lato: ital, wght @ 1.100 & family = Montserrat: wght @ 100 & display = swap';

OBS: essa forma de importar fonte não é a mais indicada pq o site fica mais lento

é mais indcado importar por meio da tag link, nesse caso, o site de fontes do google já aparece na opção link.. aí é só pegar o que tá escrito na parte de CSS e colar no arquivo CSS ou pega a parte que coloca no html (ou seja, a tag <link href="link">) para colocar já no arquivo html

ex. no CSS:

@import'https://fonts.googleapis.com/css2? family = Lato: ital, wght @ 1.100 & family = Montserrat: wght @ 100 & display = swap';

h1 {
    color: red;
    família da fonte: 'Lato', sans-serif;
    família da fonte: 'Montserrat', sans-serif;
    /*adicionando a font montsserrat do fonts.google.com */
}
```



# Cascata:
<!--tá em um arquivo própio-->



# At - Rules

* São regras relacionadas ao comportamento do CSS, 
* começa com um sinal de @ seguido do identificador e do valor.

# São as seguintes:
```css
- @import /*serve para incluir um CSS externo.*/
- @media /* são regras condicionais para vários dispositivos.*/
- @font-face /*é para colocar fontes externas*/
- @keyframes  /*serve para as animations do CSS*/

@import url("https://local.style.css")

@media (min-width: s00px)
    /*regras aqui */

@font-face {
    /*regras aqui */
}
@keyframes nameofanimation {
    /*regras aqui */
}

    # Shorthand

* junção de propriedades
* resumido
* legível

```css
{
    /* background proprietes */
    background-color: #000;
    background-image: url(images/bg.gif);
    background-repeat: no-repeat;
    background-position: left top;

    /* background shorthand */
    background: #000 url(images/bg.gif) no-repeat left top;

   /* basicamente o que você faz é colocar todos os atributos em uma linha só sem especificar o tipo, só precisa dizer que tudo isso tá sendo atribuido ao background, por exemplo*/

    /* font proprieties */
    font-style: italic;
    font-weight: bold;
    font-size: 8em;
    font-height: 1.2;
    font-family: Arial, sans-serif;

    /* background shorthand */
    font: italic bold .8em/1.2 Arial, sans-serif;

}
``` 
    ##Detalhes

    * Não irá considerar propriedades anteriores, ou seja vai considerar o último código colocado respeitando a cascata
    * Valores não especificados irão assumir o valor padrão
    * Geralmente a ordem descrita não importa, mas se houver muitas propriedades com valores semelhantes, podemos encontrar problemas

    ##Propriedades que aceitam o Shorthand

    animation, background, border, border-botton, border-color, border-left, border-radius, border-right, border-style, bprder-top, border-width, colum-rule, columns, flex, flex-flw, font, grid, grid-area, grid-column, grid-row, grid-template, list-style, margin, offset, outline, overflow, padding, place-content, place-items, place-self, text-decoration, trasition

    Para saber quais aceitam Pesquise em: ***https://developer.mozila.org/en-US/docs/Web/CSS/Shorthand_proprieties**

        #Funções
    * nome seguido de abre e fecha parênteses
    * recebe argumentos
    * serve para transformar os argumentos recebidos em coisas para fazer

        ## Exemplos
```css
/*função url, são caixinhas com argumentos*/
@import url("https://urlaqui.com/style.css");

{
    color: rgb(255, 0, 100); /* esse espaço (TAB) que é dado antes do código para separar chama-se identação */
    width: calc(100% - 10%);
}

```
# Dev Tools
    * Ferramenta para desenvolvedores verem os códigos. é só apertar F12 no navegador, ou clicar com o botão direito e clicar em inspecionar.

# Cuidados com a escrita
    * Formatação de texto
    * atenção a espaços, identação que é o tab que dá no código.
    
    # ex:
```css
    p {
       margin: 0 auto; 
    }
```

    # Vendor Prefixes
    * Permite que browsers adicione `features` a fim de colocar um uso alguma novidade que vemos no CSS

    # Exemplo

```css
P {
    -webkit-backgound-clip: text; /*Chrome, Safari, iOS e Android*/
    -moz-background-clip: text;   /* Mozilla (Firefox) */
    -ms-backgound-clip: text;     /* Internet Explorer */
    -o-background-clip: text;     /* Opera */
}
```

    # Consultas: 
    * para pesquisar os prefixos que são suportados e as vesões para poder adptar melhor o CSS ao navegador que estou usando

[https://ireade.github.io/which-vendor-prefix/]
[https://caniuse.com]