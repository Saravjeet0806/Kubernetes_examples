STEPS TO CREATE BACKUP
Step 1 :- cat /etc/kubernetes/manifests/etcd.yaml
Step 2 :- ETCDCT_API=3 etcdctl snapshot save my_snapshot.db --cacert /etc/kubernetes/pki/etcd/ca.crt \
>  --cert /etcd/kubernetes/pki/etcd/server.crt \
>  --key /etcd/kubernetes/pki/etcd/server.key 

check your backup using ls -ltr

STEPS TO RESTORE 
Step 1 :- ETCDCTL_API=3 etcdctl snapshot restore my_snapshot.db --data-dir /var/lib/etcd --endpoints https://127.0.0.1:2379 --cacert /etc/kubernetes/pki/etcd/ca.crt --cert /etc/kubernetes/pki/etcd/server.crt --key /etc/kubernetes/pki/etcd/server.key 

Step 2 :- rm -rf /var/lib/etcd  --if required

