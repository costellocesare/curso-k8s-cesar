# Creando un Dockerfile para el backend

Aprende a crear un Dockerfile básico para tu aplicación backend en Python/Flask.

```dockerfile
FROM python:3.9-slim
WORKDIR /app
COPY . .
RUN pip install -r requirements.txt
CMD ["python", "app.py"]
```
