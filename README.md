# MODAFACIL---Modelagem-de-Banco-de-Dados---Faculdade
Sistema de Gestão da Loja de Roupas — ModaFácil

Este repositório contém os scripts SQL desenvolvidos para a Experiência Prática 4 da disciplina de Modelagem de Banco de Dados.
O projeto representa o banco de dados relacional de uma loja de roupas chamada ModaFácil, seguindo as etapas de: minimundo, DER, normalização e modelo lógico.

Os arquivos estão organizados em módulos para facilitar a execução, testes e manutenção do banco.

Estrutura do Repositório
modafacil-sql/
│
├── 00_schema.sql             # Criação das tabelas, PK, FK, índices e constraints
├── 01_inserts.sql            # Comandos de INSERT e ajustes iniciais
├── 02_selects.sql            # Consultas SELECT de exemplo
├── 03_updates_deletes.sql    # Exemplos de UPDATE e DELETE com condições
├── 04_triggers.sql           # (Opcional) Triggers automáticas de estoque e valor_total
└── README.md                 # Documentação do projeto

Objetivo do Projeto

Implementar um banco de dados funcional baseado no modelo lógico criado anteriormente.
O projeto demonstra:

Criação de tabelas relacionais usando SQL (DDL).

Inserção de dados reais utilizando DML.

Execução de consultas relacionais complexas.

Atualizações e remoções com restrições de integridade.

Uso opcional de gatilhos (triggers) para automação.

Modelo Lógico Resumido
Tabela: produto

Atributos: id_produto (PK), nome, categoria, preco, estoque_atual

Tabela: cliente

Atributos: id_cliente (PK), nome, email, telefone

Tabela: funcionario

Atributos: id_funcionario (PK), nome, cargo

Tabela: venda

Atributos: id_venda (PK), data_venda, valor_total, id_cliente (FK), id_funcionario (FK)

Tabela: itemvenda

Atributos: id_item (PK), id_venda (FK), id_produto (FK), quantidade, preco_unitario, subtotal

Requisitos do Ambiente

PostgreSQL 12 ou superior

pgAdmin, psql ou DBeaver para executar scripts

Permissão para criar bancos e tabelas

Criação do Banco de Dados

Via psql:

CREATE DATABASE modafacil;


Via pgAdmin:
Botão direito no servidor > Create > Database > Nome: modafacil

Ordem Recomendada de Execução

Executar o script de criação do schema:

00_schema.sql


Popular o banco com dados iniciais:

01_inserts.sql


Executar consultas de exemplo:

02_selects.sql


Executar modificações (UPDATE/DELETE):

03_updates_deletes.sql


(Opcional) Criar triggers:

04_triggers.sql

Execução via psql

Exemplo de execução:

psql -U postgres -d modafacil -f 00_schema.sql
psql -U postgres -d modafacil -f 01_inserts.sql
psql -U postgres -d modafacil -f 02_selects.sql
psql -U postgres -d modafacil -f 03_updates_deletes.sql
psql -U postgres -d modafacil -f 04_triggers.sql

Descrição dos Arquivos
00_schema.sql

Cria todas as tabelas, define chaves primárias, estrangeiras e constraints.
Inclui índices estratégicos para consulta por categoria e data.

01_inserts.sql

Popula as tabelas com dados reais de clientes, funcionários, produtos e vendas.
Atualiza automaticamente o valor_total das vendas e o estoque dos produtos.

02_selects.sql

Contém consultas com:

JOIN

ORDER BY

GROUP BY

LIMIT

Filtros e relatórios

03_updates_deletes.sql

Inclui exemplos completos de:

Atualização de preços

Correções de dados

Exclusão de itens

Cuidados com integridade

04_triggers.sql

Arquivo opcional contendo:

Trigger automática para atualizar estoque

Trigger para recalcular valor_total ao modificar itemvenda

Funções PL/pgSQL de suporte

Boas Práticas Utilizadas

Organização modular dos scripts

Nomes claros e padronizados

Tipos adequados para valores monetários (NUMERIC)

Uso de transações

Constraints CHECK, UNIQUE e FK

Triggers para automação de regras de negócio

Possíveis Extensões Futuras

View para relatórios consolidados

Sistema de auditoria via triggers

Procedures para registrar vendas completas

Controle de estoque por movimentação em vez de campo numérico

Licença

Este material é destinado para fins acadêmicos e pode ser adaptado conforme necessário.
