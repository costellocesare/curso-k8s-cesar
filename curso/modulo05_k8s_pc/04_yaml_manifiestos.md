# Estructura de un manifiesto YAML en Kubernetes

Ejemplo básico de manifiesto Deployment:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: mi-backend
spec:
  replicas: 1
  selector:
    matchLabels:
      app: backend
  template:
    metadata:
      labels:
        app: backend
    spec:
      containers:
      - name: backend
        image: mi-backend:latest
        ports:
        - containerPort: 5000
```
