# .github

Plantillas de PR e issues, política de seguridad y workflows reutilizables de la organización Siro Health. No contiene secretos ni información interna.

## Workflow reutilizable de tests de Python

Cada repo de un servicio lo llama desde su propio `.github/workflows/tests.yml`:

```yaml
jobs:
  tests:
    uses: Siro-Health/.github/.github/workflows/python-function-tests.yml@main
    with:
      python-version: "3.12"
      requirements: "requirements-dev.txt functions/<nombre>/requirements.txt"
```

`requirements` es una lista de archivos separados por espacio que se instalan antes de correr `pytest`.
