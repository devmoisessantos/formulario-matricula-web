# Stage 03: Definição de Layout e Organização do Código

## 1. Ajustes no `global.css`

Foram adicionadas variáveis de **tipografia**, **cores** e **comportamento do body** para padronizar o estilo do projeto.

### Alterações realizadas

* Reset básico de margens, preenchimentos e `box-sizing`.
* Ajuste de `overflow` no `body` para ocultar a barra de rolagem.
* Aplicação de variáveis de fonte nos títulos e parágrafos.

### Código atualizado (`global.css`)

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box; 
}

:root {
  --font-family: 'Poppins', sans-serif;

  /* Textos normais */
  --text: 400 1rem/1.2 var(--font-family);
  --text-lg: 400 1.125rem/1.2 var(--font-family);

  /* Headings */
  --text-xl: 700 1.25rem/1.2 var(--font-family);
  --text-xxl: 700 2rem/1.2 var(--font-family);

  /* Cores de Brand */
  --brand-light: #f67841;
  --brand-mid: #f3541c;
  --brand-dark: #e43a12;

  /* Cores de Texto */
  --text-primary: #292524;
  --text-secondary: #57534e;
  --text-tertiary: #8f8881;
  --text-highlight: #e43a12;

  /* Surface */
  --surface-primary: #fff;
  --surface-secondary: #FEE7D6;   
  --surface-disabled: #e7e5e4;

  /* Stroke */
  --stroke-default: #d6d3d1;
  --stroke-highlight: #f3541c;

  /* Semantics */
  --semantic-error: #dc2626;
}

body {
  overflow: hidden; /* Oculta a barra de rolagem */
}

h1, h2 {
  font: var(--text-xxl);
}

h3 {
  font: var(--text-xl);
}

h4 {
  font: var(--text-lg);
}

p {
  font: var(--text);
}
```

### 2. Criando o `layout.css`

Foi criado o arquivo `layout.css` para definir o **layout base** do projeto utilizando **CSS Grid**.

### Código (`layout.css`)

```css
#app {
    display: grid;
    grid-template-columns: 51.25% 48.75%;
    height: 100vh;
    overflow: hidden;
}

main {
  overflow: auto;
  padding: 4rem;
}

aside {
  background-color: var(--surface-secondary);
  padding: 4rem;
}

.main-container {
  max-width: 33rem;
  margin-left: auto;
}

.aside-container {
  max-width: 31rem;
}
```

### 3. Importação no `styles.css`

No `styles.css`, foi importado o `layout.css` para manter a organização do código.

```css
@import url('layout.css');
```

### 4. Estruturação do `index.html`

O HTML foi atualizado para seguir a nova estrutura, utilizando **`<main>`** e **`<aside>`** para organizar os blocos de conteúdo.

### Código atualizado (`index.html`)

```html
<div id="app">
    <main>
        <div class="main-container">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Quaerat, aperiam eos quam error libero ex, nobis nulla alias reiciendis deserunt non architecto odio quod suscipit, quia quisquam modi sunt quidem.
        </div>
    </main>

    <aside>
        <div class="aside-container">
            Lorem ipsum dolor sit, amet consectetur adipisicing elit. Assumenda illum minima, voluptatum omnis autem cupiditate iusto beatae dolores recusandae laborum neque reiciendis odio aperiam, minus eos quam eligendi eaque et.
        </div>
    </aside>
</div>
```

### 5. Adicionar Alterações ao Stage e Realizar o Commit

Após realizar as mudanças, adicione ao **stage** e faça o commit:

```sh
git add .
git commit -m "Definição do layout base e organização do CSS"
```

---
