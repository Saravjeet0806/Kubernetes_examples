kubectl drain node-1 -- move workload to other loads
kubectl uncordon node-1 -- remove the restrictions of node-1 so that we can schedules pods on this node after maintenance task
kubectl cordon node-2 -- marks a node unschedulable
kubectl drain node01 --ignore-daemonsets


--to upgrade cluster 
1. Firstly upgrade the master node, upgrade kubeadm and kubelet. Restart kubelet service.
2. Upgrade the worker node. Move the workload to other nodes using kubectl drain node1 and upgrade node1 , kubectl uncordon node1 to uncordon it. 
3. Similarly upgrade all the nodes



–cacert               verify certificates of TLS-enabled secure servers using this CA bundle

–cert                  identify secure client using this TLS certificate file

–endpoints=[127.0.0.1:2379] This is the default as ETCD is running on master node and exposed on localhost 2379.

–key                 identify secure client using this TLS key file


kubectl -n kube-system logs etcd-controlplane | grep -i 'etcd-version' -- to check etcd version
kubectl -n kube-system describe pod etcd-controlplane

kubectl config view -- to view configuration
kubectl config use-context cluster1 -- to switch to cluster1
kubectl get pods -n kube-system | grep etcd -- to view etcd configuration
