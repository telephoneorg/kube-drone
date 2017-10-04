# kube-drone

## Usage
* Create a secret for github oauth creds:
```bash
kubectl create secret generic drone \
    --from-literal=drone.github.secret=${GITHUB_SECRET} \  
    --from-literal=drone.secret=${DRONE_SECRET}
```

* Create drone:
```bash
kubectl create -f .
```

* Label a node or nodes with drone=true
```bash
kubectl label ${NODE} drone=true
```
