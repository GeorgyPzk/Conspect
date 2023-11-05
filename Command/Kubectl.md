# Commands

`kubectl get <substance> --all-namespaces` - show substance in all namespaces  

`kubectl create -f ./pod.json` - create pod from file
`kubectl create deployment <deploymentName> --image=<Nameimage> --replicas=3 --port=5701` - crate deployment forom image
`kubectl run nginx --image=nginx` - Create and run a particular image in a pod.
`kubectl apply -f FILENAME` -  Apply the configuration in FILENAME.json to a pod.
`kubectl expose <exist-deployment-name> --type="NodePort" --port 8080` - create new service and make it available to external users(add external IP for this service)
`kubectl logs <podName>` - show logs for pod
`kubectl top node` - show CPU and memory.
`kubectl descride node <substance> <substancename>` - Show details of a specific resource or group of resources.
`kubectl cordon $NODENAME` - To mark a Node unschedulable.
`kubectl drain NODE` -  The given node will be marked unschedulable to prevent new pods from arriving. 'drain' evicts the pods if the API server supports

`kubectl node-shell <nodename>` - enter inside the node

## Get inside to node 
`kubectl debug <nodeName> -it --image=mcr.microsoft.com/dotnet/runtime-deps:6.0`
`kubectl node-shell <nodeName>` - node-shell need to be installed

## Azure

`az aks create -g aks-rg -n aks -node-count 2 --generate-ssh-keys` - enter inside the node