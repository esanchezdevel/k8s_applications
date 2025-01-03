# How to deploy Apache Kafka on Kubernetes
Using the configuration file `kafka.yaml` you'll be able to install the image apache/kafka:latest on a Kubernetes cluster.

Before the installation, you'll need to replace in the file `kafka.yaml` all the occurrences of `{namespace}` with the Kubernetes namespace where you will install the Apache Kafka.

Once you have replace the namespace in the file, you can install it executing the following command:

`$ kubectl apply -f kafka.yaml -n <namespace>`

*Note.* If you will install Kafka in your local cluster, you have to know that this configuration could not work properly on `microk8s` cluster, and it's better to use `minikube`
