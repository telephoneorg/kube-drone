# drone-kube

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

### Gotchas

#### Problem
Running a separate docker daemon on nodes that drone=true

#### Answer
Install alt-docker on all nodes where labels `drone=true`
* git clone https://github.com/joeblackwaslike/alt-docker
* `cd alt-docker && ./install.sh`
