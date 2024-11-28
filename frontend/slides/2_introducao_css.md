---
marp: true
theme: rose-pine-moon
---

<!-- markdownlint-disable -->

# Introdução ao CSS

Thiago Ribeiro
Ciência da Computação - UFAL

![bg auto right 36%](../src/css_logo.png)

---

## O que é ?

- Linguagem para especificar como documentos são **apresentados** aos usuários
- Como eles são _estilizados_, _dispostos_ etc.

"Você define regras especificando grupos de estilo que devem ser aplicados para elementos particulares ou grupos de elementos na sua página web"

```css
h1 {
  color: red;
  font-size: 5em;
}
```

---

## Aplicando CSS

1. **Inline**

- Adicionado diretamente ao atributo `style` do elemento.

```html
<p style="color: blue; font-size: 20px;">Texto azul</p>
```

2. **Em bloco (no `<style>` dentro do HTML)**

- Definido na tag `<style>` dentro do `<head>`.

```html
<head>
  <style>
    p {
      color: red;
    }
  </style>
</head>
```

---

## Aplicando CSS (cont.)

3. **Em arquivo externo**

- Arquivo `.css` separado, vinculado ao HTML com `<link>`.

```html
<head>
  <link rel="stylesheet" href="estilo.css" />
</head>
```

- Arquivo `estilo.css`:

```css
p {
  color: green;
}
```

---

## Seletores no CSS

- Os seletores definem quais elementos o CSS irá estilizar.

### Tipos de seletores básicos:

1. **De tipo**: Estiliza todos os elementos de um tipo específico.

   ```css
   p {
     font-size: 16px;
   }
   ```

2. **Universal**: Estiliza todos os elementos.
   ```css
   * {
     margin: 0;
     padding: 0;
   }
   ```

---

## Seletores avançados

### 1. **Classe**

- Estiliza elementos com uma classe específica (`.`).

```html
<p class="destaque">Texto destacado</p>
```

```css
.destaque {
  color: orange;
}
```

### 2. **ID**

- Estiliza um único elemento com um ID específico (`#`).

```html
<p id="importante">Texto importante</p>
```

```css
#importante {
  font-weight: bold;
}
```

---

## Seletores combinados

### 1. **Descendente**

- Estiliza elementos dentro de outro elemento.

```css
div p {
  color: blue;
}
```

### 2. **Combinador de filhos**

- Estiliza apenas elementos filhos diretos.

```css
div > p {
  color: green;
}
```

---

## Seletores combinados (cont.)

### 3. **Adjacente**

- Estiliza o elemento que vem imediatamente após outro.

```css
h1 + p {
  color: purple;
}
```

### 4. **Irmãos gerais**

- Estiliza todos os elementos irmãos seguintes.

```css
h1 ~ p {
  color: gray;
}
```

---

## Seletores Pseudo-classes

- Estilizam estados ou partes específicas de um elemento.

### Exemplos:

```css
a:hover {
  color: red;
}
input:focus {
  border: 2px solid blue;
}
```

- **`:hover`**: Quando o mouse passa sobre o elemento.
- **`:focus`**: Quando o elemento está ativo ou selecionado.

---

## Seletores Pseudo-elementos

- Estilizam partes específicas de um elemento.

### Exemplos:

```css
p::first-line {
  font-weight: bold;
}
div::before {
  content: "👉 ";
}
```

---

## Box Model

- O **modelo de caixa (Box Model)** é um conceito fundamental no CSS, que define como os elementos HTML são representados no layout de uma página web. Cada elemento em HTML é tratado como uma "caixa retangular", e o modelo de caixa explica como o navegador calcula seu tamanho e posicionamento.

---

## **Estrutura do Box Model**

- Cada caixa possui quatro camadas principais, de dentro para fora:

1. **Content (Conteúdo)**: Onde o texto e os elementos são exibidos.
   - Dimensões controladas por `width` e `height`.
2. **Padding (Preenchimento)**: Espaço entre o conteúdo e a borda.
3. **Border (Borda)**: Contorno ao redor do padding e do conteúdo.
4. **Margin (Margem)**: Espaço entre a borda da caixa e outros elementos.

---

## Estrutura do Box Model

<center>
<img width=75% src="https://developer.mozilla.org/pt-BR/docs/Learn/CSS/Building_blocks/The_box_model/box-model.png" />
</center>

---

## Tipos de Exibição: `display`

### **Caixa em Linha (`inline`)**:

- Exibe elementos em linha, um ao lado do outro, como texto.
- Ignora `width` e `height`.
- Exemplo: `<span>`, `<a>`.

```css
display: inline;
```

---

## Tipos de Exibição: `display`

### **Caixa em Bloco (`block`)**:

- Ocupa toda a largura do contêiner.
- Respeita `width`, `height`, `padding`, `margin` e `border`.
- Exemplo: `<div>`, `<p>`.

```css
display: block;
```

---

### Outros Valores de Display:

1. **`inline-block`**:
   - Combina características de `inline` (pode estar em linha) e `block` (respeita dimensões).
2. **`none`**:
   - Remove o elemento do layout, como se ele não existisse.

---

## Box-Sizing

Por padrão, `width` e `height` afetam somente o **conteúdo**.

- Isso pode ser modificado com `box-sizing`.

```css
box-sizing: content-box; /* Padrão */
box-sizing: border-box; /* Inclui padding e border no cálculo de width/height */
```

---

## Box-Sizing: content-box

<div class="twocols">

- Espaço ocupado pela caixa é na verdade 410px (350 + 25 + 25 + 5 + 5) e a altura 210px (150 + 25 + 25 + 5 + 5)

```css
.box {
  width: 350px;
  height: 150px;
  margin: 10px;
  padding: 25px;
  border: 5px solid black;
}
```

<p class="break"></p>

<center>
<img src="https://developer.mozilla.org/pt-BR/docs/Learn/CSS/Building_blocks/The_box_model/standard-box-model.png" />
</center>

</div>

---

## Box-Sizing: border-box

<div class="twocols">

```css
.box {
  width: 350px;
  height: 150px;
  margin: 10px;
  padding: 25px;
  box-sizing: border-box
  border: 5px solid black;
}
```

<p class="break"></p>

<center>
<img src="https://developer.mozilla.org/pt-BR/docs/Learn/CSS/Building_blocks/The_box_model/alternate-box-model.png" />
</center>

</div>

---

# Estilização de Texto no CSS

---

## **Propriedades de Texto no CSS**

### **1. Cor do Texto**

- Define a cor do texto.
- Usada com a propriedade `color`.

```css
color: blue; /* Nome da cor */
color: #ff5733; /* Código hexadecimal */
color: rgb(255, 87, 51); /* Código RGB */
```

---

## **2. Alinhamento de Texto**

- Controla o alinhamento horizontal do texto.
- Usada com a propriedade `text-align`.

```css
text-align: left; /* Alinhado à esquerda */
text-align: right; /* Alinhado à direita */
text-align: center; /* Centralizado */
text-align: justify; /* Justificado */
```

---

## **3. Transformação de Texto**

- Modifica a capitalização do texto.
- Usada com a propriedade `text-transform`.

```css
text-transform: uppercase; /* Tudo em maiúsculas */
text-transform: lowercase; /* Tudo em minúsculas */
text-transform: capitalize; /* Primeira letra maiúscula */
```

---

## **4. Espaçamento Entre Caracteres**

- Define o espaço entre os caracteres do texto.
- Usada com a propriedade `letter-spacing`.

```css
letter-spacing: 2px; /* Espaçamento aumentado */
letter-spacing: -1px; /* Espaçamento reduzido */
```

---

## **5. Espaçamento Entre Linhas**

- Define o espaço entre as linhas de um texto.
- Usada com a propriedade `line-height`.

```css
line-height: 1.5; /* Espaçamento relativo ao tamanho da fonte */
line-height: 20px; /* Espaçamento fixo */
```

---

## **6. Decoração de Texto**

- Aplica efeitos visuais ao texto.
- Usada com a propriedade `text-decoration`.

```css
text-decoration: none; /* Sem decoração */
text-decoration: underline; /* Sublinhado */
text-decoration: overline; /* Linha acima do texto */
text-decoration: line-through; /* Riscar o texto */
```

---

## **7. Sombreamento no Texto**

- Adiciona sombras ao texto.
- Usada com a propriedade `text-shadow`.

```css
text-shadow: 2px 2px 5px gray; /* deslocamento X, deslocamento Y, raio de desfoque, cor */
```

---

## **8. Indentação de Texto**

- Adiciona recuo na primeira linha de um parágrafo.
- Usada com a propriedade `text-indent`.

```css
text-indent: 30px; /* Indenta 30px */
```

---

# Referências

- **Introdução ao CSS**. MDN Web Docs. [Acesso aqui](https://developer.mozilla.org/pt-BR/docs/Learn/CSS)

---
