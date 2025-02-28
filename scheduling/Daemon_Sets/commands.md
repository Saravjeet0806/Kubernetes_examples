kubectl get daemonsets --all-namespaces
kubectl describe daemonset kube-proxy --namespace=kube-system
kubectl describe daemonset kube-flannel-ds --namespace=kube-flannel