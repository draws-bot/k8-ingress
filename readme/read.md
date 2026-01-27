Internet
   |
   v
[Cloud Load Balancer]  <-- (L4 - forwards TCP/HTTP traffic)
   |
   v
[Ingress Controller (Pod)]  <-- (L7 - routes traffic based on rules)
   |
   v
[Kubernetes Services/Pods]



You apply the Ingress resource in front of your services, but it’s behind the cloud provider’s Load Balancer which exposes your cluster to the internet.

So the Ingress sits between:

The external Load Balancer (created via a Service of type LoadBalancer or via an Ingress Controller like ALB)

And the internal Kubernetes services