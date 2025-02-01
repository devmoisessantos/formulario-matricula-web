# Stage 15: Correção do Shift Layout no Dropzone e Inputs

Neste estágio, foi corrigido o **shift layout** que ocorria no **dropzone** e nos **inputs** devido à mudança de bordas e outlines. Abaixo estão as alterações detalhadas, incluindo o **antes** e o **depois**.

---

## **Antes da Correção**

### **Problemas Identificados**

1. **Dropzone**:
   - A mudança de borda (`border-width`) ao passar o mouse ou focar causava um deslocamento no layout.
   - Exemplo:

     ```css
     .dropzone:hover,
     .dropzone:has(input:focus) {
         border-color: var(--stroke-highlight);
         border-width: 2px; /* Causava shift layout */
         background-color: var(--surface-secondary);
     }
     ```

2. **Inputs**:
   - A mudança de borda (`border`) ao focar causava um deslocamento no layout.
   - Exemplo:

     ```css
     input:focus, textarea:focus, select:focus, input[type="date"]:focus-within {
         outline: .25rem solid var(--surface-secondary);
         border: .125rem solid var(--stroke-highlight); /* Causava shift layout */
     }
     ```

---

## **Depois da Correção**

### **Alterações Realizadas**

1. **Dropzone**:
   - Substituído o uso de `border` por `outline` para evitar o shift layout.
   - Adicionado `outline-width: 0` no estado de hover/focus para garantir consistência visual.
   - Exemplo:

     ```css
     .dropzone {
         border: 2px dashed transparent;
         outline: 1px dashed var(--stroke-default);
         border-radius: 0.25rem;
     }

     .dropzone:hover,
     .dropzone:has(input:focus) {
         outline-width: 0;
         border-color: var(--stroke-highlight);
         background-color: var(--surface-secondary);
     }
     ```

2. **Inputs**:
   - Substituído o uso de `border` por `outline` para evitar o shift layout.
   - Mantido o `border-color` para destacar o foco sem causar deslocamento.
   - Exemplo:

     ```css
     input, textarea, select {
         border: 2px solid transparent;
         outline: 1px solid var(--stroke-default);
     }

     input:focus, textarea:focus, select:focus, input[type="date"]:focus-within {
         outline: .25rem solid var(--surface-secondary);
         border-color: var(--stroke-highlight); /* Mantém o destaque sem shift */
     }
     ```

---

## **Resumo das Mudanças**

- **Dropzone**:
  - Substituído `border` por `outline` para evitar shift layout.
  - Adicionado `outline-width: 0` no estado de hover/focus.

- **Inputs**:
  - Substituído `border` por `outline` para evitar shift layout.
  - Mantido `border-color` para destacar o foco sem causar deslocamento.
