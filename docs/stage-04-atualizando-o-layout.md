# Stage 04: Adicionando Estrutura e Estilos ao Layout

Neste estágio, foram feitas alterações significativas no layout do projeto, tanto no HTML quanto no CSS. Abaixo estão as mudanças detalhadas:

---

## Alterações no `index.html`

1. **Estrutura do Container Principal (`main-container`)**:
   - Adicionado um container principal (`main-container`) que contém:
     - Um botão de "Voltar" com um ícone e texto.
     - Um título (`h1`) para o formulário de matrícula.
     - Um parágrafo (`p`) com instruções para o usuário.

   ```html
   <div class="main-container">
       <div class="back">
           <img src="assets/icons/arrow-left-02.svg" alt="Clique para voltar">
           <span>Voltar</span>
       </div>
       <h1>Formulário de Matricula</h1>
       <p>
           Preencha os dados abaixo para matricular seu filho na escola de educação infantil Estrelas do Amanhã.
       </p>
   </div>
   ```

2. **Estrutura do Container Lateral (`aside-container`)**:
   - Adicionado um container lateral (`aside-container`) que contém:
     - Um cabeçalho (`header`) com a logo da escola, um título (`h2`) e um parágrafo (`p`) explicativo.
     - Uma ilustração (`img`) de uma professora com alunos.

   ```html
   <div class="aside-container">
       <header>
           <img src="assets/logo.svg" alt="Imagem da logo Estrelas do amanhã">
           <h2>Porque cada momento de <span>aprendizado</span> conta</h2>
           <p>
               Inscreva seu filho em nossa escola e veja-o florescer em um ambiente acolhedor, seguro e estimulante.
           </p>
       </header>
       <img src="assets/image/Illustration.svg" alt="Ilustração de uma professora com alguns alunos ao seu redor">
   </div>
   ```

---

## Alterações no `layout.css`

1. **Estilos para o Botão de Voltar (`.back`)**:
   - Adicionado um estilo para o botão de "Voltar" com:
     - `display: flex` para alinhar o ícone e o texto.
     - `gap` para espaçamento entre o ícone e o texto.
     - `margin-bottom` para espaçamento abaixo do botão.

   ```css
   & .back {
       display: flex;
       align-items: center;
       gap: .5rem;
       margin-bottom: 1.5rem;
   }
   ```

2. **Estilos para o Título (`h1`)**:
   - Adicionado estilo para o título do formulário com:
     - Fonte semibold (`600`) e tamanho `1.5rem`.
     - `margin-bottom` para espaçamento abaixo do título.

   ```css
   & h1 {
       font: 600 1.5rem/1.25 var(--font-family);
       margin-bottom: .5rem;
   }
   ```

3. **Estilos para a Imagem no Container Lateral**:
   - Adicionado `margin-top` para espaçamento acima da imagem.

   ```css
   & > img {
       margin-top: 2rem;
   }
   ```

4. **Estilos para o Título (`h2`) no Container Lateral**:
   - Adicionado estilo para o título do container lateral com:
     - Fonte semibold (`600`) e tamanho `2.5rem`.
     - `margin-bottom` para espaçamento abaixo do título.
     - Um `span` com cor destacada (`--text-highlight`).

   ```css
   & h2 {
       font: 600 2.5rem/1.25 var(--font-family);
       margin-bottom: .5rem;
   }
   & span {
       color: var(--text-highlight);
   }
   ```

---

## Alterações no `global.css`

1. **Estilos Globais para o `body`**:
   - Adicionado `overflow: hidden` para ocultar a barra de rolagem e evitar transbordamento.

   ```css
   body {
       overflow: hidden;
       font: var(--text);
       color: var(--text-secondary);
   }
   ```

2. **Estilos Globais para Imagens (`img`)**:
   - Garantido que as imagens não ultrapassem o tamanho do container com `max-width: 100%` e `height: auto`.

   ```css
   img {
       max-width: 100%;
       height: auto;
   }
   ```

3. **Estilos Globais para Títulos (`h1`, `h2`)**:
   - Definido estilo padrão para títulos com a variável `--text-xxl` e cor primária (`--text-primary`).

   ```css
   h1, h2 {
       font: var(--text-xxl);
       color: var(--text-primary);
   }
   ```

---

## Resumo das Mudanças

- **HTML**:
  - Adicionada estrutura para o container principal e lateral.
  - Incluídos elementos como botão de voltar, títulos, parágrafos e imagens.

- **CSS**:
  - Estilização do botão de voltar, títulos e imagens.
  - Definição de estilos globais para o corpo da página, imagens e títulos.

Essas alterações ajudaram a organizar o layout da página e a preparar a base para a estilização futura. 🚀

