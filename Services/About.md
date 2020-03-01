Kubernetes application services enables
the connectivity between back-end and 
front-end pod to provide service to 
the external user.

Service Types:

1. NodePort Service to port the nodes
   and enable the communication.
   . TargetPort - Port number of a POD
   . NodePort - Range (30000-32767)
   . Port - Service IP and Port 80
2. ClusterIP service creates a virtual IP
   to communicate the front-end and back-end 
   application.
3. Load Balancer provisions a loadbalancer in
   support load balancing the servers.
   
