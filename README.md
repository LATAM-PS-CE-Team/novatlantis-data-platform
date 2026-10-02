# `LATAM-PS-CE-Team/novatlantis-data-platform` — Government Data Platform (GDP) & Lakehouse

Repositório de Engenharia de Dados, *Data Warehouse* Medallion no **BigQuery**, conectores **Cloud Composer / Dataflow** e gerador sintético de 100.000 cidadãos da **República Digital de Novatlantis** (`novatlantis.gov.cloud`).

## Estrutura do Repositório

```text
novatlantis-data-platform/
├── government-data-platform/   # Módulos Terraform de dados (Drop-off, Load, Curated, Confidential, Playground), DAGs e Looker
├── data-generator/             # Gerador sintético de 100k cidadãos (Parquet/NDJSON) e schemas SQL DDL do AlloyDB
├── scripts/                    # Scripts de provisionamento e atualização de Views Medallion no BigQuery
└── cloudbuild/
    ├── cloudbuild-pr.yaml      # Validação automática de Python, JSON schemas e SQL DDL em Pull Requests
    └── cloudbuild-deploy.yaml  # Sincronização automática para dev (branch main) e prod (branch prod)
```
