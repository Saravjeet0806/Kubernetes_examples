kubectl apply -f deployment.yml

kubectl apply -f nodeport-service.yml
kubectl apply -f clusterip-service.yml
kubectl apply -f loadbalancer-service.yml

To verify resource
kubectl get pods
kubectl get svc
kubectl get nodes -o wide


1. NodePort Service: Accessible via <NodeIP>:30007.
2. ClusterIP Service: Accessible only within the cluster.
3. LoadBalancer Service: If using a cloud provider, it will create an external load balancer with an IP/URL. Use the IP to access it.
