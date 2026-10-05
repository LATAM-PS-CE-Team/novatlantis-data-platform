# novatlantis-data-platform

 Camada de dados da plataforma **Novatlantis** no Google Cloud (projeto `novatlantis` / `1054221034062`), incluindo datasets BigQuery, conectores de ingestão e geração de dados sintéticos.

## Ambientes e CI/CD

| Branch | Ambiente | Datasets BigQuery | Regra de Merge |
| :--- | :--- | :--- | :--- |
| `dev` | Desenvolvimento (`_ENV=dev`) | `novatlantis_gdp_*` (views de desenvolvimento) | Merge direto após validação do PR. |
| `main` | Produção (`_ENV=prod`) | `novatlantis_gdp_*` (tabelas e views de produção) | Requer aprovação de `@pedrocalixto`. |

## Estrutura

```text
novatlantis-data-platform/
├── .github/workflows/cicd.yml      # Pipeline WIF -> Cloud Build
├── cloudbuild/
│   ├── cloudbuild-pr.yaml          # Validação de sintaxe Python, JSON e SQL em PRs
│   └── cloudbuild-deploy.yaml      # Atualização de datasets e views no BigQuery
├── data-generator/                 # Gerador de massa sintética (100k registros) e DDL SQL
├── government-data-platform/       # Fundações Terraform de Data Warehouse, DAGs e Looker
└── scripts/                        # Scripts de provisionamento no BigQuery
```
