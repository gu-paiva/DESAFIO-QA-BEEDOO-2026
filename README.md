# Desafio QA – Beedoo

Este repositório contém a análise, planejamento e execução de testes realizados como parte do desafio técnico para a vaga de QA.

O objetivo foi avaliar a qualidade de uma aplicação web de cadastro e gerenciamento de cursos, identificando possíveis falhas e documentando cenários de teste.

---
## Sumário

- [Análise da Aplicação](#análise-da-aplicação)
- [Análise das Funcionalidades do Sistema](#-análise-das-funcionalidades-do-sistema)
- [Casos de Teste](#casos-de-teste)
- [Bugs Encontrados](#bugs-encontrados)
- [Erros de API Identificados](#%EF%B8%8F-erros-de-api-identificados)
- [Evidências dos Testes](#evidências-dos-testes)
- [Ferramentas Utilizadas](#ferramentas-utilizadas)

---

#  Análise da Aplicação

Ao explorar a aplicação, identifiquei que o módulo de cursos possui como principais objetivos permitir o cadastro, exibição, consulta e gerenciamento dos cursos cadastrados.

Durante a análise inicial, considerei os seguintes pontos como mais críticos para validação:

- Funcionamento do fluxo principal de cadastro de curso;
- Integridade das informações exibidas na listagem;
- Validação de campos obrigatórios;
- Tratamento de entradas inválidas;
- Comportamento da aplicação diante de ações inesperadas do usuário;
- Estabilidade da navegação entre telas.

Também observei que, por se tratar de um módulo de cadastro, qualquer falha pode impactar diretamente a experiência do usuário e a confiabilidade dos dados exibidos no sistema.


---

##  Decisões Tomadas para Criação dos Testes

Para a criação dos testes, organizei a cobertura com foco em cenários que representassem tanto o uso esperado da aplicação quanto situações de erro e comportamento inesperado.

### 1. Priorizar o fluxo principal
O primeiro foco foi validar se o cadastro de curso funcionava corretamente com dados válidos, pois esse é o fluxo central da funcionalidade.

### 2. Cobrir validações de campos
Como telas de cadastro costumam concentrar muitos erros, testei:
- Campos obrigatórios;
- Formatos inválidos;
- Valores inconsistentes;
- Tentativas de envio com dados incorretos.

### 3. Testar cenários negativos
Incluí cenários negativos para verificar como o sistema se comporta diante de entradas inválidas, ações incompletas ou situações não previstas.

### 4. Validar a listagem de cursos
Verifiquei se os cursos cadastrados aparecem corretamente na listagem e se as informações permanecem consistentes após as ações realizadas.

### 5. Registrar bugs com severidade
Documentei os defeitos encontrados com identificação e severidade, facilitando a comunicação e destacando a criticidade de cada problema.

Com base nesses critérios foram criados **24 casos de teste**, cobrindo cenários positivos e negativos da aplicação.

---

##  Explicação do Raciocínio Durante a Análise

Meu raciocínio foi baseado em analisar a aplicação sob a perspectiva do usuário, considerando também os riscos mais relevantes para o negócio e para a qualidade do sistema.

Comecei pelo fluxo principal: **cadastrar um curso com sucesso**.

A partir disso, avaliei possíveis falhas com perguntas como:

- O que acontece se o usuário deixar campos obrigatórios em branco?
- O sistema impede valores inválidos?
- É possível cadastrar informações duplicadas?
- A aplicação mantém consistência após salvar?
- Existe alguma falha visível, como erro de página ou quebra de fluxo?

Esse processo me ajudou a construir testes não apenas para validar o funcionamento esperado, mas também para identificar falhas que poderiam passar despercebidas.


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

- Validação de campos obrigatórios
- Validação de tipos de dados, como campos numéricos
- Tratamento de dados inválidos
- Prevenção de cadastros duplicados
- Funcionamento correto da exclusão de cursos
- Tratamento de erros nas requisições da API

Esses pontos são críticos porque podem impactar diretamente a integridade dos dados e o funcionamento da aplicação.

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

## 🔒 Testes de Segurança (Extra)

Durante a análise também foi realizado um teste adicional de segurança para verificar a possibilidade de vulnerabilidade Cross-Site Scripting (XSS) no campo Nome do curso.

Nesse teste foi inserido um script no campo de entrada com o objetivo de verificar se o sistema executaria código JavaScript no navegador.

Exemplo utilizado no teste:

<script>alert('test')</script>

O comportamento esperado é que o sistema trate o conteúdo inserido como texto simples, sem executar o script no navegador.

Esse tipo de teste ajuda a identificar possíveis falhas de segurança relacionadas à validação de entradas do usuário.

---

# Bugs Encontrados

Durante a execução dos testes foram identificados os seguintes problemas:

| ID | Bug | Severidade |
|----|-----|------------|
| BUG-01 | Sistema permite cadastrar curso com data futura | Média |
| BUG-02 | Campo Número de vagas aceita valores inválidos | Média |
| BUG-03 | Botão excluir curso não funciona | Alta |
| BUG-04 | Não é possível visualizar detalhes do curso | Média |
| BUG-05 | Cadastro de curso sem preencher campo obrigatório | Alta |
| BUG-06 | Sistema permite cadastro de cursos duplicados | Média |
| BUG-07 | Erro 404 (Not Found) identificado no console ao cadastrar curso e ao retornar para a listagem | Alta |

Para mais detalhes, consulte a aba **BUG report** na planilha de testes.
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
