1. kubectl get event -o wide -- to check which scheduler scheduled the pod
2. kubectl logs <custom_scheduler_name> --name-space=kubesystem 