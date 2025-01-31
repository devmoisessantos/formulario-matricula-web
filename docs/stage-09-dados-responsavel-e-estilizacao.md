# Stage 09: Adição do Fieldset de Informações do Responsável e Validação de E-mail

Neste estágio, foi adicionado um novo campo de informações do responsável e implementada a validação de e-mail. Abaixo estão as alterações detalhadas:

---

## Alterações no HTML

1. **Adição do Fieldset de Informações do Responsável**:
   - Foi criado um novo `<fieldset>` com a classe `info-responsible` para agrupar os campos relacionados ao responsável.
   - Os campos incluem:
     - **Nome do Responsável**: Campo de texto para inserir o nome do responsável.
     - **Telefone**: Campo numérico para inserir o telefone de contato.
     - **E-mail**: Campo de e-mail com validação e mensagem de erro.
   - Estrutura do fieldset:

     ```html
     <fieldset class="info-responsible">
         <legend>Informações do responsável</legend>

         <div class="input-wrapper">
             <label for="responsible">Nome do responsável</label>
             <input type="text" id="responsible" name="responsible">
             <small>Principal responsável legal e contato de emergência</small>
         </div>

         <div class="input-wrapper">
             <label for="phone">Telefone</label>
             <input type="number" id="phone" name="phone" placeholder="(11) 99876-1234" />
         </div>

         <div class="input-wrapper">
             <label for="email">E-mail</label>
             <input type="email" id="email" name="email" required>
             <div class="error">
                 <img src="assets/icons/alert-circle.svg" alt="Icone de alerta">
                 <span>Insira um e-mail válido</span>
             </div>
         </div>
     </fieldset>
     ```

---

## Alterações no CSS

1. **Estilização do Texto de Ajuda (`small`)**:
   - Adicionado estilos para o texto de ajuda (`<small>`) que aparece abaixo do campo de nome do responsável.
   - Exemplo:

     ```css
     input + small {
         font: var(--text-sm);
         color: #78716c;
         display: inline-block;
         margin-top: .25rem;
     }
     ```

2. **Validação de E-mail**:
   - Adicionado estilos para a mensagem de erro de validação de e-mail:
     - Exibição flexível com ícone e texto.
     - Cor definida pela variável `--semantic-error`.
     - Ocultação da mensagem de erro quando o campo é válido.
   - Exemplo:

     ```css
     input[required] + .error {
         display: flex;
         align-items: center;
         gap: .25rem;
         font: var(--text-sm);
         color: var(--semantic-error);
         margin-top: .25rem;
     }

     input:valid + .error {
         display: none;
     }

     input:not(:focus):valid + .error {
         display: none;
     }

     input:not(:focus):invalid + .error {
         border: 0.125rem solid var(--semantic-error);
         display: none;
     }
     ```

---

## Resumo das Mudanças

- **HTML**:
  - Adicionado um novo fieldset para as informações do responsável.
  - Incluídos campos para nome, telefone e e-mail.
  - Adicionada mensagem de erro para validação de e-mail.

- **CSS**:
  - Estilização do texto de ajuda abaixo do campo de nome do responsável.
  - Implementação da validação de e-mail com mensagem de erro personalizada.
