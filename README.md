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

## Análise da Aplicação

A análise inicial teve como objetivo compreender o funcionamento do módulo de cursos e identificar os principais fluxos da aplicação.

Foi observado que o sistema permite cadastrar cursos, visualizar a listagem, acessar detalhes e realizar a exclusão. Esses fluxos foram tratados como prioritários por representarem o uso principal da funcionalidade.

Também foram analisados os campos do formulário de cadastro, como nome do curso, URL da imagem, descrição, tipo de curso, data e número de vagas, além do comportamento da navegação entre páginas, redirecionamentos e atualização das informações após cada ação.

Com base nessa análise, foi definida uma estratégia de testes focada nos fluxos críticos, validações de campos e cenários negativos.

## Decisões Tomadas para Criação dos Testes

A criação dos testes foi baseada na priorização das funcionalidades de maior impacto para o usuário.

O fluxo principal de cadastro de cursos recebeu atenção especial por ser a funcionalidade central do módulo. Além disso, foram realizados testes de validação de campos, contemplando dados inválidos, campos obrigatórios não preenchidos e entradas fora do padrão esperado.

Também foram incluídos cenários negativos para avaliar como o sistema se comporta diante de ações incorretas ou inesperadas. A listagem de cursos foi validada para garantir a exibição correta das informações e o funcionamento de ações como visualização e exclusão.

Os testes foram organizados de forma prática e objetiva, resultando em 24 casos de teste cobrindo cenários positivos e negativos da aplicação.

## Explicação do Raciocínio Durante a Análise

Durante a análise o foco foi compreender o comportamento principal do módulo de cursos e identificar os fluxos com maior impacto para o usuário.

Meu raciocínio foi validar primeiro o funcionamento esperado da aplicação e em seguida explorar cenários de erro, entradas inválidas e comportamentos inesperados. Isso permitiu avaliar tanto os fluxos positivos quanto o sistema em situações negativas.

Também foram considerados os riscos de cada funcionalidade, priorizando ações críticas que afetam diretamente a experiência do usuário e a confiabilidade da aplicação.

Além da interface, foi analisado o console do navegador para identificar possíveis falhas técnicas, como erros nas requisições da API, incluindo problemas ao executar a exclusão de cursos.

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

## 🔒 Testes de Segurança

Durante a análise também foi realizado um teste adicional de segurança para verificar a possibilidade de vulnerabilidade Cross-Site Scripting (XSS) no campo Nome do curso.

Nesse teste foi inserido um script no campo de entrada com o objetivo de verificar se o sistema executaria código JavaScript no navegador.

Exemplo utilizado no teste:

<script>alert('test')</script>

O comportamento esperado é que o sistema trate o conteúdo inserido como texto simples, sem executar o script no navegador.

Esse tipo de teste ajuda a identificar possíveis falhas de segurança relacionadas à validação de entradas do usuário.

---

## Bugs Encontrados

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

##  Evidências dos Testes

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
