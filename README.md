# `LATAM-PS-CE-Team/novatlantis-data-platform` — Government Data Platform (GDP) & Lakehouse

Repositório oficial de Engenharia de Dados, *Data Warehouse* Medallion no **BigQuery**, conectores **Cloud Composer / Dataflow** e gerador sintético de 100.000 cidadãos da **República Digital de Novatlantis** (`gov.novatlantis.cloud` e `dev.gov.novatlantis.cloud`).

## Regra de Branches, Projeto GCP Unificado (`novatlantis`) e Ambientes (`dev` e `prod`)

| Branch Alvo | Projeto GCP | Ambiente | Regra de Aprovação e Merge |
| :--- | :--- | :--- | :--- |
| **`dev`** | **`novatlantis`** (`1054221034062`) | **`dev`** (`_ENV=dev`) | **Sem entraves (0 aprovações exigidas):** Qualquer colaborador abre PR para `dev`, valida os schemas/SQL e faz o merge livremente, disparando a sincronização via Keyless WIF + Cloud Build. |
| **`main`** | **`novatlantis`** (`1054221034062`) | **`prod`** (`_ENV=prod`) | **Aprovação obrigatória de `@pedrocalixto`:** Qualquer colaborador pode abrir PR promovendo `dev` $\rightarrow$ `main`, mas o merge exige aprovação explícita de **`@pedrocalixto`** antes de atualizar a camada produtiva no projeto `novatlantis`. |

## Estrutura do Repositório

```text
novatlantis-data-platform/
├── .github/workflows/
│   └── cicd.yml                # Pipeline Keyless WIF (OIDC) -> Google Cloud Build
├── government-data-platform/   # Módulos Terraform de dados (Drop-off, Load, Curated, Confidential, Playground), DAGs e Looker
├── data-generator/             # Gerador sintético de 100k cidadãos (Parquet/NDJSON) e schemas SQL DDL do AlloyDB
├── scripts/                    # Scripts de provisionamento e atualização de Views Medallion no BigQuery
└── cloudbuild/
    ├── cloudbuild-pr.yaml      # Validação automática de Python, JSON schemas e SQL DDL em Pull Requests
    └── cloudbuild-deploy.yaml  # Sincronização automática Medallion BigQuery para dev (branch dev) e prod (branch main)
```
