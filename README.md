
1：<b>创建secret(请根据自己的需要配置)</b> </br>
     kubectl apply -f ceph-secret.yaml 

2：<b>创建rbac和rbd-provisioner </b></br>
kubectl apply -f rbac/

3：<b>创建storage-class </b></br>
kubectl apply -f storage-class.yaml 

4：<b>创建pvc和pod </b></br>
kubectl apply -f pod-pvc.yaml 
