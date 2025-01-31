# Stage 10: Adição do Fieldset de Opções de Matrícula

Neste estágio, foi adicionado um novo campo de opções de matrícula, incluindo a seleção de turno de estudo, esportes e termos de aceitação. Abaixo estão as alterações detalhadas:

---

## Alterações no HTML

1. **Adição do Fieldset de Opções de Matrícula**:
   - Foi criado um novo `<fieldset>` com a classe `enroll-options` para agrupar as opções de matrícula.
   - Os campos incluem:
     - **Turno de Estudo**: Seleção de turno (manhã ou tarde) com ícones ilustrativos.
     - **Esportes**: Lista de esportes disponíveis para inscrição, cada um com um ícone ilustrativo.
     - **Termos e Condições**: Checkbox para aceitar os termos e condições da escola.

   - Estrutura do fieldset:

     ```html
     <fieldset class="enroll-options">
         <legend>Opções de matrícula</legend>

         <!-- Seleção de Turno de Estudo -->
         <div class="input-wrapper">
             <label>Selecione o turno de estudo</label>
             <div class="radio-wrapper">
                 <div class="radio-inner">
                     <div class="radio-image">
                         <input type="radio" id="morning" name="study-shift" value="morning">
                         <img src="assets/icons/sun-cloud-02.svg" alt="Ilustração de um sol com nuvens">
                         <label for="morning">Manhã</label>
                     </div>
                 </div>

                 <div class="radio-inner">
                     <div class="radio-image">
                         <input type="radio" id="afternoon" name="study-shift" value="afternoon">
                         <img src="assets/icons/sun-02.svg" alt="Ilustração de um sol">
                         <label for="afternoon">Tarde</label>
                     </div>
                 </div>
             </div>
         </div>

         <!-- Seleção de Esportes -->
         <div class="input-wrapper">
             <label>Em qual esporte você gostaria de inscrever seu filho?</label>
             <div class="input-wrapper">
                 <label value="morning">Futebol</label>
                 <img src="assets/icons/football.svg" alt="Ilustração de um jogador de futebol">
                 <label value="afternoon">Basquete</label>
                 <img src="assets/icons/basketball-02.svg" alt="Ilustração de um jogador de basquete">
                 <label value="morning">Natação</label>
                 <img src="assets/icons/swimming.svg" alt="Ilustração de um jogador de volei">
                 <label value="morning">Yoga</label>
                 <img src="assets/icons/yoga-02.svg" alt="Ilustração de um jogador de volei">
                 <label value="morning">Volei</label>
                 <img src="assets/icons/volleyball.svg" alt="Ilustração de um jogador de volei">
                 <label value="morning">Boxe</label>
                 <img src="assets/icons/boxing-glove-01.svg" alt="Ilustração de um jogador de volei">
             </div>
         </div>

         <!-- Termos e Condições -->
         <div class="terms">
             <input type="checkbox" id="terms" name="terms">
             <h4>Declaro que li e concordo com os <span>Termos e Condições</span> e com a <span>Política de Privacidade</span> da escola Estrela do Amanhã.</h4>
         </div>
     </fieldset>
     ```

---

## Resumo das Mudanças

- **HTML**:
  - Adicionado um novo fieldset para as opções de matrícula.
  - Incluída seleção de turno de estudo com ícones ilustrativos.
  - Adicionada lista de esportes disponíveis para inscrição, cada um com um ícone ilustrativo.
  - Implementado checkbox para aceitar os termos e condições da escola.
