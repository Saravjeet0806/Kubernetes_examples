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