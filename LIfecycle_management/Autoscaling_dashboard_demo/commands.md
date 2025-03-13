kubectl get deployment metrics-server -n kube-system -- to check if metrics server is ready

kubectl get pods -n kubernetes-dashboard

1. kubectl create token dashboard-admin -n kubernetes-dashboard -- to generate token

2. kubectl create serviceaccount dashboard-admin -n kubernetes-dashboard -- create admin service account

3. kubectl create clusterrolebinding dashboard-admin --clusterrole=cluster-admin --serviceaccount=kubernetes-dashboard:dashboard-admin -- create clusterrole binding

kubectl proxy -- to access dashboard


