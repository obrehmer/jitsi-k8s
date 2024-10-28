# Install JITSI MEET 

### prerequisites

You need access to a kubernetes cluster and helm/kubetctl tool installed on your desktop.
You need access to a DNS Zone to set a A entry.



### Configuration

Edit values.yaml and templates/configmaps.yaml.
Change the domainname/Url and set the domain name. When the service is up and running create the DNS entry and change the extip to the loadbalancer service ip.

### Installation

just run

```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.3.0/deploy/static/provider/cloud/deploy.yaml
```
```
kubectl apply -f https://github.com/jetstack/cert-manager/releases/download/v1.7.1/cert-manager.yaml
```

set the DNS A entry to the external IP of the ingress-nginx-controller:

```
kubectl get -n ingress-nginx svc ingress-nginx-controller
NAME                       TYPE           CLUSTER-IP     EXTERNAL-IP       PORT(S)                      AGE
ingress-nginx-controller   LoadBalancer   10.240.21.69   195.192.156.198   80:32613/TCP,443:31651/TCP   60m
```

```
helm install  jitsi-meet  jitsi-meet
```

After editing the value upgrade the system

```
helm upgrade  jitsi-meet  jitsi-meet
```
