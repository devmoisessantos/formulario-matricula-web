# Stage 08: Adição do Fieldset de Endereço e Ajustes de Estilo

Neste estágio, foi adicionado um novo campo de endereço ao formulário e realizados ajustes de estilo para melhorar a usabilidade e a aparência. Abaixo estão as alterações detalhadas:

---

## Alterações no HTML

1. **Adição do Fieldset de Endereço**:
   - Foi criado um novo `<fieldset>` com a classe `address` para agrupar os campos relacionados ao endereço residencial.
   - Os campos incluem:
     - **CEP**: Campo de texto para inserir o CEP.
     - **Rua**: Campo de texto pré-preenchido e desabilitado.
     - **Número**: Campo numérico para inserir o número da residência.
     - **Cidade**: Campo de texto pré-preenchido e desabilitado.
     - **Estado**: Campo de texto pré-preenchido e desabilitado.
   - Estrutura do fieldset:

     ```html
     <fieldset class="address">
         <legend>Endereço residencial</legend>

         <div class="input-wrapper">
             <label for="cep">CEP</label>
             <input type="text" id="cep" name="cep">
         </div>

         <div class="flex">
             <div class="input-wrapper flex-2">
                 <label for="street">Rua</label>
                 <input type="text" id="street" name="street" value="Rua das Flores" disabled />
             </div>

             <div class="input-wrapper flex-1">
                 <label for="number">Número</label>
                 <input type="number" id="number" name="number" />
             </div>
         </div>

         <div class="flex">
             <div class="input-wrapper flex-2">
                 <label for="city">Cidade</label>
                 <input type="text" id="city" name="city" value="São Paulo" disabled />
             </div>

             <div class="input-wrapper flex-1">
                 <label for="state">Estado</label>
                 <input type="text" id="state" name="state" value="SP" disabled />
             </div>
         </div>
     </fieldset>
     ```

---

## Alterações no CSS

1. **Ajustes no Espaçamento entre Fieldsets**:
   - Adicionado um espaçamento superior de `3rem` entre fieldsets para melhorar a organização visual.
   - Exemplo:

     ```css
     fieldset + fieldset {
         margin-top: 3rem;
     }
     ```

2. **Ajustes no Padding do Dropzone**:
   - O padding do `.dropzone` foi alterado para `1.75rem 1rem` para melhorar o espaçamento interno.
   - Exemplo:

     ```css
     .dropzone {
         padding: 1.75rem 1rem;
     }
     ```

3. **Estilização do Layout Flexível**:
   - Adicionado um espaçamento (`gap`) de `1.25rem` entre os elementos flexíveis dentro do fieldset de endereço.
   - Exemplo:

     ```css
     .address .flex {
         gap: 1.25rem;
     }
     ```

4. **Estilização de Campos Desabilitados**:
   - Campos desabilitados (`disabled`) receberam estilos específicos para indicar visualmente que estão inativos:
     - Redução da opacidade para 50%.
     - Cor de fundo definida pela variável `--surface-disabled`.
     - Manutenção da cor do texto e da borda para consistência visual.
   - Exemplo:

     ```css
     .input-wrapper:has([disabled]) {
         opacity: .5;
     }

     input[disabled] {
         background-color: var(--surface-disabled);
         border: 1px solid var(--stroke-default);
         color: var(--text-primary);
     }
     ```

---

## Resumo das Mudanças

- **HTML**:
  - Adicionado um novo fieldset para o endereço residencial.
  - Incluídos campos para CEP, rua, número, cidade e estado.

- **CSS**:
  - Ajustes de espaçamento entre fieldsets e dentro do dropzone.
  - Estilização de campos desabilitados para melhorar a usabilidade.
  - Melhoria no layout flexível do fieldset de endereço.
