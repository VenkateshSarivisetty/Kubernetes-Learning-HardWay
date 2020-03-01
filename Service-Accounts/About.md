Service Accounts in Kubernetes is like maintaining
a token to connect to the application to provide security

For example,  when your run kubectl get serviceacccount command
it will show you you the default sa which means any
application to be devloped by a default token.

Or else if you want to use any defined token, you can
run kubectl create serviceaccount <serviceaccountname>, this will
create a serviceaccount with tokenid,
kubectl get secrets <secretname> will give you the
token,

Copy paste this token the application where you are using to connect the
application can use this and make the applicaiton to be
secured!!!!