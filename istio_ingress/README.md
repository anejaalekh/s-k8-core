Istio is a completely open source service mesh that layers transparently onto existing distributed applications. It is also a platform, including APIs that let it integrate into any logging platform, or telemetry or policy system. Istio’s diverse feature set lets you successfully, and efficiently, run a distributed microservice architecture, and provides a uniform way to secure, connect, and monitor microservices. Istio can also be used a Ingress for kubernetes. Istio can also be used with knative for Ingress purposes.

Istio features: 

1. Automatic load balancing for HTTP, gRPC, WebSocket, and TCP traffic.

2. Fine-grained control of traffic behavior with rich routing rules, retries, failovers, and fault injection.

3. A pluggable policy layer and configuration API supporting access controls, rate limits and quotas.

4. Automatic metrics, logs, and traces for all traffic within a cluster, including cluster ingress and egress.

5. Secure service-to-service communication in a cluster with strong identity-based authentication and authorization.



Install Istio on Kubernetes:

1. Install istioctl and add istio/bin to your classpath
    curl -L https://istio.io/downloadIstio | sh -
	
2. Install Istio on K8's. This command will install Istio core, Ingress and Egress to name the few. We are using demo profile but there are other profiles for    production as well.
    istioctl install --set profile=demo

3. Add a side car Proxy, This is not mandatory. This command will add a proxy pod to all the pods deployed in default namespace on k8s
    kubectl label namespace default istio-injection=enabled
	
4. Deploy the icap-server using helm charts. Check if pods are running.

5. Deploy the istio-definition.yaml using below command. This file contains Istio Gateway configuration, Virtual server and Destination rule. That specify how traffic will be routed.

 kubectl create -f istio-definition.yaml
 
 
 
 
 
 Read More  about Istio...  https://istio.io/latest/docs/concepts/what-is-istio/