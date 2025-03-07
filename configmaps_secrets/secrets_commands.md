kubectl get secrets
kubectl describe secret <secret_name>
kubectl get secret <name> -o yaml
kubectl create secret generic <name> --from-literal=<key>=<value>