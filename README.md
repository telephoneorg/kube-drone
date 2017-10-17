# kube-drone

## Usage
* Create a secret for github oauth creds:
```bash
kubectl create secret generic drone \
    --from-literal=github.secret=$GITHUB_SECRET \
    --from-literal=drone.secret=$(echo $GITHUB_SECRET | sha256sum | awk '{print $1}')
```

* Create drone:
```bash
kubectl create -f .
```

* Label a node or nodes with drone=true
```bash
kubectl label ${NODE} ci-server=true
```
