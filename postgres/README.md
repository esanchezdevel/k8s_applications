# How to deploy Postgres in Kubernetes
Before deploy the PostgreSQL database in Kubernetes, is needed to create a `secret` manually to store the password encrypted.

You can create the `secret` with the following command:

`kubectl create secret generic postgres-password --from-literal=password=<your-password> -n <your-namespace>`

By default, the port 30007 is configured for external connections using the cluster IP. For minikube environment the IP can be get using the command:

`minikube ip`

For internal connections, the following dns can be used
<pod-name>.postgres-headless.<namespace>.svc.cluster.local

To run the database in Kubernetes just execute the following command:

`kubectl apply -f postgres.yaml -n <namespace>`
