# Desplegando el frontend

Crea un Deployment y Service para el frontend, similar al backend.

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: frontend
spec:
  replicas: 1
  selector:
    matchLabels:
      app: frontend
  template:
    metadata:
      labels:
        app: frontend
    spec:
      containers:
      - name: frontend
        image: mi-frontend:latest
        ports:
        - containerPort: 80
```
