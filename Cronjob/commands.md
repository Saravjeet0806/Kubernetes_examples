This deployment creates a cronjob and executes the job 

kubectl get cronjob
kubectl get pods
kubectl get jobs -- to see if the job has been executed

kubectl logs <pod_name> -- to see the desired hello from kubernetes cronjob message
