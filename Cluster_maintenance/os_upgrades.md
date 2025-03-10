kubectl drain node-1 -- move workload to other loads
kubectl uncordon node-1 -- remove the restrictions of node-1 so that we can schedules pods on this node after maintenance task
kubectl cordon node-2 -- marks a node unschedulable
kubectl drain node01 --ignore-daemonsets


--to upgrade cluster 
1. Firstly upgrade the master node, upgrade kubeadm and kubelet. Restart kubelet service.
2. Upgrade the worker node. Move the workload to other nodes using kubectl drain node1 and upgrade node1 , kubectl uncordon node1 to uncordon it. 
3. Similarly upgrade all the nodes