# Stage 05: Estrutura do Formulário de Matrícula

Neste estágio, foi iniciada a construção do formulário de matrícula, com foco na estrutura HTML. Abaixo estão as alterações realizadas:

---

## Alterações no HTML

1. **Estrutura do Formulário**:
   - Adicionado um formulário (`<form>`) com o método `POST` e suporte para upload de arquivos (`enctype="multipart/form-data"`).
   - O formulário está organizado em um `<fieldset>` com a legenda "Informações da criança".

   ```html
   <form action="" method="post" enctype="multipart/form-data">
       <fieldset class="child-info">
           <legend>Informações da criança</legend>
   ```

2. **Campo de Nome Completo**:
   - Adicionado um campo de texto para o nome completo da criança.
   - Inclui um `label` e um `input` com um placeholder para orientar o usuário.

   ```html
   <div class="input-wrapper">
       <label for="fullname">Nome completo</label>
       <input id="fullname" type="text" placeholder="Qual o nome da criança">
   </div>
   ```

3. **Campo de Data de Nascimento**:
   - Adicionado um campo de data (`<input type="date">`) para a data de nascimento da criança.
   - O campo está configurado para o idioma português do Brasil (`lang="pt-BR"`).

   ```html
   <div class="input-wrapper">
       <label for="birth">Data de nascimento</label>
       <input id="birth" type="date" name="birth" lang="pt-BR">
   </div>
   ```

4. **Campo de Seleção de Sexo**:
   - Adicionado um campo de seleção (`<select>`) para o sexo da criança.
   - As opções incluem "Masculino", "Feminino" e "Prefiro não informar".

   ```html
   <div class="select-wrapper">
       <label for="gender">Sexo</label>
       <select name="gender" id="gender">
           <option value="male">Masculino</option>
           <option value="female">Feminino</option>
           <option value="na">Prefiro não informar</option>
       </select>
   </div>
   ```

5. **Campo de Informações Médicas**:
   - Adicionado um campo de texto longo (`<textarea>`) para informações médicas.
   - O campo inclui um placeholder para orientar o usuário.

   ```html
   <div class="textarea-wrapper">
       <label for="medical-info">Informações Medicas</label>
       <textarea name="medical-info" id="medical-info" cols="30" rows="10"
           placeholder="A criança possui alguma condição médica que a escola deve estar ciente? Informe aqui."></textarea>
   </div>
   ```

6. **Campo de Upload de Arquivos**:
   - Adicionado um campo de upload de arquivos (`<input type="file">`) para documentos, como a certidão de nascimento.
   - O campo inclui um ícone de upload e um texto de orientação.

   ```html
   <div class="droparea-wrapper">
       <input type="file" id="birth-file" name="birth-file">
       <img src="assets/icons/cloud-upload.svg" alt="Icone de upload de arquivos">
       <p>Clique aqui para selecionar os arquivos</p>
   </div>
   ```

7. **Fechamento do Formulário**:
   - O formulário foi fechado corretamente com as tags `</fieldset>` e `</form>`.

   ```html
       </fieldset>
   </form>
   ```

---

## Resumo das Mudanças

- **HTML**:
  - Criada a estrutura básica do formulário de matrícula.
  - Adicionados campos para nome completo, data de nascimento, sexo, informações médicas e upload de arquivos.
  - Utilização de `<fieldset>` e `<legend>` para agrupar os campos de forma semântica.
