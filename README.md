# Teste Técnico - QA

Este repositório foi desenvolvido como parte de um teste técnico para a posição de Quality Assurance (QA).  

O objetivo deste documento é apresentar uma análise da aplicação, identificando:

- **O objetivo principal do sistema**
- **Os principais fluxos disponíveis**
- **Os pontos mais críticos que devem receber maior atenção durante os testes**

A análise foi realizada com base na observação do comportamento da aplicação e dos fluxos disponíveis na interface.

# DESAFIO-QA-BEEDOO-2026


# Análise da Aplicação 

Este documento apresenta uma análise inicial da aplicação, com o objetivo de identificar seu propósito, os principais fluxos disponíveis e os pontos mais críticos que devem receber maior atenção durante os testes.

---

# 1. Objetivo da Aplicação

A aplicação tem como objetivo permitir o gerenciamento de cursos dentro de uma plataforma educacional, possibilitando que usuários criem, organizem e visualizem conteúdos educacionais.

O sistema permite o cadastro e a visualização de cursos, contendo informações relevantes como nome do curso, descrição, instrutor, datas, número de vagas e tipo de curso.

---

# 2. Principais Fluxos Disponíveis

Com base na análise da aplicação, os seguintes fluxos principais foram identificados.

## Cadastro de Curso

Permite ao usuário cadastrar um novo curso informando os seguintes dados:

- **Nome do curso**
- **Descrição**
- **Instrutor**
- **URL da imagem de capa**
- **Data de início**
- **Data de término**
- **Número de vagas**
- **Tipo de curso (presencial ou online)**

Durante esse processo, o sistema deve realizar validação dos campos informados e garantir que as informações sejam armazenadas corretamente.

---

## Listagem de Cursos

Permite visualizar todos os cursos cadastrados na plataforma, exibindo as principais informações de cada curso.

Esse fluxo é importante para garantir que os cursos cadastrados sejam corretamente exibidos e acessíveis aos usuários.

---

## Visualização de Detalhes do Curso

Permite acessar as informações completas de um curso específico, apresentando os dados cadastrados anteriormente.

---

# 3. Pontos Mais Críticos para Teste

Algumas partes da aplicação são mais sensíveis e devem receber maior atenção durante a execução dos testes.

## Validação de Campos no Cadastro de Curso

É fundamental garantir que o sistema valide corretamente os campos obrigatórios, evitando o cadastro de cursos com dados inválidos ou incompletos.

Exemplos de validações importantes incluem:

- **Campos obrigatórios não preenchidos**
- **Tamanho mínimo ou máximo de texto**
- **Formato inválido de URL**
- **Datas inconsistentes**
- **Número de vagas inválido**

---

## Persistência dos Dados

Após o cadastro de um curso, é importante verificar se:

- **O curso foi salvo corretamente**
- **Ele aparece na listagem de cursos**
- **As informações exibidas correspondem aos dados cadastrados**

---

## Comportamento da Listagem de Cursos

A listagem deve:

- **Exibir corretamente todos os cursos cadastrados**
- **Atualizar após novos cadastros**
- **Não apresentar duplicidades ou falhas de carregamento**
- **Excluir curso**
---

## Cenários Negativos

Também é importante validar comportamentos inesperados, como:

- **Tentativa de cadastro com campos vazios**
- **Inserção de dados muito longos**
- **Envio de dados inválidos**
- **Possíveis falhas durante o envio das informações**
