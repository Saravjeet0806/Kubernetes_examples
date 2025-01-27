1. For applying the role use - kubectl apply -f role.yaml or kubectl apply -f rolebinding.yaml
2. kubectl get role or kubectl get rolebinding
3. kubectl auth can-i get pod --as jack -to check permission of a specific user