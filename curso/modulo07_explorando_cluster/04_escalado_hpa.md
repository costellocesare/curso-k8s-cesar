# Escalado manual y automático (HPA)

Aprende a escalar tus aplicaciones manualmente y con Horizontal Pod Autoscaler (HPA).

- Escalado manual: `kubectl scale deployment <nombre> --replicas=3`
- HPA: `kubectl autoscale deployment <nombre> --cpu-percent=50 --min=1 --max=5`
