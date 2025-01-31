# Stage 02: Configuração de Assets e Variáveis

## 1. Adicionar Imagens e Ícones

Baixe ou exporte todos os assets necessários para o projeto.

> No **Figma**, utilizei o **Style Guide** para exportar as imagens e ícones para o diretório:
>
> `assets/images/` e `assets/icons/`

### 2. Definir Variáveis Globais

No arquivo `global.css`, adicione o seletor `:root { }` contendo as variáveis principais do projeto:

```css
:root {
  --font-family: 'Poppins', sans-serif;
  --text: 400 1rem/1.5 var(--font-family); 
  --text-color: #fff; 
}
```

### 3. Importar `global.css` no `styles.css`

No início do arquivo `styles.css`, importe o `global.css`:

```css
@import url('global.css');
```

### 4. Criar a Estrutura Base no `index.html`

No `index.html`, defina a estrutura base do documento e adicione a fonte escolhida via **Google Fonts**.

### Métodos para importar a fonte

* **Diretamente no CSS:**

  ```css
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;700&display=swap');
  ```

* **No HTML (recomendado para melhor performance):**

  ```html
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;700&display=swap" rel="stylesheet">
  ```

### 5. Adicionar Alterações ao Stage e Realizar o Commit

Adicione os arquivos ao **stage** e faça o commit:

```sh
git add .
git commit -m "Configuração de assets, variáveis e estrutura base do HTML"
```

---
