1. kubectl apply -f deployment.yaml
2. kubectl apply -f hpa.yaml
3. kubectl get deployments
4. kubectl get hpa
5. kubectl exec -it my-app-8499fbf78d-xvzkw -- /bin/sh -- to open shell inside a pod
6. apt update && apt install -y stress -- install stress tool 
7. stress --cpu 2 --timeout 300 -- generate cpu load
8. kubectl delete hpa my-app-hpa -- to delete hpa
