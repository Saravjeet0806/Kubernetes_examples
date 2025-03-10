Manual autoscaling -- kubectl scale deployment my-app --replicas=3
Using HPA -- kubectl autoscale deployment my-app --cpu-percent=50 --min=1 --max=10
kubectl autoscale deployment nginx-deployment --cpu-percent=80 --min=1 --max=3
kubectl get hpa
kubectl get hpa --watch

kubectl vpa
kubectl describe vpa <name> -- to see recommendations 
kubectl get pods -n kubesystem | grep vpa -- to see vpa deployments