kubectl apply -f secrets.yaml
kubectl apply -f configmap.yaml
kubectl apply -f pod.yaml

verify 
1. kubectl exec -it my-pod -- sh  
2. env | grep -E 'APP_NAME|LOG_LEVEL|DB_PASSWORD'