# Automatically Update Statefulset
This project implements an operator using the Python k8s-client to automatically update the disk storage of StatefulSet PersistentVolumeClaims (PVCs). It completely resolves the issue of being unable to modify PVC storage, and once deployed, you will never need to worry about capacity issues.

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

## Workflow
```mermaid

```

## Setup steps

Each operator needs to build an image and deploy it to Kubernetes.

**1. [Webhook](https://github.com/pong1013/resize-statefulset-operator/blob/main/webhook/README.md)**

**2. [Manually resize]()**

**3. [Automatically resize]()**

── main.rs
```
