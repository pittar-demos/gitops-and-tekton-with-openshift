# GitOps and Serverless CI/CD with OpenShift

## What's In This Demo?

The puprose of this demo is to:

* Stand up some shared CI/CD infrastructure in an OpenShift cluster, such as:
    * Sonatype Nexus - Maven artefact repository.
    * SonarQube - Static code analysis and CVE reporting.
    * Argo CD - GitOps lifecycle management, provided by OpenShift GitOps.
    * Tekton - Serverless CI/CD, provided by OpenShift Pipelines.
* GitOps repositories to:
    * Create serverless pipelines.
    * Provision and configure application environments (dev/prod)
* Ability to use notifications from git repository manageres such as Github, GitLab, Bitbucket to trigger new builds. Coming soon!
* Ability to manually start a build with a "pipeline run" custom resource, or
* Manually trigger a build with the `tkn` command line tool.

## What You Will Need

Cluster Admin access to an OpenShift 4.6+ cluster. This has demo has been tested with:

* Red Hat OpenShift Container Platform 4.7
* Red Hat OpenShift Container Platform 4.6
* Azure Red Hat OpenShift (OpenShift 4.6)

## What You Will Do

This demo is deployed in stage:
* Install OpenShift GitOps operator
* Use the default Argo CD instance in the `openshift-gitops` namespace to deploy a "Developers" Argo CD instance.
* Use Argo CD to stand up some common tooling (Nexus and SonarQube)
* Use Argo CD to create pipelines and application environments
* Kick off a pipeline run!

## Getting Started

Select the version of OpenShift you are using to see how to install the OpenShift GitOps Operator:

* [OpenShift 4.6 (including Azure Red Hat OpenShift)](docs/01-install-gitops-operator-46.md)
* [OpenShift 4.7 (including CodeReady Containers)](docs/01-install-gitops-operator-47.md)

