# Despliegue en Kubernetes y EKS

En esta sección aprenderás cómo automatizar el despliegue de tu aplicación en un clúster de Kubernetes local y en Amazon EKS usando pipelines de CI/CD.

## Despliegue en Kubernetes local

Puedes agregar un paso en tu pipeline para aplicar los manifiestos YAML a tu clúster local:

```yaml
- name: Desplegar en Kubernetes local
  run: |
    kubectl apply -f k8s/
```

Asegúrate de que tu contexto de `kubectl` apunte a tu clúster local (por ejemplo, Minikube o Kind).

## Despliegue en Amazon EKS

Para desplegar en EKS, necesitas autenticarte y apuntar tu `kubectl` al clúster de EKS. Puedes usar los siguientes pasos en tu pipeline:

```yaml
- name: Configurar credenciales AWS
  uses: aws-actions/configure-aws-credentials@v2
  with:
    aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
    aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
    aws-region: us-east-1

- name: Configurar kubectl para EKS
  run: |
    aws eks update-kubeconfig --region us-east-1 --name NOMBRE_DEL_CLUSTER

- name: Desplegar en EKS
  run: |
    kubectl apply -f k8s/
```

Recuerda almacenar tus credenciales de AWS como secretos en tu repositorio y reemplazar `NOMBRE_DEL_CLUSTER` por el nombre real de tu clúster de EKS.
