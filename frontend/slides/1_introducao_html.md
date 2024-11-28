---
marp: true
theme: rose-pine-moon
---

<!-- markdownlint-disable -->

# Introdução ao HTML

Thiago Ribeiro
Ciência da Computação - UFAL

![bg auto right 50%](../src/html5_logo.png)

---

## O que é?

- Linguagem de **Marcação** (~~Não de programação~~);

> "uma série de elementos que você usa para anexar, envolver ou marcar diferentes partes do conteúdo para que apareça ou aja de uma certa maneira"

---

# O Básico

---

## Anatomia de um elemento

![](https://developer.mozilla.org/pt-BR/docs/Learn/HTML/Introduction_to_HTML/Getting_started/grumpy-cat-small.png)

- **Aninhamento**: inserção de elementos em outros elementos

```html
<p>Isso se trata de um <strong>aninhamento</strong> de elementos.</p>
```

---

## Anatomia de um elemento

Tipos de elementos:

- **Em bloco**: realizam quebra de linha. Elementos estruturais.
- **Inline**: sem quebra de linha. Contidos dentro de blocos
  e envolvem apenas pequenas partes do conteúdo
- **Vazios**: tag única, usada para incorporar algo no documento em seu lugar.
  (ex: `img`, `video`, `input`, etc)

```html
<img src="https://marpit.marp.app/marpit.png" />
```

---

## Atributos

![](https://developer.mozilla.org/pt-BR/docs/Learn/HTML/Introduction_to_HTML/Getting_started/grumpy-cat-attribute-small.png)

- Informações sobre os elementos que não aparecem visualmente;
- Separados por espaços, com estrutura key="value";
- **Exceção**:
  - **Atributos booleanos**: atributos de valor único que podem ser passados sem valor

```html
<input type="text" disabled />
```

---

## Anatomia de um documento

```html
<!doctype html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>My test page</title>
  </head>
  <body>
    <p>This is my page</p>
  </body>
</html>
```

---

## Anatomia de um documento

- `<!DOCTYPE html>`: Define o tipo de documento, um artefato histórico necessário para que tudo funcione corretamente.
- `<html></html>`: Elemento raiz que envolve todo o conteúdo da página.
- `<head></head>`: Container para conteúdo não visível, como metadados e links de estilos.
- `<meta charset="utf-8">`: Define a codificação de caracteres como UTF-8, garantindo compatibilidade com diversos textos.
- `<title></title>`: Define o título da página, exibido na guia do navegador e nos favoritos.
- `<body></body>`: Contém todo o conteúdo visível da página.

---

## Caracteres Especiais e Comentários

- Caracteres que fazem parte da sintaxe do HTML não pode ser usados diretamente
- Solução:
  - referência de caracteres
  - ex.: `<` é equivalente a `&lt;`; `>` é equivalente a `&gt;`
  - [tabela de referências](http://en.wikipedia.org/wiki/List_of_XML_and_HTML_character_entity_references)
- Comentários tem marcadores especiais:

```html
<p>Eu não estou dentro de um comentário</p>

<!-- <p>Eu estou!</p> -->
```

---

## Metadados

- Dados que descrevem dados, presentes na `<head>`

```html
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Document</title>
  <link rel="stylesheet" href="style.css" />
</head>
```

---

## Metadados: <meta>

- Define qualquer informação de metadados que não podem ser definidos por outros elementos HTML
- Existem muitos tipos diferentes de elementos <meta>
- `<meta charset="utf-8" />`: especifica a codificação de caracteres do documento
- [Documentação da tag meta](https://developer.mozilla.org/pt-BR/docs/Web/HTML/Element/meta)

---

## Metadados: <meta>

- Muitos elementos `<meta>` incluem atributos `name` e `content`
- `author`, `description`, `generator`, ~~keywords~~, ...

```html
<meta name="tipo do elemento" content="conteudo real do meta" />
```

## ![center](https://developer.mozilla.org/pt-BR/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML/search-result.png)

---

## Metadados: <link>

- `<link>`: especifica as relações entre o documento atual e um recurso externo.
- Principais usos:
  - **favicon**: ícone associado a página
  - **css**: folha de estilo vinculada

```html
<link rel="shortcut icon" href="favicon.ico" type="image/x-icon" />
<link rel="stylesheet" href="style.css" />
```

---

# Explorando os Elementos

---

## Fundamentos do texto

- Um dos principais objetivos do HTML é dar estrutura e significado
  a um texto para a correta exibição em navegadores (**semântica**)
- O conteúdo estruturado torna a experiência de leitura mais fácil e
  mais agradável.
- A **semântica** está em todos os lugares — contamos com experiência anterior para saber qual a função dos objetos do dia a dia
  - _Vai além da estilização_, pois é usada por mecanismos
    de busca e leitores de tela

---

## Elementos Básicos: Parágrafos e Títulos

<div class="twocols">

- Parágrafos:

```html
<p>apenas um parágrafo</p>
```

- Níveis de títulos:

```html
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6</h6>
```

<p class="break"></p>

![heading levels](https://media.geeksforgeeks.org/wp-content/uploads/20231217130922/Screenshot-2023-12-17-130848.png)

</div>

---

## Elementos Básicos: Listas

- Listas Não Ordenadas:

```html
<ul>
  <li>leite</li>
  <li>ovos</li>
  <li>pão</li>
  <li>homus</li>
</ul>
```

- Listas Ordenadas:

```html
<ol>
  <li>Dirija até o final da estrada</li>
  <li>Vá em frente nas duas primeiras rotatórias</li>
  <li>Vire à esquerda na terceira rotatória</li>
  <li>A escola fica à sua direita, a 300 metros</li>
</ol>
```

---

## Elementos Básicos: Ênfase e Importância

- Quando queremos acrescentar ênfase na linguagem falada, enfatizamos certas palavras, alterando sutilmente o significado do que estamos dizendo

```html
Estou <em>feliz</em> que você não chegou <em>atrasado</em>
```

- Estou _feliz_ que você não chegou _atrasado_.

```html
Estou <strong>feliz</strong> que você não chegou <strong>atrasado</strong>
```

- Estou **feliz** que você não chegou **atrasado**.
- Reconhecidos por leitores de tela e falado em tom diferente;
- Navegadores exibem como negrito e itálico, mas não deve ser usado para esse propósito. Use: `<i>` e `<b>`

---

## Elementos Básicos: Outros

---

## Hyperlinks

- Torna a web como ela é;
- Vinculam documentos a qualquer outro documento (ou a ele mesmo);
- Você pode transformar qualquer conteúdo em link, colocando dentro das tags `<a></a>`

```html
<p>
  Estou criando um link para
  <a href="https://www.mozilla.org/pt-BR/">a página inicial da Mozilla</a>.
</p>
```

<p>
  Estou criando um link para
  <a href="https://www.mozilla.org/pt-BR/">a página inicial da Mozilla</a>.
</p>

---

## Hyperlinks: URLs e caminhos

- Os URLs usam caminhos para encontrar arquivos;
- **URL Absoluto:** Um caminho completo para um recurso, incluindo protocolo e domínio:

```html
<a href="https://example.com/about">Sobre Nós</a>
```

- **URL Relativo**: Relacionado à localização do arquivo HTML. Navegando na mesma estrutura de páginas:

```html
<!-- Página no mesmo diretório -->
<a href="contato.html">Contato</a>
<!-- Subdiretório -->
<a href="pasta/arquivo.html">Arquivo</a>
```

---

## Hyperlinks: URLs e caminhos

- URLs Absolutos _versus_ Relativos

| Tipo de URL | Vantagem                      | Desvantagem                    |
| ----------- | ----------------------------- | ------------------------------ |
| Absoluto    | Funciona em qualquer lugar    | Quebra se o domínio mudar      |
| Relativo    | Fácil de gerenciar localmente | Depende da estrutura da página |

---

## Hyperlinks: Fragmentos de documentos

- O que são **Fragmentos**?

  - Saltos dentro da mesma página ou entre seções de diferentes documentos.
  - Criados usando IDs nos elementos HTML.

Defina o id de destino:

```html
<h2 id="seção1">Seção 1</h2>
```

Crie o hyperlink:

```html
<a href="#seção1">Ir para Seção 1</a>
```

---

## Estruturação

- As páginas da web podem e serão muito diferentes umas das outras, mas todas tendem a compartilhar componentes padrão semelhantes:
- Cabeçalho, Barra de Navegação, conteúdo principal, barra lateral e rodapé

![bg right auto Semantic HTML Layout](https://www.scientecheasy.com/wp-content/uploads/2024/05/html-webpage-layout.png)

---

## Estruturação

- cabeçalho: `<header>`.
- barra de navegação: `<nav>`.
- conteúdo principal: `<main>`, com subseções representadas por `<article>`, `<section>`, e elementos `<div>`.
- barra lateral: `<aside>`
- rodapé: `<footer>`.

![bg right auto Semantic HTML Layout](https://www.scientecheasy.com/wp-content/uploads/2024/05/html-webpage-layout.png)

---

## Estruturação

- **`<main>`**: Define o conteúdo principal da página; deve ser único e diretamente filho de `<body>`.
- **`<article>`**: Bloco de conteúdo independente, como postagens de blog ou artigos de notícias.
- **`<section>`**: Agrupa conteúdo funcional ou temático, geralmente com um título.
- **`<aside>`**: Conteúdo complementar ao principal, como links relacionados ou notas de rodapé.
- **`<header>`**: Introduz o conteúdo de uma página ou seção, como títulos ou menus.
- **`<nav>`**: Define a área principal de navegação com links importantes.
- **`<footer>`**: Contém o conteúdo final da página, como créditos ou informações legais.

---

## Elementos Não Semânticos

- Às vezes, você se depara numa situação em que não consegue encontrar um elemento semântico ideal para agrupar alguns itens ou agrupar algum conteúdo. Nesses momentos, convém agrupar um conjunto de elementos para afetá-los todos como uma única entidade com alguns CSS ou JavaScript

---

## Elementos de Layout Não Semânticos: Div e Span

- `<span>`: é um elemento não-semântico embutido, que você deve usar apenas se não conseguir pensar em um elemento de texto semântico melhor
- `<div>`: é um elemento não semântico no nível de bloco, que você deve usar apenas se não conseguir pensar em um elemento de bloco semântico melhor

---

## Elementos de Layout Não Semânticos: Div e Span

```html
<div class="carrinho-de-compras">
  <h2>Carrinho de compras</h2>
  <ul>
    <li>
      <p>
        <a href=""><strong>Brincos de prata</strong></a
        >: $99.95.
      </p>
      <img src="../products/3333-0985/thumb.png" alt="Brincos de prata" />
    </li>
    <li>...</li>
  </ul>
  <p>Preço total: $237.89</p>
</div>
```

---

## Elementos Não Semânticos: Br e Hr

- `<br>`: cria uma quebra de linha em um parágrafo;
- `<hr>`: criam uma regra horizontal no documento que indica uma alteração temática no texto

---

# Multimídias

---

## Imagens

- `<img>`: Usado para exibir imagens no HTML.
- Atributos principais:
  - **`src`**: Caminho para a imagem.
  - **`alt`**: Texto alternativo para acessibilidade.
  - **`width`** e **`height`**: Controle de tamanho.
- Exemplo:
  ```html
  <img src="imagem.jpg" alt="Descrição da imagem" width="300" />
  ```

---

## Imagens

<div class="twocols">

- Atribuindo **semântica** para imagens;
- `<figure>`: contâiner semântico para imagens.
- `<figcaption>`: é utilizado dentro do `<figure>` para fornecer essa legenda ou descrição associada.

```html
<figure>
  <img src="html5_logo.png" alt="Descrição da imagem" size="300px" />
  <figcaption>Legenda da imagem</figcaption>
</figure>
```

<p class="break"></p>

<figure >
  <img src="../src/html5_logo.png" alt="Descrição da imagem" size="300px">
  <figcaption>Legenda da imagem</figcaption>
</figure>

</div>

---

## Vídeos

- `<video>`: Exibe vídeos diretamente na página.
- Atributos principais:
  - **`src`**: Caminho do vídeo.
  - **`controls`**: Exibe os controles de reprodução.
  - **`autoplay`**: Reprodução automática (use com cuidado).
  - **`loop`**: Reproduz o vídeo em loop.
- Exemplo:
  ```html
  <video src="video.mp4" controls width="640"></video>
  ```

---

## Áudios

- `<audio>`: Reproduz áudio na página.
- Atributos principais:
  - **`src`**: Caminho do áudio.
  - **`controls`**: Exibe os controles de reprodução.
  - **`autoplay`**: Reprodução automática.
  - **`loop`**: Reproduz o áudio continuamente.
- Exemplo:
  ```html
  <audio src="audio.mp3" controls></audio>
  ```

---

# Tabelas

---

## O básico sobre Tabelas

- As tabelas organizam dados em linhas e colunas.
- Usam o elemento `<table>`.
- Compostas por:
  - **Linhas**: `<tr>` (table row)
  - **Células**: `<td>` (table data)
  - **Cabeçalhos**: `<th>` (table header)

---

## O básico sobre Tabelas

Elementos principais:

- **`<table>`**: Define a tabela.
- **`<tr>`**: Define uma linha.
- **`<td>`**: Define uma célula com dados.
- **`<th>`**: Define uma célula de cabeçalho.
  - Geralmente, é exibida em negrito e centralizada.

Agrupamento de Tabelas:

- **`<thead>`**: Agrupa cabeçalhos.
- **`<tbody>`**: Agrupa o corpo da tabela.
- **`<tfoot>`**: Agrupa o rodapé da tabela.

---

## O básico sobre Tabelas

<div class="twocols">

Exemplo:

```html
<table>
  <thead>
    <tr>
      <th>Nome</th>
      <th>Idade</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>João</td>
      <td>25</td>
    </tr>
    ...
  </tbody>
</table>
```

<p class="break"></p>

<table>
  <thead>
    <tr>
      <th>Nome</th>
      <th>Idade</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>João</td>
      <td>25</td>
    </tr>
    <tr>
      <td>Pedro</td>
      <td>28</td>
    </tr>
    <tr>
      <td>Carla</td>
      <td>21</td>
    </tr>
  </tbody>
</table>

</div>

---

## Mesclagem de Células

<div class="twocols">

```html
<table>
  <tr>
    <th colspan="2">Título</th>
  </tr>
  <tr>
    <td>Linha 1, Coluna 1</td>
    <td>Linha 1, Coluna 2</td>
  </tr>
  <tr>
    <td rowspan="2">Mesclado</td>
    <td>Linha 2, Coluna 2</td>
  </tr>
  <tr>
    <td>Linha 3, Coluna 2</td>
  </tr>
</table>
```

<p class="break"></p>

- **`colspan`**: Mescla colunas.
- **`rowspan`**: Mescla linhas.

<table>
  <tr>
    <th colspan="2">Título</th>
  </tr>
  <tr>
    <td>Linha 1, Coluna 1</td>
    <td>Linha 1, Coluna 2</td>
  </tr>
  <tr>
    <td rowspan="2">Mesclado</td>
    <td>Linha 2, Coluna 2</td>
  </tr>
  <tr>
    <td>Linha 3, Coluna 2</td>
  </tr>
</table>

</div>

---

# Referências

- **Introdução ao HTML**. MDN Web Docs. [Acesso aqui](https://developer.mozilla.org/pt-BR/docs/Learn/HTML/Introduction_to_HTML)

---
