# solidarytech-gitops

Desired state do cluster EKS da SolidaryTech, sincronizado pelo ArgoCD a partir deste repositório.

```text
argocd/          Applications (app-of-apps): serviços, observabilidade, Velero
apps/            manifests Kubernetes por serviço (deployment, service, hpa, pdb, servicemonitor)
observability/   Prometheus/Grafana/Loki (values), OTel Collector, dashboards e regras de SLO
velero/          values do backup (DR)
```

Código-fonte dos serviços e Terraform da infraestrutura: [`solidarytech`](https://github.com/cltcansado/solidarytech).

O CI de cada serviço (nesse outro repositório) commita aqui a nova tag de imagem depois de
um build bem-sucedido; o ArgoCD detecta o commit e sincroniza automaticamente.
