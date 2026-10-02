# Guia de Contribuição — `LATAM-PS-CE-Team/novatlantis-data-platform`

Repositório oficial da **Government Data Platform (GDP)** e do gerador de dados soberanos (100.000 cidadãos) da **República Digital de Novatlantis**, mantido pelo time [`LATAM-PS-CE-Team`](https://github.com/LATAM-PS-CE-Team).

## Regra de Branches e Ambientes (`dev` e `prod`)

Existem apenas **duas branches permanentes** no repositório:

| Branch Alvo do PR | Ambiente no GCP | Regra de Aprovação e Merge |
| :--- | :--- | :--- |
| **`dev`** | **Ambiente `dev`** (`_ENV=dev`) | **Sem entraves (0 aprovações exigidas):** Qualquer colaborador pode submeter PR da sua branch local para a branch **`dev`** e fazer o merge por conta própria após o check verde do Cloud Build. |
| **`main`** | **Ambiente `prod`** (`_ENV=prod`) | **Aprovação obrigatória de `@pedrocalixto`:** Qualquer colaborador pode submeter PR promovendo `dev` $\rightarrow$ `main`, mas o merge na `main` exige aprovação explícita de **`@pedrocalixto`**. |
