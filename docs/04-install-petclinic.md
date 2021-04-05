# Create Pipelines and Application Environments

With the base infrastructure in place, it's time to move on to the Pet Clinic application!

In this step we will create three new Argo CD *Applications*.
* `petclinic-cicd` - Includes the Pet Clinic *BuildConfig, ImageStream, Tasks, and Pipelines*.
* `petclinic-dev` - All configuration for the **dev** Pet Clinic environment.
* `petclinic-prod` - All configuration for the **prod** Pet Clinic environment.

To begin deploying all of this, simply run the following command:

```
oc apply -k https://github.com/pittar-demos/gitops-and-tekton-with-openshift/gitops/argocd/04-petclinic
```

Once that is done, you will see the three new Argo CD *Applications* beginning to synchronize in the Argo CD UI. After a moment or two, the `petclinic-cicd` *Application* should be healthy and green, however, the `petclinic-dev` and `petclinic-prod` *Applications* will still by trying to progress.  It should looks like this:

![Argo CD environments progressing](images/argocd-petclinic-init.png)

Argo CD has actually done quite a bit, including:
* Creating custom Tekton *Tasks* to run maven builds, s2i builds, and tag images.
* Create a *build-and-rollout* pipeline that will:
    * Build the Pet Clinic from source
    * Run unit tests
    * Perform static code analysis and CVE scanning of dependencies
    * Build and tag the pet clinic container image
    * Deploy the pet clinic image to the *dev* and *prod* environments.
* Create *dev* and *prod* Pet Clinic environments (`petclinic-dev` and `petclinic-prod`).

You'll notice that the "petclinic-dev" and "petclinic-prod" Argo CD projects never finish "progressing".  They might even report as "unhealthy" (red).  This is expected, since we have not yet built a Pet Clinic container image, so there is nothing to deploy!  Let's fix that...

**Next:** [Start your first Pipeline Run](05-start-pipeline-run.md)