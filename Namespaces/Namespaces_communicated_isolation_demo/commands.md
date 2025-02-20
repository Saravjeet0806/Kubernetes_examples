kubectl apply -f create_namespace.yaml
kubectl apply -f network_policy_test1_test2.yaml
kubectl apply -f network_policy_test3.yaml

# Kubernetes Namespace Communication Demo

This guide demonstrates how to configure and verify network communication between Kubernetes namespaces.

## Overview

- `test1` and `test2` can communicate with each other.
- `test3` is completely isolated.

## 1️⃣ Create Namespaces

Create the following namespaces:

```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: test1
---
apiVersion: v1
kind: Namespace
metadata:
  name: test2
---
apiVersion: v1
kind: Namespace
metadata:
  name: test3
```

Apply the configuration:

```sh
kubectl apply -f namespaces.yaml
```

## 2️⃣ Configure Network Policies

### Allow communication between `test1` and `test2`

Create the following NetworkPolicies:

```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: allow-test2-to-test1
  namespace: test1
spec:
  podSelector: {}
  ingress:
    - from:
        - namespaceSelector:
            matchLabels:
              name: test2
---
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: allow-test1-to-test2
  namespace: test2
spec:
  podSelector: {}
  ingress:
    - from:
        - namespaceSelector:
            matchLabels:
              name: test1
```

Apply the policies:

```sh
kubectl apply -f network-policies.yaml
```

### Isolate `test3`

Create a NetworkPolicy to block all traffic in `test3`:

```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: deny-all
  namespace: test3
spec:
  podSelector: {}
  policyTypes:
    - Ingress
    - Egress
```

Apply the policy:

```sh
kubectl apply -f test3-network-policy.yaml
```

## 3️⃣ Verify Connectivity

### Deploy Test Pods

Run test pods in each namespace:

```sh
kubectl run test1-pod --image=busybox --restart=Never -n test1 -- sleep 3600
kubectl run test2-pod --image=busybox --restart=Never -n test2 -- sleep 3600
kubectl run test3-pod --image=busybox --restart=Never -n test3 -- sleep 3600
```

### Get Pod IPs

```sh
kubectl get pods -o wide -n test1
kubectl get pods -o wide -n test2
kubectl get pods -o wide -n test3
```

### Test Communication

✅ **Test communication between **``** and **``** (Should Work)**

```sh
kubectl exec -it test1-pod -n test1 -- ping <test2-pod-IP>
kubectl exec -it test2-pod -n test2 -- ping <test1-pod-IP>
```

❌ **Test communication with **``** (Should Fail)**

```sh
kubectl exec -it test1-pod -n test1 -- ping <test3-pod-IP>
kubectl exec -it test2-pod -n test2 -- ping <test3-pod-IP>
```

✅ **Confirm **``** is isolated from the internet**

```sh
kubectl exec -it test3-pod -n test3 -- ping 8.8.8.8
```

### Cleanup (Optional)

```sh
kubectl delete pod test1-pod -n test1
kubectl delete pod test2-pod -n test2
kubectl delete pod test3-pod -n test3
```

## 🎯 Expected Results

- `test1` and `test2` should communicate successfully.
- `test3` should be completely isolated.

This confirms the network policies are correctly applied! 🚀

