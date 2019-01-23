1：创建secret(请根据自己的需要配置)
kubectl apply -f ceph-secret.yaml 

2：创建rbac和rbd-provisioner
kubectl apply -f rbac/

3：创建storage-class
kubectl apply -f storage-class.yaml 

4：创建pvc和pod
kubectl apply -f pod-pvc.yaml 
