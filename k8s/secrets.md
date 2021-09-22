Kubernetes Secrets:
---
    k create secret generic app1 \
    --from-literal=MONGODB='PASSWORD' \ 
    --dry-run=client \
    -o yaml > secret-api.yaml
