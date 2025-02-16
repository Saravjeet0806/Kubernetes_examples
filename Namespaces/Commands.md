1. kubectl get pods --namespace=kube-system - to view pods in other namespace.
2. kubectl create -f pod.yaml --namespace=dev - to create pod in other namespace.
3. kubectl get pods --all-namespaces - to view pods in all namespaces.
4. kubectl create namespace dev - to create namespace
5. kubectl config set-context --current --namespace=dev - to switch to other namespace
6. curl http://my-service.other-namespace.svc.cluster.local - to access a service in another namespace.
