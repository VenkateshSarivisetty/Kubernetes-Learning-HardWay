#Pods

kubectl run nginx --image nginx
kubectl get pods
kubectl create -f Pod-definition.yaml
kubectl get pods
kubectl describe pod myapp-pod
kubectl delete pod myapp-pod
kubectl edit pod redis


#Replication Controller

kubectl create -f ReplicationController.yaml
kubectl get rc
kubectl get pods -o wide
kubectl delete rc myapp-rc

#ReplicaSet

kubectl create -f ReplicaSet.yaml
kubectl get rs
kubectl get pods -o wide
kubectl delete rs myapp-rs
kubectl replace -f ReplicaSet.yaml
kubectl scale --replicas=6 ReplicaSet.yaml
kubectl scale --replicas=6 <type> myapp-<name>


#Deployments
kubectl create -f Deployment.yaml
kubectl get deployments
kubectl get rs
kubectl get pods
