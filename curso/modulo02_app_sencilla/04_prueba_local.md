# Prueba local de la aplicación

## Objetivo
Ejecutar la API y el frontend en tu equipo para probar la app de notas.

## Pasos

1. **Inicia el backend**
   ```sh
   python app.py
   ```
   El backend estará disponible en http://localhost:5000

2. **Abre el frontend**
   - Abre `index.html` en tu navegador.
   - Si tienes problemas con CORS, usa una extensión de navegador o ejecuta un servidor simple:
     ```sh
     # Desde la carpeta donde está index.html
     python3 -m http.server 8080
     ```
     Luego entra a http://localhost:8080

## Ejercicio
- Prueba agregar, ver y eliminar notas desde la web.
- Observa los mensajes en la terminal donde corre Flask.

## Reto
- Personaliza la app cambiando el título o los campos de las notas.

---
[Volver al índice](../../README.md)