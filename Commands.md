1. kubectl get nodes - to get no. of nodes
2. minikube start - to start minikube 
3. minikube start --memory=4096 --driver=hyperkit - for big application 
4. kubectl create -f pod.yml - to create pod
5. kubectl get pods - to get details about pod
6. kubectl get pods -o wide - to get detailed info about pods
7. minikube ssh - to login into kubernetes cluster, curl <ip_address of pod> - to run the application
8. kubectl delete pod <name_of_pod> - to delete the pod
9. kubectl logs <pod_name> - to check logs
10. kubectl describe pod <pod_name> - to status of pod and debugging
11. kubectl get deploy - to get deployment
12. kubectl get all - to get all information at a single place 
13. kubectl get all -A - to get all info of all namespace 
14. kubectl apply -f pod.yaml - to create pod
15. kubectl get rs - to get replica sets
16. kubectl get pods -w - to see what is happening with the pods (realtime)
17. kubectl rollout status deployment/<deployment_name>
18. kubectl rollout history deployment/<deployment_name> 
19. kubectl rollout undo deployment/<deployment_name>
20. kubectl get nodes -o wide - detailed info about nodes.
21. kubectl edit replicaset new-replica-set - to update replicaset

//use kubernetes cheatsheet to get bunch of kubernetes commands