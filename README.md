# spingarden-training
### Create namespaces
```bash
$ kubectl apply -f namespaces.yaml
```
### Install minio cluster
```bash
$ helm upgrade --install minio --values minio-values.yaml --namespace ns-minio --version 5.0.17 stable/minio
```
### Install OSS spinnaker-operator 
```bash
$ mkdir -p spinnaker-operator && cd spinnaker-operator
$ bash -c 'curl -L https://github.com/armory/spinnaker-operator/releases/download/v1.0.2/manifests.tgz| tar -xz'
 
# Install or update CRDs cluster wide
$ kubectl apply -f deploy/crds/

# Install operator in namespace spinnaker-operator
$ kubectl -n spinnaker-operator apply -f deploy/operator/cluster

$ kubectl apply -f spinnaker-cluster.yaml

```
### Install Jenkins
```bash
helm upgrade --install jenkins --values jenkins-values.yaml --namespace jenkins --version 2.4.0 stable/jenkins
```
