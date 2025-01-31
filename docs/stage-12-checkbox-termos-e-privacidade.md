# Stage 12: Refatoração do Checkbox de Aceitação dos Termos e Privacidade

Neste estágio, foi refatorada a estrutura e a estilização do checkbox de aceitação dos termos e condições, além da política de privacidade. Abaixo estão as alterações detalhadas:

---

## Alterações no HTML

1. **Refatoração do Checkbox**:
   - O checkbox foi reorganizado para melhorar a semântica e a acessibilidade.
   - Adicionado um `div` com a classe `checkbox-image` para exibir o ícone personalizado do checkbox.
   - O texto do label foi aprimorado com a utilização da tag `<strong>` para destacar os termos importantes.

   - Estrutura do checkbox:

     ```html
     <div class="terms-wrapper input-wrapper checkbox-wrapper">
         <div class="checkbox-image"></div>
         <input type="checkbox" id="terms" name="terms">
         <label for="terms">Declaro que li e concordo com os 
             <strong>Termos e Condições</strong> 
             e com a 
             <strong>Política de Privacidade</strong> 
             da escola Estrela do Amanhã.
         </label>
     </div>
     ```

---

## Alterações no CSS

1. **Criação do Arquivo `checkbox.css`**:
   - Foi criado um novo arquivo `checkbox.css` para centralizar os estilos do checkbox.
   - Estilos aplicados:
     - **Layout do Checkbox**:
       - Utilização de flexbox para alinhar o ícone e o texto.
       - Espaçamento entre o ícone e o texto.
     - **Estilização do Texto**:
       - Destaque dos termos importantes com a tag `<strong>`.
     - **Estilização do Ícone**:
       - Ícones personalizados para os estados default, hover e selecionado.

   - Exemplo:

     ```css
     .terms-wrapper {
         margin-top: 3rem;
         display: flex;
         gap: 0.75rem;
         align-items: flex-start;
     }

     .terms-wrapper strong {
         font-weight: 500;
         color: var(--text-highlight);
     }

     .checkbox-wrapper {
         position: relative;
     }

     .checkbox-wrapper [type="checkbox"] {
         all: unset;
         position: absolute;
         inset: 0;
     }

     .checkbox-wrapper .checkbox-image {
         flex: 0 0 1.5rem;
         height: 1.5rem;
         background-image: url('../../assets/icons/checkbox-default.svg');
     }

     .checkbox-wrapper:hover,
     .checkbox-wrapper:focus-within {
         .checkbox-image {
             background-image: url('../../assets/icons/checkbox-hover.svg');
         }
     }

     .checkbox-wrapper:has(:checked) .checkbox-image {
         background-image: url('../../assets/icons/checkbox-selected.svg');
     }
     ```

2. **Importação do `checkbox.css` no `index.css`**:
   - O arquivo `checkbox.css` foi importado no `index.css` para garantir a aplicação dos estilos.
   - Exemplo:

     ```css
     @import url('checkbox.css');
     ```

---

## Resumo das Mudanças

- **HTML**:
  - Refatoração do checkbox de aceitação dos termos e condições.
  - Adicionado ícone personalizado e texto destacado.

- **CSS**:
  - Criação do arquivo `checkbox.css` para centralizar os estilos do checkbox.
  - Estilização dos estados default, hover e selecionado do checkbox.
