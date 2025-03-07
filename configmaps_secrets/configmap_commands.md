Imperative way to create configmaps
 1. kubectl create configmap
  <config_name> --from-literal=<key>=<value>
 2. kubectl create configmap
  <config_name> --from-file=<file_path> 

  eg- kubectl create configmap webapp-config-map --from-literal=APP_COLOR=darkblue --from-literal=APP_OTHER=disregard
  
kubectl describe configmaps -- to get details about configmaps  

kubectl replace --force -f /tmp/kubectl-edit-2017421804.yaml -- to force and recreate the pod 