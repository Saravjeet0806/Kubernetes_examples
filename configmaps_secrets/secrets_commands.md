kubectl get secrets
kubectl describe secret <secret_name>
kubectl get secret <name> -o yaml
kubectl create secret generic <name> --from-literal=<key>=<value>
kubectl replace --force -f <filename.yaml> -- to edit a pod and save changes directly