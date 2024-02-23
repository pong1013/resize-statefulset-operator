# Automatically Update Statefulset
![k8s](https://upload.wikimedia.org/wikipedia/commons/thumb/6/67/Kubernetes_logo.svg/798px-Kubernetes_logo.svg.png)

---
This project implements an operator using the Python k8s-client to automatically update the disk storage of StatefulSet PersistentVolumeClaims (PVCs). It completely resolves the issue of being unable to modify PVC storage, and once deployed, you will never need to worry about capacity issues.


## Workflow
```mermaid
flowchart LR

    subgraph Resize
    direction TB
    E[Watch statefulset object] --> F[Get the updating events]
    F --> G[Modify PVC size];
    G --Backup--> H[Encrypt statefulset and save into configmap with new size]
    H --> I[Recreate Statefulset]
    end;

    subgraph webhook
    direction TB
    A[Webhook intercepts API request] --> B[Check if the storage change to bigger size];
    B --Yes--> C[Add annotation];
    B --No--> D[abort 400];
    C --> X[Go to resize];
    end;
    webhook --> Resize
    
```

### Operator Structure
```
<Operator-name>
├── Dockerfile
├── requirements.txt
├── <operator>.py
├── azure_pipelines.yaml
└── chart
    ├── Chart.yaml
    ├── azure_pipelines.yaml
    ├── values.yaml
    └── templates
        └── ...
```

## Setup steps

Each operator needs to build an image and deploy it to Kubernetes.

**1. [Webhook](https://github.com/pong1013/resize-statefulset-operator/tree/main/webhook)**

**2. [Manually resize](https://github.com/pong1013/resize-statefulset-operator/tree/main/main-resize-operator)**

**3. [Automatically resize](https://github.com/pong1013/resize-statefulset-operator/tree/main/auto-resize-operator)**


