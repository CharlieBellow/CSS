# box model


- Fundamental para fazer layouts para a web

- Maior facilidade para aplicar o CSS

## O que é?

Uma caixa retangular.

Essa caixa possui propriedades de uma caixa (2D)

- Tamanho (largura x altura)        width | height
- Conteúdo                          content
- Bordas                            border
- Preenchimento interno             padding
- Espaços fora da caixa             margin

*Cada elemento na sua página, será considerado uma caixa.*


## box-sizing

Como será calculado o tamanho total da caixa?

- content-box| border-box

por padrão o tamanho da caixa é calculado a partir dos atributos colocados nela. se eu considero 100px mas coloco uma margem de 20 px, então a caixa fica com 140px. ou seja, o conteúdo da caixa tem 100px e a margem tem 20 px e cada lado;
Para fazer com que a caixa (incluindo a margem) tenha 100px, usa o box-sizing: border-box;

```CSS

* {
  box-sizing: border-box;
}

# Ex:

div {
  width: 100px;
  height: 100px;
  border: 1px solid red;
  margin: 10%;
  padding: 0 20px;
  box-sizing: border-box;
}
```


## display: block vs display: inline


- Como as caixas se comportam em relação às outras caixas 
- Comportamento externo das caixas

| **block**                                                            |   **inline**                                             |
|----------------------------------------------------------------------|----------------------------------------------------------|
| Ocupa toda a linha, colocando o próximo elemento abaixo desse        | Elemento ao lado do outro                                |
|----------------------------------------------------------------------|----------------------------------------------------------|
| width e height são respeitados                                       | width e height não funcionam                             |
|----------------------------------------------------------------------|----------------------------------------------------------|
| padding, margin, border irão funcionar normalmente.                  | Somente valores horizontais de margin, padiing e border. |
|----------------------------------------------------------------------|----------------------------------------------------------|

# exemplos


block: <p> <div> <section>` todos os headings <h1><h2>...' 
inline; <a> <strong> <span> <em>


<div>block</div>

<span>inline</span>

```css
div {
  height: 100px;
  border: 1px solid red;
  width: 10px;
  display: inline; /*aqui faz a div se comportar como inline*/
}

span {
  width: 10px;
  height: 100px;
  border: 1px solid green;
  display: block; /*aqui faz o span se comportar como block*/
}
```

* quando usa o display: block ou inline, as formatações só funcionam no block. No inline, só funciona os valores horizontais

ex:

```css

div {
  margin: 20px;
  }

span {
  margin: 100px;
}

```

## margin


Espaços entre os elementos

- margin-top | margin-right | margin-bottom | margin-left <!--para lembrar da sequência imagina as horas do relógio, em sentido horário.--> 

- values: <length>| <percentage | auto

```CSS

div {


/* shorthand */

    margin: 12px 16px 10px 4px; /*quando tem os quatro representa cada uma das laterais.*/

    margin: 12px 16px 0; /*quando tem só 3 medidas, a primeira é o topo, a segunda são as duas laterais juntas e a últipa é o bottom(parte de baixo)*/

    margin: 8px 16px; /*quando tem só dois é a parte de cima e de baixo no primeiro espaço e as duas laterais no segundo espaço*/

    margin: 8px; /*quando só tem uma, se aplica a todos os lados */

    margin: 10px auto;  /* Respondendo a minha dúvida, se usar o auto, o computador vai calcular as leterais e deixar a caixa no meio, mas só funciona nas laterais*/

}
  * o margin só se aplica a elementos do tipo block.
  * Cuidado com margin collapsing (top se ajunta ao bottom, e só acontece com o block)


https://developer.mozilla.org/en-US/docs/Web/CSS/margin


## padding

Preenchimento interno da caixa


- padding-top | padding-right | padding-bottom | padding-left

- values: `<length>` | `<percentage>`

```css
* { margin: o; }
div {
  /* shorthand */
  padding: 12px 16px 10px 4px;
  padding: 12px 16px 0;
  padding: 8px 16px;
  padding: 8px;
 /*segue o mesmo princípio do relógio*/
}

• Padding poderá causar diferença na largura de um elemento

ex:

* { margin: o; }
div, section {
  border: 1px solid red;
  padding: 10px 2em 8px 50%;
}

```

## border (e outline )


As bordas da caixa



-value: `<border-style>` | `<border-width>` | `<border-color>`
  -style: solid | dotted | dashed | double | groove | ridge | inset | outset

  - width: `<length>`

  - color: `<color>`
```css
div {

/* shorthand */

border-top: solid 2px; /* top | right | bottom | left */

/* style */
border: solid;

/* width <length> | style */
border: 2px dotted;


/* style | color */

border; outset #f33;


/* width | style | color */ 
border: medium dashed green;

}

ex:
div, section {
  width: 100px;
  height: 100px;
  margin: 20% auto;
  border: 20px solid red;
  border-top: double green 4px;
  border-bottom: none;
  
  
  outline: yellow 4px solid;


}

## outline


- difere em 4 sentidos:

  - Não modifica o tamanho da caixa, pois não é parte do Box Model

  - Poderá ser diferente de retangular - Não permite ajuste individuais

  - Mais usado pelo user agent para acessibilidade

https://developer.mozilla.org/en-US/docs/web/CSS/border

<input type="text">