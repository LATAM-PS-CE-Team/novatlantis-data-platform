# `LATAM-PS-CE-Team/novatlantis-data-platform` — Government Data Platform (GDP) & Lakehouse

Repositório de Engenharia de Dados, *Data Warehouse* Medallion no **BigQuery**, conectores **Cloud Composer / Dataflow** e gerador sintético de 100.000 cidadãos da **República Digital de Novatlantis** (`novatlantis.gov.cloud`).

## Regra de Branches, Projetos GCP e Ambientes (`dev` e `prod`)

| Branch Alvo do PR | Projeto GCP Dedicado | Ambiente | Regra de Aprovação e Merge |
| :--- | :--- | :--- | :--- |
| **`dev`** | **`novatlantis-dev`** | **`dev`** | **Sem entraves (0 aprovações exigidas):** Qualquer colaborador abre PR para `dev`, valida os schemas/SQL e faz o merge livremente, disparando deploy em `novatlantis-dev`. |
| **`main`** | **`novatlantis-prd`** | **`prod`** | **Aprovação obrigatória de `@pedrocalixto`:** Qualquer colaborador pode abrir PR promovendo `dev` $\rightarrow$ `main`, mas o merge exige aprovação explícita de **`@pedrocalixto`** antes de disparar deploy em `novatlantis-prd`. |

## Estrutura do Repositório

```text
novatlantis-data-platform/
├── government-data-platform/   # Módulos Terraform de dados (Drop-off, Load, Curated, Confidential, Playground), DAGs e Looker
├── data-generator/             # Gerador sintético de 100k cidadãos (Parquet/NDJSON) e schemas SQL DDL do AlloyDB
├── scripts/                    # Scripts de provisionamento e atualização de Views Medallion no BigQuery
└── cloudbuild/
    ├── cloudbuild-pr.yaml      # Validação automática de Python, JSON schemas e SQL DDL em Pull Requests
    └── cloudbuild-deploy.yaml  # Sincronização automática para dev (branch dev -> novatlantis-dev) e prod (branch main -> novatlantis-prd)
```
