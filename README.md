#  Análise da Aplicação

## Análise Inicial da Aplicação

A aplicação analisada consiste em um sistema web para **cadastro e gerenciamento de cursos**.  
Por meio da interface, o usuário pode inserir informações sobre cursos e gerenciar esses registros.

Durante a análise inicial foi possível identificar que a aplicação possui um **formulário de cadastro** com diferentes campos.

Também foi possível observar que o sistema realiza requisições para uma API para armazenar e manipular os dados cadastrados.

Com base nessa análise inicial, foram identificados alguns pontos que poderiam apresentar falhas.

---

##  Decisões Tomadas para Criação dos Testes

Para a criação dos testes foi adotada uma abordagem focada nos principais fluxos da aplicação e nos possíveis cenários de erro que podem ocorrer durante o uso do sistema.

Entre as decisões tomadas para planejar os testes estão:

- Verificar a **validação de campos obrigatórios**, garantindo que o sistema não permita cadastros incompletos.
- Testar **entradas inválidas**, como inserção de letras em campos numéricos.
- Avaliar o comportamento do sistema ao inserir **textos muito longos**, verificando possíveis problemas de layout ou ausência de limite de caracteres.
- Testar **campos preenchidos apenas com espaços**, verificando se o sistema trata corretamente esse tipo de entrada.
- Avaliar se o sistema permite **cadastro de cursos duplicados**.
- Verificar se o sistema realiza **validação adequada de URLs**.
- Testar a funcionalidade de **exclusão de cursos**.
- Monitorar possíveis **erros de comunicação com a API** através do console do navegador.

Com base nesses critérios foram criados **23 casos de teste**, cobrindo cenários positivos e negativos da aplicação.

---

##  Explicação do Raciocínio Durante a Análise

Durante o processo de análise o foco principal foi identificar possíveis situações onde o sistema poderia apresentar comportamentos inesperados.

A estratégia adotada foi simular diferentes tipos de interação do usuário, incluindo:

- Inserção de dados inválidos
- Tentativa de envio de formulários incompletos
- Uso de valores fora do padrão esperado
- Execução de funcionalidades principais da aplicação

Além disso, foi realizada a análise do **console do navegador**, permitindo identificar erros relacionados às requisições da API, como falhas ao tentar excluir um curso.

---

# 📋 Análise das Funcionalidades do Sistema

##  Qual é o objetivo da aplicação?

A aplicação tem como objetivo permitir que usuários possam **cadastrar, visualizar e gerenciar cursos**, armazenando informações relevantes sobre cada curso em um sistema web.

Esse tipo de sistema facilita a organização de cursos e permite que os dados sejam gerenciados de forma centralizada.

---

##  Quais são os principais fluxos disponíveis?

Durante a análise foram identificados os seguintes fluxos principais da aplicação:

- Cadastro de novos cursos
- Visualização da lista de cursos cadastrados
- Visualização dos detalhes de um curso específico
- Exclusão de cursos cadastrados

Esses fluxos representam as principais interações que o usuário pode realizar dentro do sistema.

---

##  Quais pontos do sistema são mais críticos para teste?

Alguns pontos foram considerados mais críticos e exigem maior atenção durante os testes:

- **Validação de campos obrigatórios**
- **Validação de tipos de dados**, como campos numéricos
- **Tratamento de dados inválidos**
- **Prevenção de cadastros duplicados**
- **Funcionamento correto da exclusão de cursos**
- **Tratamento de erros nas requisições da API**

Esses pontos são críticos porque podem impactar diretamente a **integridade dos dados e o funcionamento da aplicação**.

---
##  Casos de Teste

Os casos de teste criados para validar o sistema foram documentados em uma planilha do Google Sheets.

A planilha contém:

- ID do teste
- Descrição do cenário
- Passos para execução
- Resultado esperado
- Resultado obtido
- Status do teste

🔗 Acesse os casos de teste:

[Planilha de Casos de Teste](https://docs.google.com/spreadsheets/d/1vOkG__h7XskD_OkKhCCapEOrhaL4BewvO6WfCftrt2k/edit?usp=sharing)

---

# Bugs Encontrados

Durante a execução dos testes foram identificados os seguintes problemas:

| ID | Bug | Severidade |
|----|-----|------------|
| BUG-01 | Cadastro de curso sem preencher campo obrigatório | Alta |
| BUG-02 | Campo número de vagas aceita letras | Alta |
| BUG-03 | Sistema aceita campos preenchidos apenas com espaços | Média |
| BUG-04 | Sistema permite cadastro de cursos duplicados | Média |
| BUG-05 | Sistema aceita URL inválida | Média |
| BUG-06 | Erro ao excluir curso (405 Method Not Allowed) | Alta |
| BUG-08 | Erro 404 (Not Found) identificado no console ao cadastrar curso e ao retornar para a listagem | Média |

## ⚠️ Erros de API Identificados

Durante a execução dos testes foi identificado um erro na comunicação com a API ao tentar excluir um curso.

Erro retornado:

405 - Method Not Allowed

Esse erro ocorre quando a aplicação tenta realizar uma requisição utilizando um método HTTP que não é permitido pela API.

No caso analisado, o sistema tentou executar uma requisição do tipo DELETE para excluir um curso, porém o servidor não permite esse método nessa rota, impedindo a exclusão do curso.
---

#  Evidências dos Testes

As evidências coletadas durante a execução dos testes estão disponíveis no Google Drive.

📂 Pasta com evidências:

🔗 **(https://drive.google.com/drive/folders/18ZaAU8HI3qYrWAjgIMAazCNMcapRWbu9?usp=drive_link)**

---

##  Ferramentas Utilizadas

Durante a execução dos testes foram utilizadas as seguintes ferramentas:

- **Google Sheets** – criação e documentação dos casos de teste
- **Google Drive** – armazenamento das evidências dos testes
- **Google Chrome DevTools** – análise de erros no console e requisições da API
- **GitHub** – documentação do desafio
- ---
