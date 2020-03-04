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
kubectl get deploy --namespace <namespace>

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
kubectl create secret generic app-secret --from-literal=DB_HOST=mysql<br>
kubectl create secret generic <secret-name> --from-file=<path-of-the file><br>
kubectl create secret generic app-secret --from-file=app.secret.properties<br>
kubectl create -f secret-data.yaml<br>
kubectl get secrets<br>
kubectl describe secrets -o yaml<br>


#To View Secrets run below commands to encrypt the values<br>
echo -n 'mysql' | base64<br>
echo -n 'root' | base64<br>
echo -n 'paswrd' | base64<br>

#decode
echo -n 'mysql' | base64 --decode<br>
echo -n 'root' | base64 --decode<br>
echo -n 'paswrd' | base64 --decode<br>

#Container Security<br>
docker run --user=1001 ubuntu sleep 3600<br>
docker run --cap-add MAC_ADMIN ubuntu<br>
docker run --privelaged ubuntu<br>

#Kubernetes Service Account<br>
kubectl create serviceaccount <serviceaccountname><br>
kubectl get serviceaccount<br>
kubectl describe serviceaccount <serviceaccountname><br>

#Taints & Tolerations<br>
kubectl taint nodes node-name key=value:taint-effect<br>
kubectl taint nodes node-name key=value:Noschedule/PreferNoSchedule/NoExecute<br>
kubectl taint nodes node1 app=blue:NoSchedule<br>
kubectl describe node kubemaster | grep Taint<br>
kubectl taint nodes master node-role.kubernetes.io/master:NoSchedule-<br>

#Label Nodes<br>
kubectl label nodes <node-name> <label-key>=<label=value><br>
kubectl label nodes node-1 size=Large Large or Medium/ Not Small<br>

#Multi-Continer log monitoring<br>

kubectl exec -it app cat /log/app.log<br>

# Log monitoring in kubernetes<br>
kubectl create -f <file-name><br>
kubectl logs -f <pod-name><br>
#To see logs in a multi-container<br>
kubectl logs -f <pod-name><container-name><br>

#lables<br>
kubectl get pods --selector app=app1<br>
kubectl get all --selector env=prod,bu=finance,tier=frontend<br>

#RollOuts<br>
kubectl create -f deployment-definition.yaml --record<br>
kubectl rollout status deployment/myapp-deployment<br>
kubectl rollout history deployment/myapp-deployment<br>
kubectl rollout undo deployment/myapp-deployment<br>

kubectl apply -f deployment-definition.yaml<br>
kubectl set image deployment/myapp-deployment nginx-container=nginx:1.9.1<br>
kubectl rollout history deployment nginx --revision=1<br>

#Jobs and Cronjobs<br>
kubectl create -f job-definition.yaml
kubectl get pods
kubectl get jobs
kubectl logs <container-name>
kubectl delete job <job-name>
kubectl create -f cronjob-definition.yaml
kubectl get cronjobs

#Services
kubectl create -f service-definition.yaml
kubectl get svc
curl http://<NodeIP:30008>

#Ingress
kubectl get ingress --all-namespaces
kubectl describe ingress --namespace app-space
kubectl edit ingress --namespace app-space
kubectl get deploy --namespace app-space
kubectl create configmap nginx-configuration --namespace ingress-space
kubectl create serviceaccount <sa name> --namespace ingress-space
kubectl get roles,rolebindings --namespace ingress-space

#NetworkPolicy
kubectl get networkpolicy

#Volumes
kubectl create -f pv-definition.yaml
kubectl get persistentvolume
kubectl get persistentvolumeclaim -- Pending State
kubectl delete persistentvolumeclaim myclaim
# Choose persistentVolumeReclaimPolicy: Retain/Delete/Recycle
kubectl exec webapp cat /log/app.log

#StateFul Sets
kubectl create -f stateful-definition.yaml
kubectl scale statefulset mysql --replicas=5
kubectl scale statefulset mysql --replicas=3
kubectl delete statefulset mysql