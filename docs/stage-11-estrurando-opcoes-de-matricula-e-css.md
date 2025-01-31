# Stage 11: Refatoração e Estilização dos Inputs e Radio Buttons

Neste estágio, foram realizadas refatorações e melhorias na estilização dos inputs e radio buttons, além da organização do código CSS em arquivos separados para melhor manutenção. Abaixo estão as alterações detalhadas:

---

## Alterações no CSS

1. **Criação do Arquivo `radio.css`**:
   - Foi criado um novo arquivo `radio.css` para centralizar os estilos dos radio buttons.
   - Estilos aplicados:
     - **Layout dos Radio Buttons**:
       - Utilização de grid para organizar os radio buttons em colunas.
       - Espaçamento entre os radio buttons.
     - **Estilização dos Radio Buttons**:
       - Bordas arredondadas e cores definidas pelas variáveis do projeto.
       - Efeitos de hover e foco para melhorar a interação do usuário.
       - Ícones personalizados para indicar o estado do radio button (default, hover e selecionado).

   - Exemplo:

     ```css
     label + .radio-wrapper {
         margin-top: 1rem;
     }

     .radio-wrapper {
         display: grid;
         grid-template-columns: repeat(auto-fit, minmax(7.5rem, 1fr));
         gap: 1rem;
     }

     .radio-inner {
         border: 1px solid var(--stroke-default);
         border-radius: 0.5rem;
         display: grid;
         justify-items: center;
         gap: .5rem;
         padding: 2rem .5rem .5rem;
         position: relative;
     }

     .radio-inner input,
     .radio-inner input:focus,
     .radio-inner input:hover {
         all: unset;
         position: absolute;
         inset: 0;
     }

     .radio-inner .radio-image {
         background-image: url(../../assets/icons/radio-default.svg);
         width: 1.5rem;
         height: 1.5rem;
         position: absolute;
         top: 0.5rem;
         left: 0.5rem;
     }

     .radio-inner:hover,
     .radio-inner:focus-within {
         border: 1px solid var(--stroke-highlight);
     }

     .radio-inner:hover .radio-image,
     .radio-inner:focus-within .radio-image {
         background-image: url(../../assets/icons/radio-hover.svg);
     }

     .radio-inner:has(:checked) {
         border: 2px solid var(--stroke-highlight);
     }

     .radio-inner:has(:checked) .radio-image {
         background-image: url(../../assets/icons/radio-selected.svg);
     }
     ```

2. **Criação do Arquivo `input.css`**:
   - Foi criado um novo arquivo `input.css` para centralizar os estilos dos inputs.
   - Estilos aplicados:
     - **Estilização Geral dos Inputs**:
       - Remoção da aparência padrão (`appearance: none`).
       - Bordas arredondadas e cores definidas pelas variáveis do projeto.
       - Padding interno para melhorar a usabilidade.
     - **Estilização de Campos Desabilitados**:
       - Redução da opacidade e cor de fundo específica.
     - **Validação de Campos**:
       - Mensagem de erro para campos inválidos.

   - Exemplo:

     ```css
     input, textarea, select {
         appearance: none;
         width: 100%;
         border-radius: 0.5rem;
         border: 1px solid var(--stroke-default);
         padding: 0.75rem 1rem;
         font: var(--text);
     }

     label {
         font: var(--text-sm);
         color: var(--text-secondary);
         display: block;
         margin-bottom: 0.25rem;
     }

     input:focus, textarea:focus, select:focus, input[type="date"]:focus-within {
         outline-offset: .1px;
         outline: .25rem solid var(--surface-secondary);
         border: .125rem solid var(--stroke-highlight);
     }

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

     select {
         background: url(../../assets/icons/arrow-down-01.svg) no-repeat right .75rem center;
     }

     .address .flex {
         gap: 1.25rem;
     }

     .input-wrapper:has([disabled]) {
         opacity: .5;
     }

     input[disabled] {
         background-color: var(--surface-disabled);
         border: 1px solid var(--stroke-default);
         color: var(--text-primary);
     }

     input + small {
         font: var(--text-sm);
         color: #78716c;
         display: inline-block;
         margin-top: .25rem;
     }

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

3. **Atualização do `index.css`**:
   - Foram importados os novos arquivos `input.css`, `drop-area.css` e `radio.css` no `index.css` para garantir a aplicação dos estilos.
   - Exemplo:

     ```css
     @import url('input.css');
     @import url('drop-area.css');
     @import url('radio.css');
     ```

---

## Alterações no HTML

1. **Refatoração do Fieldset de Opções de Matrícula**:
   - Adicionado a estrutura de radio buttons para a seleção de turno de estudo e esportes.
   - Utilização da classe `radio-inner` para estilização personalizada dos radio buttons.
   - Exemplo:

     ```html
     <fieldset class="enroll-options">
         <legend>Opções de matrícula</legend>
         <div class="input-wrapper">
             <label>Selecione o turno de estudo</label>
             <div class="radio-wrapper">
                 <div class="radio-inner">
                     <div class="radio-image"></div>
                     <input type="radio" id="morning" name="study-shift" value="morning">
                     <img src="assets/icons/sun-cloud-02.svg" alt="Ilustração de um sol com nuvens">
                     <label for="morning">Manhã</label>
                 </div>
                 <div class="radio-inner">
                     <div class="radio-image"></div>
                     <input type="radio" id="afternoon" name="study-shift" value="afternoon">
                     <img src="assets/icons/sun-02.svg" alt="Ilustração de um sol">
                     <label for="afternoon">Tarde</label>
                 </div>
             </div>
         </div>
         <div class="input-wrapper">
             <label>Em qual esporte você gostaria de inscrever seu filho?</label>
             <div class="radio-wrapper">
                 <div class="radio-inner">
                     <div class="radio-image"></div>
                     <input type="radio" id="futebol" name="sport" value="futebol">
                     <img src="assets/icons/football.svg" alt="Ilustração de um jogador de futebol">
                     <label for="futebol">Futebol</label>
                 </div>
                 <!-- Repetir estrutura para outros esportes -->
             </div>
         </div>
     </fieldset>
     ```

---

## Resumo das Mudanças

- **CSS**:
  - Criação dos arquivos `radio.css` e `input.css` para organizar os estilos dos radio buttons e inputs.
  - Importação dos novos arquivos no `index.css`.

- **HTML**:
  - Refatoração do fieldset de opções de matrícula para utilizar a nova estrutura de radio buttons.
