# Install JITSI MEET 

### prerequisites

You need access to a kubernetes cluster and helm/kubetctl tool installed on your desktop.
Optional Cloudflare and DNS.


### Configuration

Edit values.yaml and templates/configmaps.yaml.
Change the domainname/Url and set the domain name. When the service is up and running create the DNS entry and change the extip to the loadbalancer service ip.

### Installation

just run

```
helm install  jitsi-meet  jitsi-meet
```

After editing the value upgrade the system

```
helm upgrade  jitsi-meet  jitsi-meet
```
