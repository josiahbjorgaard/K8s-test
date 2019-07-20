# Example K8s manifest for basic k8s concepts


The chart installs a simple nginx server according to the following
pattern:

- A `ConfigMap` is used to store the files the server will serve.
- A `Deployment` is used to create a Replica Set of nginx pods.
- A `Service` is used to create a gateway to the pods running in the
  replica set
- A test pod is used to run `curl` inside of the K8s cluster to test the server and return the stored data

It follows [this helm chart](https://github.com/helm/helm/tree/release-2.14/docs/examples/nginx) in basic structure.

## Useage
```
kubectl create -f configmap.yaml
kubectl create -f deployment.yaml
kubectl create -f service.yaml
kubectl create -f service-test.yaml
kubectl exec service-test-pod-name -- curl service-name:port
```
