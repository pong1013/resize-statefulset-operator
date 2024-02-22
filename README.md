# Automatically Update Statefulset
This project implements an operator using the Python client to automatically update the disk storage of StatefulSet PersistentVolumeClaims (PVCs). It completely resolves the issue of being unable to modify PVC storage, and once deployed, you will never need to worry about capacity issues.

## How it works?

### Manually Resize
1. Add the annotation to the pod
    ```yaml
        "resize-statefulset-operator/resize": 16Gi
    ```
   
