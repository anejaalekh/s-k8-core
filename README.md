# s-k8-core

Kubernetes Architecture:

1. One pod for icap-service, This pod exposes port 1344 for ICAP protocol.
2. LoadBalancer service to expose icap-service on port from range 30000-32767, This is tcp load balancer.
3. There are some environment variables they are injected directly as of now. But can be easily moved to secrets to inject direcltly


Deployment: 
  This repo can be deployed using helm, version 3. 
  
  command to bring up the k8 nodes
  
  helm install <service-name> ./icap-service 
  