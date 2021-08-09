#CSS GRID LAYOUT

## GRID CONTAINER

Tag que irá envolver os elementos para serem GRID; \*\* O Filho do filho não será GRID

display: grid; Tem o comportamento inicial similar ao display BLOCK;

Quando for usar o grid, tenho que me ater as propriedades templates, ou seja, ele sempre vai começar com grid e logo após virá o template:

Exemplo:

- grid-templates-columns

--

O display sera aplicado no container, para afetar os filhos:

```html
<section class="container">
  <div class="Item1">1</div>
  <div class="Item1">2</div>
  <div class="Item1">3</div>
  <div class="Item1">4</div>
</section>
```

Unidade FR foi introduzida no grid layout:

Quer dizer que é 1 fração , ou seja posso ter 3 elementos e quero que eles sejam iguais em tamanho, logo coloco 1fr 1fr 1fr. Posso ir alterando as frações de acordo com o planejado.

Exemplo:

```html
<section class="grid-fr">
  <div class="Item1">1</div>
  <div class="Item1">2</div>
  <div class="Item1">3</div>
  <div class="Item1">4</div>
</section>
```

```css
.grid-fr {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
}
```

Resultado

<section class="grid-fr" style="display:grid; grid-template-columns: 1fr 1fr 1fr 1fr; border: 1px solid white; max-width:400px; margin:0 auto;">
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">1</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">2</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">3</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">4</div>
</section>
--

## Propriedades:

grid-template-columns: Define o número de colunas dentro do grid.

Como usar:

No HTML eu defino meu container ou classe que desejo aplicar o grid:

```html
<section class="grid-fr">
  <div class="Item1">1</div>
  <div class="Item1">2</div>
  <div class="Item1">3</div>
  <div class="Item1">4</div>
</section>
```

```css
.grid-fr {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
}
```

No CSS eu defino o display grid + a propriedade em questão:

Exemplos:

- Usando px:

<section class="grid-fr" style="display:grid; grid-template-columns: 100px 100px 100px 100px; border: 1px solid white; max-width:400px; margin:0 auto;">
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">1</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">2</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">3</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">4</div>
</section>

- Usando fr:

<section class="grid-fr" style="display:grid; grid-template-columns: 1fr 1fr 1fr 1fr; border: 1px solid white; max-width:400px; margin:0 auto;">
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">1</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">2</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">3</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">4</div>
</section>

---

Podemos economizar tempo usando a função repeat(); Funciona assim: repeat("Número de colunas","Tamanho")

<section class="grid-fr" style="display:grid; grid-template-columns: repeat(4,1fr); border: 1px solid white; max-width:400px; margin:0 auto;">
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">1</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">2</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">3</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">4</div>
</section>

- Usando px como unidade de medida:

<section class="grid-fr" style="display:grid; grid-template-columns:repeat(4,100px); border: 1px solid white; max-width:400px; margin:0 auto;">
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">1</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">2</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">3</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">4</div>
</section>

**Tenho sempre que me ater ao tamanho do meu container, para não estourar ele.**

Segue exemplo de um container estourado, isto porque no elemento pai, foi definido um max-width de 400px. Observe abaixo:

<section class="grid-fr" style="display:grid; grid-template-columns:repeat(4,150px); border: 1px solid white; max-width:400px; margin:0 auto;">
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">1</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">2</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">3</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">4</div>
</section>

---

Trabalhando com minmax(), ou seja ele tera o mínimo como base e o máximo que ele poderá atingir;

<section class="grid-fr" style="display:grid; grid-template-columns:repeat(4,minmax(100px,1fr)); border: 1px solid white; max-width:400px; margin:0 auto;">
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">1</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">2</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">3</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">4</div>
</section>

---

Começando a entrar na responsividade com auto-fill e auto-fit:

auto-fill, irá auto organizar o item dentro do container de acordo com o tamanho solicitado, segue exemplo:

<section class="grid-fr" style="display:grid; grid-template-columns:repeat(auto-fill,100px); border: 1px solid white; max-width:400px; margin:0 auto;">
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">1</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">2</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">3</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">4</div>
</section>

auto-fit, dará sempre prioridade para as colunas, mesmo que sobre espaço ele irá criar mais colunas e não alocar o elemento conforme o auto-fill. Segue exemplo:

<section class="grid-fr" style="display:grid; grid-template-columns:repeat(auto-fit,80px); border: 1px solid white; max-width:400px; margin:0 auto;">
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">1</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">2</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">3</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">4</div>
</section>

Neste exemplo ele deixou um espaço em branco, onde caso, se tive espaço e entrar mais um elemento div, ele alocará o mesmo.

## grid-template-rows

Utiliza as mesmas propriedades do columns, vamos para os exemplos:

Neste primeiro exemplo iremos utilizar apenas 2 colunas com 2 linhas e iremos alterar os tamanhos das linhas, sendo a primeira com 100px e segunda com 200px;

<section class="grid-fr" style="display:grid; grid-template-columns:1fr 1fr; grid-template-rows:100px 200px; border: 1px solid white; max-width:400px; margin:0 auto;">
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">1</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">2</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">3</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">4</div>
</section>

Neste exemplo eu defini um grid columns de 2 colunas e defini um rows com 4 linhas de 100px, porém como o conteúdo já se ajustou em 2 linhas, ele deixara o espaço vazio para o restante que entrar. Note que usamos a propriedade repeat().

<section class="grid-fr" style="display:grid; grid-template-columns:repeat(auto-fit,200px); grid-template-rows:repeat(4,100px); border: 1px solid white; max-width:400px; margin:0 auto;">
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">1</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">2</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">3</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">4</div>
</section>

Neste exemplo passamos o repeat() com auti-fill e tamanho de 300px e um minmax de 100px e 1fr

<section class="grid-fr" style="display:grid; grid-template-columns:repeat(auto-fill,250px); grid-template-rows:repeat(4,minmax(100px,1fr)); border: 1px solid white; max-width:400px; margin:0 auto;">
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">1</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">2</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">3</div>
    <div class="item" style="background-color:tomato; text-align: center; font-size: 1.1em; margin: 5px; border: 1px solid black;">4</div>
</section>

## Grid template areas

Define as áreas do site.

Como usar:

```html
<section class="container">
  <div class="item logo">Logo</div>
  <div class="item nav">nav</div>
  <div class="item sidenav">sidenav</div>
  <div class="item content">content</div>
  <div class="item advert">advert</div>
  <div class="item footer">footer</div>
</section>
```

```css
body {
  background-color: black;
  color: white;
}
.container {
  display: grid;
  grid-template-areas:
    "logo nav nav"
    "sidenav content advert"
    "sidenav footer footer";
  border: 1px solid white;
  max-width: 400px;
  margin: 0 auto;
  margin-top: 100px;
}
.item {
  background-color: tomato;
  margin: 5px;
  padding: 5px;
  font-size: 1.2em;
  text-align: center;
}

.logo {
  grid-area: logo;
}

.nav {
  grid-area: nav;
}
.sidenav {
  grid-area: sidenav;
}
.content {
  grid-area: content;
}
.advert {
  grid-area: advert;
}
.footer {
  grid-area: footer;
}
```

Vamos aplicar este layor na prática:

![Layot usando grid areas](./assets/img/imgsMD/grid-areas.png)

## Grid template

É a junção dos 3 elementos que vimos anteriormente, mais conhecido como shortcut, veremos exemplos:

```html
<section class="container">
  <div class="item logo">Logo</div>
  <div class="item nav">nav</div>
  <div class="item sidenav">sidenav</div>
  <div class="item content">content</div>
  <div class="item advert">advert</div>
  <div class="item footer">footer</div>
</section>
```

Forma 1 de se aplicar o css:

```css
display: grid;
grid-template: 50px 50px 50px / repeat(2, 1fr); /* Primeiro as linhas, depois colunas */
```

resultado:

Note que usamos apenas o template sem apontar os indicativos das classes.

![Layout usando grid-template, forma 1](.\assets\img\imgsMD\grid-template1.png)
