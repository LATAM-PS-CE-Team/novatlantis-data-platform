# Guia de Contribuição — `novatlantis-data-platform`

1. Crie uma branch a partir de `dev` para alterar schemas em `data-generator/`, scripts em `scripts/` ou módulos em `government-data-platform/`.
2. Abra um Pull Request para `dev`. O pipeline validará os scripts Python, arquivos JSON e schemas SQL.
3. Para atualizar o ambiente de produção, promova `dev` para `main` via Pull Request com aprovação de `@pedrocalixto`.
