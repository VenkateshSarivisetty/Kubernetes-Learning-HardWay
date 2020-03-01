Ingress will provide the Controller
and Resources to configure the Load
Balancer.

Rather than accessing the application iusing the nodeport url with port, it can be 
accessed using a domain name. Also
URL can be accessed without port id , for that 
we can use proxy-server as 80. With that , it can be accessed
by using a domain name.

If any new application got added , for example
www.my-online-store.com/video, for that it can be 
a new load balance will create by clourd platform.
Need to access url as https with a secure level.

This complete SSL and loadbalance can be 
handled within a kubernetes cluster.

Ingress helps the users to access by using a single URL
for multiple applications.

Instead of Ingress, it can be done by using 
NGINX, HAPROXY and trafik using a cofiguration setup.

Ingress Controller - Nginx/HAPROXY and trafik
Ingress Resources - Definition Files.


Ingress Controller is not a default in kubernetes cluster.
Example: - GCP HTTP(s) LoadBalncer - NGINX,Countour, HAPROXY, trafik and Istio.


Ingress Controller:-
1. Deployment
2. Service
3. ConfigMap
4. Auth

Ingress Resource:-
Different Rules will get created for each
application/pod.
