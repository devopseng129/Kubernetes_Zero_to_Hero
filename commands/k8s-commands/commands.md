### check cluster info
kubectl cluster-info
### check available node
kubectl get nodes
kubectl get nodes -o wide
### list,create and delete pod using command
kubectl get pods
kubectl run nginx --image=nginx
kubectl get pods -o wide
kubectl describe pod nginx
kubectl get pod nginx -o yaml
kubectl delete pod nginx