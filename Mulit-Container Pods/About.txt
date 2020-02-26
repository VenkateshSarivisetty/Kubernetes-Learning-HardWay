#Mulit-Container Pods Patterns as below,
 1. Ambassdor - Application communicates to different environments.
 2. Adapter - convert logs into a common pattern before sending it to central server
 3. Sidecar - Deploying a Logging agent along with a webserver
 to capture logs generated and send to log server.