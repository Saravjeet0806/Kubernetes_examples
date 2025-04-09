kubectl describe node node01 -- to get details about a node
kubectl label node node01 color=blue -- to apply label to a node
kubectl describe node controlplane | grep -i taints -- to check taints on a node