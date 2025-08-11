# Instalando Python y Flask

## Objetivo
Preparar el entorno de desarrollo instalando Python y Flask para crear una API sencilla.

## ¿Qué es Flask?
Flask es un microframework de Python que permite crear aplicaciones web y APIs de manera rápida y sencilla.

## Pasos para instalar Python y Flask

### 1. Verifica si tienes Python instalado
Abre una terminal y escribe:
```sh
python3 --version
```
Si no lo tienes, descárgalo desde [python.org](https://www.python.org/downloads/).

### 2. Crea un entorno virtual (opcional, recomendado)
```sh
python3 -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate
```

### 3. Instala Flask
```sh
pip install Flask
```

### 4. Verifica la instalación
```sh
python -c "import flask; print(flask.__version__)"
```

## Recursos
- [Documentación oficial de Flask](https://flask.palletsprojects.com/)

---
[Volver al índice](../../README.md)