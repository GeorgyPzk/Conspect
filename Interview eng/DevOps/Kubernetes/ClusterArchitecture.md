# Cluster Architecture

## Master Node

- API Server - it interact with the cluster components

- etcd cluster – **a simple, distributed key value storage** which is used to store the Kubernetes cluster data (such as number of pods, their state, namespace, etc), API objects and service discovery details. It is only accessible from the API server for security reasons. etcd enables notifications to the cluster about configuration changes with the help of watchers. Notifications are API requests on each etcd cluster node to trigger the update of information in the node’s storage.

- kube-scheduler - choose a Node to create a Pod

- kube-controller-manager - responsible for the health and monitoring of the cluster. It works constantly and does not interact with the user in any way.

- cloud-controller-manager - connect API Server with API Cloud(Azure, AWS, GCP). Responsible for creating resources in the cloud.


## Worker node

- kubelet - it is exist in every Node. Responsible for the health and monitoring of containers in this Node. Communicates with container runtime to starts and stops containers. Sends information to the API Server.

- Container runtime - is the software that is responsible for running containers.

- kube-proxy - is in every Node. Responsible for maintaining network rules on the node, allowing and disallowing network interaction.

