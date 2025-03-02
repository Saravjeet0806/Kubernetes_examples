1. In minikube to deploy metrics-server -- minikube addons enable metrics-server
2. In others follow the documentation to deploy metrics server on kubernetes
3. kubectl top node -- to check performance metrics of nodes.
4. kubectl top pod -- to check performance metrics of pods.
5. kubectl logs -f <pod_name> <container_name> -- to get logs of a container. 