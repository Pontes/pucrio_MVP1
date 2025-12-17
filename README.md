# PUC-Rio — MVP 1 (Databricks) — Pipeline de Dados

## Objetivo
Construir um pipeline de dados na nuvem (Databricks) a partir de exportações CSV do prontuário eletrônico, visando responder perguntas de negócio com SQL e disponibilizar um BI online.

## Perguntas de negócio
- Quais pacientes foram atendidos em mais de uma unidade?
- Total de pacientes homens e mulheres?
- Quantidade de pacientes por raça/cor?
- Quantidade de pacientes diabéticos?
- Quantidade de pacientes hipertensos?
- Quais profissionais mais realizaram atendimentos no município?

## Arquitetura (Medallion)
- **Bronze**: dados brutos (CSV → tabelas Delta)
- **Silver**: dados limpos e conformados (tipos, domínios, pseudonimização)
- **Gold**: camada analítica (modelo estrela / views para BI)

## Stack
- Databricks Free Edition (Serverless)
- Delta Tables
- SQL (principal) + Python quando necessário

## Privacidade
Os CSVs reais não são publicados neste repositório por conterem dados sensíveis.
Este repositório contém apenas código, documentação e evidências (prints/diagramas).

## Como reproduzir
1. Fazer upload dos CSVs no Databricks (delimiter `;`, header habilitado) e criar tabelas Delta.
2. Executar os scripts em `/sql` na ordem:
   - `01_schemas.sql`
   - `02_bronze_setup.sql`
   - `03_silver.sql`
   - `04_gold.sql`
   - `05_queries_bi.sql`

## Evidências
Prints do BI e diagramas ficam em `/assets/img`.
