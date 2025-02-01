# Stage 13: Adição dos Botões de Ação e Estilização

Neste estágio, foram adicionados os botões de ação ao formulário e realizada a estilização dos mesmos. Abaixo estão as alterações detalhadas:

---

## Alterações no HTML

1. **Adição dos Botões de Ação**:
   - Foram adicionados dois botões dentro de um container com a classe `actions-wrapper`:
     - **Salvar Respostas**: Botão secundário para salvar as respostas sem enviar o formulário.
     - **Fazer Matrícula**: Botão primário para enviar o formulário e finalizar a matrícula.

   - Estrutura dos botões:

     ```html
     <div class="actions-wrapper">
         <button class="btn-primary" type="button">
             Salvar respostas
         </button>
         <button class="btn-secondary" type="submit">
             Fazer matrícula
         </button>
     </div>
     ```

---

## Alterações no CSS

1. **Estilização do Container dos Botões**:
   - Adicionado margem superior e layout flexível para organizar os botões.
   - Exemplo:

     ```css
     .actions-wrapper {
         margin-top: 3rem;
         display: flex;
         gap: 1rem;
     }
     ```

2. **Criação do Arquivo `buttons.css`**:
   - Foi criado um novo arquivo `buttons.css` para centralizar os estilos dos botões.
   - Estilos aplicados:
     - **Estilização Geral dos Botões**:
       - Remoção da aparência padrão (`all: unset`).
       - Fonte semibold (`font-weight: 500`).
       - Cores e bordas definidas pelas variáveis do projeto.
       - Padding interno e bordas arredondadas.
       - Cursor pointer para indicar que os botões são clicáveis.
     - **Estilização do Botão Primário**:
       - Cor do texto e borda definidas pela variável `--text-highlight`.
       - Efeitos de hover e foco para melhorar a interação do usuário.
     - **Estilização do Botão Secundário**:
       - Cor do texto branca e fundo definido pela variável `--brand-dark`.
       - Efeitos de hover e foco para melhorar a interação do usuário.

   - Exemplo:

     ```css
     button {
         all: unset;
         font-weight: 500;
         color: var(--text-highlight);
         padding: .75rem 1.5rem;
         border-radius: .5rem;
         cursor: pointer;
     }

     button.btn-primary {
         margin-left: auto;
         border: 1px solid var(--text-highlight);
     }

     button.btn-primary:hover,
     button.btn-primary:focus {
         color: var(--brand-dark);
         outline: .25rem solid var(--surface-secondary);
     }

     button.btn-secondary {
         color: white;
         background-color: var(--brand-dark);
     }

     button.btn-secondary:hover,
     button.btn-secondary:focus {
         background-color: var(--brand-mid);
     }
     ```

3. **Importação do `buttons.css` no `index.css`**:
   - O arquivo `buttons.css` foi importado no `index.css` para garantir a aplicação dos estilos.
   - Exemplo:

     ```css
     @import url('buttons.css');
     ```

---

## Resumo das Mudanças

- **HTML**:
  - Adicionado container com os botões de ação.
  - Incluídos botões para salvar respostas e fazer matrícula.

- **CSS**:
  - Criação do arquivo `buttons.css` para centralizar os estilos dos botões.
  - Estilização dos botões primário e secundário.
  - Importação do arquivo `buttons.css` no `index.css`.
