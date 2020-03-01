Bring down all the pods and deployment the new pods is called
Recreate Deployment Strategy, Application may went down
if the new pod deployment was not occur on time.

Rolling-Update is the default strategy where the pod
deployment will occur one-by-one. Hence there wont be any
downtime.

Recreate                  RollingUpdate
Old Replicas to scaled    New Replicas scaled up
down and new replicas     1 at a time.
will came up

