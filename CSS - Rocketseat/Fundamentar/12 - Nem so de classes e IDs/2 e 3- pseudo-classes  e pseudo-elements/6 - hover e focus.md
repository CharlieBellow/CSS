## Ações do usuário

  * :hover
  * :focus

  # Atributos:
  * :disabled
  * :required

Algumas estilos só são aplicados quando o usuário faz alguma ação na página.

# :hover

HTML: 
<a href="#">Clique aqui</a>

<input type="text">

```css
a:hover {
  color: red;
}

input:focus{
  border-color: red;
  outline: none; /* ´e a borda que já existe na entrada de dados.. não é indicado usar o none pra tirar ela pq serve pra acessibilidade */
}
```
Vai mudar a cor do link para vermelho quando o usuário passar o mouse sobre o link

# :focus 

é aplicado quando o elemento recebe o foco da ação do usuário que pode ser feita utilizando o teclado ou clicando no elemento com o mouse. É comumente usado em campos de input como uma forma de mostrar qual o input "ativo".

```css
input:focus {
  border-color: red;
}
```

