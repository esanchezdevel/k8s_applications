# How to deploy Apache Kafka on Kubernetes
Using the configuration file `kafka.yaml` you'll be able to install the image apache/kafka:latest on a Kubernetes cluster.

Before the installation:
1. Replace in the file `kafka.yaml` all the occurrences of `{namespace}` with the Kubernetes namespace where you will install the Apache Kafka.
2. Replace in the file `kafka.yaml` all the occurences of `{cluster-ip}` with the cluster ip. For example in Minikube is the result of the command `minikube ip`

Once you have replace the namespace in the file, you can install it executing the following command:

`$ kubectl apply -f kafka.yaml -n <namespace>`

*Note.* If you will install Kafka in your local cluster, you have to know that this configuration could not work properly on `microk8s` cluster, and it's better to use `minikube`

# How to produce messages from outside the cluster
If you want to produce messages from outside the cluster, you have to use as Broker URL to connect the following one
<cluster-ip>:30094

Remember that if you are using Minikube as your cluster in local, the <cluster-ip> can be found using the command:
`minikube ip`
