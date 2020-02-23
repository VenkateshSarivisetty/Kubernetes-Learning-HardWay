#Pods

kubectl run nginx --image nginx <br>
kubectl get pods<br>
kubectl create -f Pod-definition.yaml<br>
kubectl get pods<br>
kubectl describe pod myapp-pod<br>
kubectl delete pod myapp-pod<br>
kubectl edit pod redis<br>


#Replication Controller<br>

kubectl create -f ReplicationController.yaml<br>
kubectl get rc<br>
kubectl get pods -o wide<br>
kubectl delete rc myapp-rc<br>

#ReplicaSet<br>

kubectl create -f ReplicaSet.yaml<br>
kubectl get rs<br>
kubectl get pods -o wide<br>
kubectl delete rs myapp-rs<br>
kubectl replace -f ReplicaSet.yaml<br>
kubectl scale --replicas=6 ReplicaSet.yaml<br>
kubectl scale --replicas=6 <type> myapp-<name><br>


#Deployments<br>
kubectl create -f Deployment.yaml<br>
kubectl get deployments<br>
kubectl get rs<br>
kubectl get pods<br>
