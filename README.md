# k8s-external-ip-checker

A small utility which checks that the current machine's external IP address is in a list of allowed IP addresses.

It can be used to verify that traffic is being correctly routed through a NAT gateway, and to trigger an alert if not.

The utility runs as a k8s DaemonSet, meaning a replica will run on every node in the k8s cluster.
This can be changed by specifying nodeSelectors and/or taint tolerations through the Helm configuration.


## Installation
```shell
$ helm install --namespace nat-gateway --name nat-ip-checker \
  https://github.com/isaziconsulting/k8s-external-ip-checker/releases/download/v0.1.0/k8s-external-ip-checker-0.1.0.tgz
```