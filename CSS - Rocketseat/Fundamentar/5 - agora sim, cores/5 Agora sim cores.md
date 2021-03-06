# 1 CORES

Usamos Css para alterar cores do nosso documento.

## Tipos

* background-color (para caixas)

* color (para textos)

* border-color (para-caixas)

* outros...


## Valores


Podemos definir os valores por


* palavra-chave (blue, transparent)

* hexadecimal (#990011) <!--dois valores para o red, 2 para green e 2 pra blue-->

* funções: rgb, rgba, hsl, hsla

```css
element {
  color: currentcolor;

  /* <named-color> values */
  color: red;
  color: orange;
  color: tan;
  color: rebeccapurple;

  /* <hex-color> values 0-F */
  color: #090; /* RED GREEN BLUE */ /*3 valores*/
  color: #009900; /*6 valores*/
  color: #090a; /* 4 valores para RGB*/ /*o a é o alfa, para dar transparência*/
  color: #009900aa;

  /* <rgb()> values */
  color: rgb(34, 12, 64, 0.6);  /*0 - 255*/
  color: rgb(34, 12, 64, 60%);
  color: rgba(34, 12, 64, 0.6);
  color: rgb(34 12 64 / 0.6);
  color: rgba(34 12 64 / 0.3);
  color: rgb(34.0 12 64 / 60%);
  color: rgba(34.6 12 64 / 30%);


  /* <hsl()> values */
  color: hsl(30, 100%, 50%, 0.6); /* Hue - Saturation - Lumiance */
  color: hsla (30, 100%, 50%, 0.6);
  color: hsl(30 100% 50% / 0.6); /*o que está depois da barra é a transparência*/
  color: hsla (30 100 % 50 % / 0.6);
  color: hsl(30.0 100% 50% / 60%);
  color: hsla (30.2 100% 50% / 60%);

  /* Global values */
  color: inherit; /*herança, herda a cor do elemento anterior*/
  color: initial; /*coloca na cor inicial*/
  color: unset; /* não define cor e o elemento pega do contexto... */
}
```

<!--OBS.: instalei a extensão colorize para que as cores escolhidas fossem mostradas, mas não deu certo pq não funciona em arquivo Markdown(.md). Então instalei a Flutter collor, que não é o que eu queria, mas funciona em alguns casos..-->

# Referência

https://developer.mozilla.org/en-US/docs/Web/CSS/color_value

# 2 BACKGROUND

- Define um fundo para o nosso elemento 
- Sua área de atuação é a caixa toda 
- por padrão, é transparente 

### Exemplos 
- Usar cores sólidas 
- Usar imagens 
- Controlar:
    - a posição das imagens,
    - se elas se repetem ou não
    - o tamanho delas na caixa
- Usar cor e imagem juntas 
- Usar cor gradiente


No HTML:

<header>

</header>
<main> 
  <h1>Evolua rápido como a tecnologia.</h1>
  <p>Junte-se a milhares de devs e acelere na direção dos seus objetivos.</p>
</main>

No CSS:
```css
header {
  height: 500px;
  border: 7px dashed red;
  padding: 160px;
  background-color: rgb(55, 100, 50);
  background-image: url(https://images.pexels.com/photos/1379636/pexels-photo-1379636.jpeg?auto=compress&cs=tinysrgb&dpr=1&w=500);
  background-repeat: no-repeat;
  background-repeat: repeat-y; /*se repete só no eixo y*/
  background-repeat: repeat-x;
  /*se repete só no eixo x */
  
  /*se colocar uma imagem pequena demais, ela vai ficar se repetindo pra completar o tamanho. aí precisa alterar isso com o no-repeat*/
  
  background-position: center; /*altera a posição da imagem*/
  background-size: contain;
  /*
  tem diferentes tipos: 
  * contain: a imagem se expande até tocar pelo menos uma das bordas adicionadas com o comando border, nesse exemplo a borda vermelha
  * cover: a imagem se expande pra preencher a área do quadrado, ou seja, até tocas todas as bordas vermelhas
  * pode usar porcentagem ou pixels também: 
    - quando coloca um só valor se aplica à horizontal (largura da foto) e se colocar mais um valor de percentagem, esse segundo vai se aplicar à altura
    ex: background-size: 500px 100px;
  */

  background-origin: content-box;
  /*
  O background-origin altera a forma como a foto vai se comportar em relação ao lugar onde ela está, nesse caso, em relação ao quadrado
  tem diferentes tipos: 
  * border-box: a imagem se expande até tocar pelo menos uma borda do quadrado e passa da borda que foi adicionada
  * content-box: é o que fica por padrão e faz a mesma coisa que o background-size:contain
  * padding-box: considera a margem padding e inicia o tamanho a partir dalí SÓ FUNCIONOU NA VERTICAL
  * pode usar porcentagem ou pixels também: 
    - quando coloca um só valor se aplica à horizontal (largura da foto) e se colocar mais um valor de percentagem, esse segundo vai se aplicar à altura
    ex: background-size: 500px 100px;
  */

  background-clip: content-box;
  /*serve para alterar as bordas da imagem em relação às bordas da caixa (border) e o padding (espaço entre a borda e o conteúdo, nesse caso, a nossa imagem)
  - border box é o padrão e faz a mesma coisa que o contain, ou seja, a imagem se expande até tocar pelo menos uma das bordas adicionadas com o comando border,
  nesse exemplo a borda vermelha
  - content-box: exclui o padding / passa por cima, era verde e ficou branco
  - padding-box: elimina a parte de fundo do background
  */

}
```

# Background-attachment
altera a questão da foto de fundo acompanhar o conteúdo do texto.. por padrão é o scroll.
- scroll: a foto se mexe junto com o conteúdo, fica parecendo que ela está presa naquela parte especifica do conteúdo.
- fixed: quando dá um scroll com o mouse, a foto de fundo fica estatica e só o texto e mexe

```css
* {margin: 0;}

main {
  color: white;
  background-color: rgb(55, 100, 50);
  background-image: url(https://images.pexels.com/photos/1379636/pexels-photo-1379636.jpeg?auto=compress&cs=tinysrgb&dpr=1&w=500);
  background-repeat: no-repeat;
  background-position: center;
  background-size: contain;
  background-origin: content-box;
  background-clip: content-box;
  background-attachment: fixed; /*gostei desse!*/

  background: rgb(55, 100, 50) url(https://images.pexels.com/photos/1379636/pexels-photo-1379636.jpeg?auto=compress&cs=tinysrgb&dpr=1&w=500) no-repeat right top / 50px border-box content-box fixed;

  /* # shorthand: escrevendo o código acima com menos linhas (versão compacta
  
  OBS: quando dois topicos podem receber valores iguais, usa uma barra pra dizer que estamos falando de propriedades diferentes.. 

  # Gradient
  faz um degradê entre cores. pode alterar onde vai ser a divisão colocando a medida em graus: 90º = 90deg (pra lembrar: 180 degraus)
  */

  /*  background: linear-gradient(180deg, red, orange, yellow, green, blue, purple); */
  /*degradê de arco-iris*/
  background: linear-gradient(180deg, #00E8E8, #FF00FF, #FFFFFF, #FF00FF, #00E8E8); /*degradê da bandeira trans*/

  /*background: radial-gradient(rgba(255, 255, 255 0), rgba(255, 0, 0, 0.2));
*/
}

 /*#mútiplos backgrounds: para usar vários e combinar é só usar a vírgula pra separar*/
```
