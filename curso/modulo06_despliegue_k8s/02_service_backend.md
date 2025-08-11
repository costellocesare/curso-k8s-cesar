# Exponiendo el backend con un Service

Crea un Service para exponer tu backend dentro o fuera del clúster.

```yaml
apiVersion: v1
kind: Service
metadata:
  name: backend-service
spec:
  type: NodePort
  selector:
    app: backend
  ports:
    - port: 5000
      targetPort: 5000
      nodePort: 30001
```
