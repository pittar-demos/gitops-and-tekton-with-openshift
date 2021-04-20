# Install Argo CD for Developers

The default "cluster" instance of Argo CD is meant for cluster admin tasks (such as creating new namespaces, managing role bindings, etc.), not for day-to-day application management.  In order to manage our Pet Clinic application, we will install a new instance of Argo CD in a new `argocd` namespace for Developers to use.

However, we first need to create the projects/namespaces that we will use in this demo.  They are:

* **argocd** - The namespace where the new Argo CD instance will be deployed.
* **cicd-tools** - The namespace for the shared CI tools (Nexus and SonarQube).
* **petclinic-cicd** _ The namespace where Pet Clinic `BuildConfig`, `ImageStream`, `Task` and `Pipeline` resources will reside.
* **petclinic-dev** - The "DEV" Pet Clinic environment.
* **petclinic-prod** - The "PROD" Pet Clinic environment.

To put all this in place, we will create a new *AppProject* and *Application* in the `openshift-gitops` Argo CD instance to manage these environments.  You can do this by executing the following command:

```
oc apply -k https://github.com/pittar-demos/gitops-and-tekton-with-openshift/gitops/argocd/01-environments-ga
```

Once the environments *Application* is synchronized and healthy, you can execute the next command to create an *Application* to deploy and manage the Developer instance of Argo CD:

```
oc apply -k https://github.com/pittar-demos/gitops-and-tekton-with-openshift/gitops/argocd/02-argocd-for-developers
```

If you have the UI for the cluster instance of Argo CD open, you should see "argocd-devs" and "environments" *Applications*.  Once they are both healthy and green, the new Argo CD instance in the `argocd` namespace will be ready!

**Note:** If you are using OpenShift 4.6 the Argo CD application will remain "Out of Sync".  This is ok!  This is due to the fact that OpenShift 4.6 is using an older version of Argo CD.  This "Out of Sync" status does not happen in OpenShift 4.7 (OpenShift GitOps 1.0.1).  Remember, OpenShift GitOps is still *Tech Preview*, so there are still a few rough edges :)

![Cluster Argo CD deploying the Developer instance of Argo CD](images/cluster-argocd.png)

Like the cluster instance, you can login to the Developers Argo CD UI by clicking on the route that becomes available in the `argocd` project.  The default username once again is `admin` and the password can be found in the `argocd-cluster` secret. You can also get the password using the `oc` cli:

```
oc get secret argocd-cluster -n argocd -o jsonpath='{.data.admin\.password}' | base64 -d
```

Keep the Argo CD UI open so you can see the magic happen during the next few steps!

**Next:** [Install shared CI/CD Tools](03-install-shared-cicd-tools.md)