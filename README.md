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
* Ability to use notifications from git repository manageres such as Github, GitLab, Bitbucket to trigger new builds.
* Ability to manually start a build with a "pipeline run" custom resource, or
* Manually trigger a build with the `tkn` command line tool.

## What You Will Need

* Cluster Admin access to an OpenShift 4.7+ cluster.  CodeReady Containers should work if given enough resources.

## Getting Started

This demo is deployed in two parts:
* Common CI/CD tooling
* Everything else!

### Deploy CI/CD Tooling

### Deploy Pipelines and Application Environments

### Manually Trigger First Builds


