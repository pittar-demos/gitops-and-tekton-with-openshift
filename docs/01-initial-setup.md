# Install Supporting Components

This demo assumes you have a few components in place that are out of the scope of the demo itself.  These components are:

* Gitea - A git repository manager with webhook capabilities.
* OpenShift GitOps - The default "cluster admin" instance of Argo CD
* Additional Argo CD Config - RBAC and configuration to allow Argo CD to deploy Gitea instances, use an edge-terminated TLS route, and set the default Argo CD role to "admin".

## Install and Configure OpenShift GitOps

Please follow these [Common Setup instructions](https://github.com/pittar-demos/demo-setup#common-setup) to deploy and configure OpenShift GitOps *or* Advanced Cluster Management.

## Install Components Specific To This Demo

Please follow these [demo setup instructions](https://github.com/pittar-demos/demo-setup#demo-gitops-and-serverless-cicd-with-openshift) to deploy and configure the rest of the base components for this demo (OpenShift Pipelines and GitOps).


**Next:** [Install Argo CD for Developers](02-install-argocd-for-developers.md)
