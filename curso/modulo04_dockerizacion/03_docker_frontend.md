# Dockerizando el frontend (opcional)

Puedes crear un contenedor para el frontend usando una imagen de Nginx o similar.

```dockerfile
FROM nginx:alpine
COPY ./frontend /usr/share/nginx/html
```
