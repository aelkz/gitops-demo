## GitOps demo
`ArgoCD` `Red Hat OpenShift GitOps`

## Installation
from Red Hat:

### What is GitOps?
GitOps is a set of DevOps practices that are used to manage infrastructure and application configurations using the Git open source version control system as a "single source of truth," and is widely used with Kubernetes.
At its core, GitOps maintains that a system must have its desired state expressed declaratively, and that the desired state is versioned and immutable, pulled automatically, and continuously reconciled.
GitOps provides an array of benefits, including standardizing workflows, simplifying tool sets, reducing potential variables and errors, increasing developer productivity, and more.

### What is ArgoCD?
Put simply, ArgoCD is an easy to use tool that allows development teams to deploy and manage applications without having to learn a lot about Kubernetes, and without needing full access to the Kubernetes system. This hugely simplifies the process of running applications in Kubernetes, ultimately leading to better security and increased developer productivity.

`source`<br>
https://www.redhat.com/en/blog/argocd-and-gitops-whats-next<br>
https://argoproj.github.io/cd/

### GitOps managed project

```
oc delete project $APP_NS ; oc new-project $APP_NS --description="Application demo managed by GitOps" --display-name="Application demo managed by GitOps"
```

## Red Hat OpenShift GitOps operator

```
export ARGOCD_NS=lab-argocd
export APP_NS=lab-app
export APP_NAME=app-3scale-apicast-gitops

oc delete project $ARGOCD_NS ; oc new-project $ARGOCD_NS --description="GitOps Tools" --display-name="GitOps Tools"
```

#### PKCS#8 key (api.middleware.rhbr-lab.com)

```
openssl req -x509 -utf8 -sha256 -days 3650 -newkey rsa:4096 -keyout key.pem -out cert.pem -nodes
```

#### PKCS#8 to PKCS#1

```
openssl rsa -in key.pem -out key.pem
```
