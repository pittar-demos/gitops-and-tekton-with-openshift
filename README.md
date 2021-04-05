# GitOps and Serverless CI/CD with OpenShift

## What's In This Demo?

The puprose of this demo is to:

* Deploy shared CI/CD infrastructure in an OpenShift cluster, such as:
    * Sonatype Nexus - Maven artifact repository.
    * SonarQube - Static code analysis and CVE reporting.
    * Argo CD - GitOps lifecycle management, provided by OpenShift GitOps.
    * Tekton - Serverless CI/CD, provided by OpenShift Pipelines.
* Use GitOps repositories to:
    * Create serverless pipelines.
    * Provision and configure application environments (dev/prod)
* Demonstrate the ability to use notifications from git repository managers such as Github, GitLab, Bitbucket to trigger new builds. Coming soon!
* Manually start a build with a "pipeline run" custom resource.

## What You Will Need

Cluster Admin access to an OpenShift 4.6+ cluster. This has demo has been tested with:

* Red Hat OpenShift Container Platform 4.7
* Red Hat OpenShift Container Platform 4.6
* Azure Red Hat OpenShift (OpenShift 4.6)

## What You Will Do

This demo is deployed in stages:
* Install OpenShift GitOps operator.
* Use the default Argo CD instance in the `openshift-gitops` namespace to:
    * Create the projects/namespaces required for the demo.
    * Configure RBAC for pipelines and Argo CD.
    * Deploy an Argo CD instance for Developers to use.
* Use Developers Argo CD to deploy common tooling (Nexus and SonarQube)
* Use Developers Argo CD to create pipelines and application configuration.
* Kick off a pipeline run!

## Getting Started

Select the version of OpenShift you are using to see how to install the OpenShift GitOps Operator:

* [OpenShift 4.6 (including Azure Red Hat OpenShift)](docs/01-install-gitops-operator-46.md)
* [OpenShift 4.7](docs/01-install-gitops-operator-47.md)

