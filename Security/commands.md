Certificates API commands

1. kubectl logs etcd-master -- to check logs
2. cat /etc/kubernetes/manifests/kube-apiserver.yaml -- to get details about the certificates
3. kubectl certificate deny <name>
4. kubectl get csr <name> -o yaml -- to view certificate 
5. kubectl certificate approve <name>
6. kubectl delete csr <name> -- delete csr object

Kubeconfig commands

1. kubectl config view -- to view current kubeconfig file
2. kubectl config view -- kubeconfig=my-custom-config -- to use another kubeconfig file
3. kubectl config --kubeconfig=/root/my-kube-config current-context -- to  view current context
4. kubectl config --kubeconfig=/root/my-kube-config use-context research -- to change context




kubectl describe pod kube-apiserver-controlplane -n kube-system -- to check details about kube-api server
kubectl describe role kube-proxy -n kube-system -- list roles in kube-system namespace
kubectl describe rolebinding kube-proxy -n kube-system -- check detail of rolebinding in the kube-system namespace

Service accounts and tokens commands
1. kubectl create serviceaccount <name>
2. kubectl get serviceaccount
3. kubectl describe serviceaccount <name>
4. kubectl crate token <name>
5. kubectl get po -o yaml

Security contexts commands
1. kubectl exec <pod_name> -- whoami -- to check which user is executing the process