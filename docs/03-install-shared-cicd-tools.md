# Deploy Shared CI/CD Tools

There are often a few shared CI/CD tools for all project teams to use.  Two good examples are Sonatype Nexus and SonarQube.

Now, we will use Argo CD to install both of these tools in a new namespace called `cicd-tools`.

To do this, run the following command:

```
oc apply -k https://github.com/pittar-demos/gitops-and-tekton-with-openshift/gitops/argocd/03-cicd-tools
```

In the developer instance of Argo CD you will see a new *Application* appear and begin to sync. You can take a look in your cluster at the new `cicd-tools` project to see Nexus and SonarQube spinning up.  Wait until they are both ready (dark blue circles) before continuing.

Although you don't need to login to Nexus or SonarQube for this demo, if you would like to look around, the default credentials are as follows:

Nexus:
* Username: `admin`
* Password: `admin123`

SonarQube:
* Username: `admin`
* Password: `admin`

**Next:** [Create Pipelines and Application Environments](04-install-petclinic.md)