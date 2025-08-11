# Ejemplo básico de pipeline CI/CD

A continuación, se muestra un ejemplo sencillo de un pipeline de CI/CD usando GitHub Actions:

```yaml
name: CI/CD Pipeline
on:
  push:
    branches: [ main ]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Configurar Python
        uses: actions/setup-python@v2
        with:
          python-version: '3.9'
      - name: Instalar dependencias
        run: |
          pip install -r requirements.txt
      - name: Ejecutar pruebas
        run: |
          pytest
```

Este pipeline instala dependencias y ejecuta pruebas automáticamente en cada push a la rama principal.
