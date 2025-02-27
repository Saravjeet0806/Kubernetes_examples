kubectl describe node node01 | grep -i taints -- check if taints exist on node01
kubectl taint nodes node01 spray=mortein:NoSchedule -- to create a taint
kubectl taint nodes controlplane node-role.kubernetes.io/control-plane:NoSchedule -- to untaint controlplane