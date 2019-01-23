1：创建secret
echo "$(ceph auth get-key client.k8s)"|base64
cat << EOF >> ceph-secret.yaml 
apiVersion: v1
kind: Secret
metadata:
  name: ceph-secret-k8s
  namespace: default
type: "kubernetes.io/rbd"
data:
  key: "QVFCWUdraGMvU2VwTHhBQXEvVTNqSmRnQytTbU4vUk43dnhmSXc9PQo="
EOF

kubectl apply -f ceph-secret.yaml 

2：创建rbac和rbd-provisioner
kubectl apply -f rbac/

3：创建storage-class
kubectl apply -f storage-class.yaml 

4：创建pvc和pod
kubectl apply -f pod-pvc.yaml 
