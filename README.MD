## GitOps demo
`ArgoCD` `Red Hat OpenShift GitOps`

#### PKCS#8 key (api.middleware.rhbr-lab.com)
openssl req -x509 -utf8 -sha256 -days 3650 -newkey rsa:4096 -keyout key.pem -out cert.pem -nodes
#### PKCS#8 to PKCS#1
openssl rsa -in key.pem -out key.pem
