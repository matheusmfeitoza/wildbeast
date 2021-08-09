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
