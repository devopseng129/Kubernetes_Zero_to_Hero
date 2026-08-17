### command to cretae multi node cluster using kind command
kind create cluster --name k8s-multi-node --config multi-node-cluster.yaml

### command to switch between clusters created by kind
kubectl config get-contexts
kubectl config use-context k8s-multi-node