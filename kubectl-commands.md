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

#namespace<br>
kubectl create -f namespace-definition.yaml
kubectl create namespace dev
kubectl get pods --namespace=dev
kubectl get pods --namespace=prod
kubectl config set-context $(kubctl config current-context) --namespace=dev
kubectl get pods --all-namepsace

#Config Map<br>
kubectl create configmap<br>
kubectl create configmap app-config --from-literal=APP_COLOR=blue<br>
kubectl create configmap <config-name> --from-file=<path-to-file><br>
kubectl create configmap app-config --from-file=app.config.properties<br>
kubectl create -f configmap.yaml
kubectl get configmap
kubectl describe configmap

#Secrets<br>
kubectl create secret generic<br>
kubectl create secret generic app-secret --from-literal=DB_HOST=mysql
kubectl create secret generic <secret-name> --from-file=<path-of-the file>
kubectl create secret generic app-secret --from-file=app.secret.properties
kubectl create -f secret-data.yaml
kubectl get secrets
kubectl describe secrets -o yaml


#To View Secrets run below commands to encrypt the values
echo -n 'mysql' | base64
echo -n 'root' | base64
echo -n 'paswrd' | base64

#decode
echo -n 'mysql' | base64 --decode
echo -n 'root' | base64 --decode
echo -n 'paswrd' | base64 --decode
