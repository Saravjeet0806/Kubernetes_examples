kubectl apply -f clusterrole.yaml

kubectl get clusterrole

kubectl apply -f rolebinding.yaml

kubectl get rolebinding

kubectl auth can-i get secret --as dev -n development -- to check permissions of dev user in developement namespace

kubectl apply -f clusterrolebinding.yaml

kubectl get clusterrolebinding

kubectl auth can-i get secret --as john -A -to check permissions of john user in all namespaces