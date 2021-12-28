# Valores e unidades de medida

* cada propriedade possui valores property: value`

* estudo constante a fim de entender as propriedades e seus valores

 ## Prática

* como conhecer e estudar os valores na documentação? 890

  * <color> <length>

* os termos podem variar. 'values ou 'data types`

<!--recomenda a documentação do mdn-->

https://developer.mozilla.org/pt-BR/


# Tipos numéricos

* <integer>   Número inteiro como -10 ou 223
* <number>    Número decimal como -2.4, 64 ou 0.234
* <dimension>   É um <number> com uma unidade junto: 90deg, 2s, 8px
* <percentagem>   Representa a fração de outro número: 50%


## Unidades comuns

* <length>    Representa um valor de distância: px, em, vw
* <angle>   Representa um ângulo: deg, rad, turn
* <time>    Representa um tempo: s, ms
* <resolution>    Representa resoluções para dispositivos: dpi

# Distâncias absolutas <lengthp

São fixas e não alteram seu valor.

UNIDADE        NOME                    EQUIVALÊNCIA  
cm             Centímetros             1cm= 96px/2.54
in             Inches (polegadas)      1in = 2.54cm = 96px
px             Pixels                  1px = 1/96th of lin


* o mais comum e mais utilizado é o **p**
* não recomendado usar cm

<!--mas a minha dúvida continua sendo: como saber quantos pixel tem na tela (viewport) para que eu possa fazer com que a caixa fique onde eu quero, e principalmente, que isso aconteça em qualquer dispositivo-->

# Distâncias relativas


São relativas a algum outro valor, pode ser o elemento pai, ou root, ou o tamanho da tela.

* Benefício: Maior adaptação aos diferentes tipos de tela

UNIDADE         RELATIVO A

em              Tamanho da font do pai.
rem             Tamanho da font do elemento raiz (root/html)
VW              1% da viewport width.
vh              1% da viewport height.

Por padrão o tamanho da fonte é 16px. Para alterar o elemento root, faz assim:

```css
:root {
  font-size: 35px;
}

ou 

html {
  font-size: 23px;
}
```
# Porcentagens %

* Em muitos casos tratado da mesma maneira que as distâncias <length>

* Sempre será relativo a algum valor
```css
NO HTML:
<p> oi </p>

html {
  font-size: 50%;
}
```

Se colocar uma tabela dentro de uma tabela e atribuir à tag <li> o valor de 80%, ele vai considerar o tamanho do primeiro li que é o pai e depois vai atribuir ao li que está dentro dessa tabela pai o valor de 80% e assim sucessivamente:

No HTML:
<body>
  <div></div>
</body>

No Css:
```css
div {
  background-color: blue;
  width:100%;
  height:100px;

}
```
nesse caso tá pegando 100% do body que é o pai dessa div7

então no css ele vai atribuindo valores a partir do valor de algo anterior àquele elemento

# Posições

<position>

Representa um conjunto de coordenadas 2D: - top, right, bottom, left e center

* Usado para alguns tipos de propriedades
* Não confundir com a propriedad `position`

ex:

No HTML:

  <div class="box"></div>


No Css:
```css
.box {
  width:400px;
  height:300px;
  background-image: url(https://source.unsplash.com/random);
  background-repeat: no-repeat;
  background-position: center;
}
```

# Funções

Em programação, funções são reconhecidas por causar um reaproveitamento de código.

* rgb()
* hsl()
* url()
* calc()

## Exemplo do calc
No HTML:

  <div class="box"></div>


No Css:
```css

body {
  height: 100vh;
  /*o viewport (espaço em branco do navegador) não tem altura e largura definido. então é necessário definir quanto quer considerar para poder fazer o calculo*/
}

.box {
  height: calc(100% - 20px);
  width:700px;
  background-image: url(https://source.unsplash.com/random);
  background-repeat: no-repeat;
  background-position: center;
}


# Strings e identificadores

* Strings: Texto envolto em aspas
* Identificadores: red, black, gold;

```css
.box::after {
  content: "isso é uma string";
  color: white; 
}