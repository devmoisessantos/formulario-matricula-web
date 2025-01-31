# Stage 06: Estilizando o Formulário (Parte I)

Neste estágio, iniciamos a estilização do formulário de matrícula, focando na aparência dos campos de entrada (`input`, `textarea`, `select`) e na organização do layout. Abaixo estão as alterações realizadas:

---

## Estrutura de Arquivos

1. **Criação da Pasta `fields`**:
   - Foi criada uma pasta chamada `fields` para organizar os estilos relacionados aos campos do formulário.
   - Dentro dela, foi adicionado o arquivo `index.css`, que contém os estilos específicos para `input`, `textarea`, `select` e `label`.

2. **Criação do Arquivo `form.css`**:
   - Na pasta `css`, foi criado o arquivo `form.css`, que importa os estilos da pasta `fields` e adiciona estilos para o formulário e seus containers.

3. **Importação no `styles.css`**:
   - O arquivo `form.css` foi importado no `styles.css` para garantir que os estilos sejam aplicados globalmente.

---

## Alterações no CSS

### **Arquivo `fields/index.css`**

1. **Estilização Geral dos Campos**:
   - Aplicado estilos globais para `input`, `textarea` e `select`:
     - `appearance: none` para remover estilos padrão do navegador.
     - Largura de 100% (`width: 100%`).
     - Bordas arredondadas (`border-radius: 0.5rem`).
     - Bordas com cor definida pela variável `--stroke-default`.
     - Padding interno de `0.75rem 1rem`.
     - Fonte definida pela variável `--text`.

   ```css
   input, textarea, select {
       appearance: none;
       width: 100%;
       border-radius: 0.5rem;
       border: 1px solid var(--stroke-default);
       padding: 0.75rem 1rem;
       font: var(--text);
   }
   ```

2. **Estilização dos Labels**:
   - Aplicado estilos para `label`:
     - Fonte definida pela variável `--text-sm`.
     - Cor do texto definida pela variável `--text-secondary`.
     - Exibição em bloco (`display: block`).
     - Margem inferior de `0.25rem`.

   ```css
   label {
       font: var(--text-sm);
       color: var(--text-secondary);
       display: block;
       margin-bottom: 0.25rem;
   }
   ```

3. **Estilização do Estado de Foco**:
   - Adicionado estilos para o estado de foco (`:focus`) dos campos:
     - `outline-offset` e `outline` para destacar o campo.
     - Borda com cor definida pela variável `--stroke-highlight`.

   ```css
   input:focus, textarea:focus, select:focus {
       outline-offset: .1px;
       outline: .25rem solid var(--surface-secondary);
       border: .125rem solid var(--stroke-highlight);
   }
   ```

4. **Estilização do Campo de Data (`input[type="date"]`)**:
   - Personalizado o campo de data:
     - Removido o ícone padrão do calendário (`::-webkit-calendar-picker-indicator`).
     - Adicionado um ícone personalizado usando `::before`.

   ```css
   input[type="date"] {
       position: relative;
   }

   input[type="date"]::-webkit-calendar-picker-indicator {
       opacity: 0;
   }

   input[type="date"]::before {
       content: '';
       width: 1.25rem;
       height: 1.25rem;
       position: absolute;
       background: url(../../assets/icons/calendar-03.svg) center/contain;
       right: 1rem;
       top: 50%;
       transform: translateY(-50%);
   }
   ```

5. **Estilização do Campo de Seleção (`select`)**:
   - Adicionado um ícone de seta personalizado ao campo de seleção.

   ```css
   select {
       background: url(../../assets/icons/arrow-down-01.svg) no-repeat right .75rem center;
   }
   ```

---

### **Arquivo `form.css`**

1. **Importação dos Estilos dos Campos**:
   - Importado o arquivo `fields/index.css` para aplicar os estilos dos campos.

   ```css
   @import url('fields/index.css');
   ```

2. **Estilização do Formulário**:
   - Adicionado margem superior de `3rem` ao formulário.

   ```css
   form {
       margin-top: 3rem;
   }
   ```

3. **Estilização do Fieldset**:
   - Removido bordas padrão do `fieldset`.
   - Organizado os campos em um layout de grid com espaçamento de `1.5rem`.

   ```css
   fieldset {
       border: none;
       display: grid;
       gap: 1.5rem;
   }
   ```

4. **Estilização da Legenda (`legend`)**:
   - Aplicado estilos para a legenda do `fieldset`:
     - Fonte semibold (`600`) com tamanho `1rem` e altura de linha `1.25`.
     - Margem inferior de `1.5rem`.

   ```css
   legend {
       font: 600 1rem/1.25 var(--font-family);
       margin-bottom: 1.5rem;
   }
   ```

---

## Resultado Visual

Após as alterações, o formulário deve ter:

- Campos de entrada com aparência uniforme e moderna.
- Ícones personalizados para campos de data e seleção.
- Destaque visual ao focar nos campos.
- Layout organizado e espaçado.

---

## Próximos Passos

- **Parte II da Estilização**:
  - Adicionar estilos para a área de upload de arquivos.
  - Melhorar a responsividade do formulário.

- **Validações**:
  - Adicionar feedback visual para campos inválidos.
