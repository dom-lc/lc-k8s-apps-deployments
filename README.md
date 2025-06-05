# K8S Apps Deployments

Repository that mocks the lc-k8s-apps-deployments. </br></br>
*Note that this repository will be used to demonstrate concepts and does not follow the best security practices.*

## Charts/app-management

Here lives a Helm Chart to produce applicationand applicationsets for our clusters. The objective is to use this Chart to deploy our applications via an applicationset.</br>
Since we are using release-please, and want to target specific versions of our app, I decided to make the use of a list generator specifying the apps and versions to deploy.
</br></br>
To deploy the base applicationset for a cluster use:

```
k apply -f ./clusters/<desired-cluster-name>/do_not_touch/management.application.yaml
```

## Clusters/

The ```./clusters``` directory contains sub-directories nammed as our clusters. In each cluster sub-directory are the values for ou Helmapp-management Chart. This chart will be deployed by the application defined in the cluster ```/do_not_touch/management.application.yaml```. 

## Testing a New Application

In order to test a new application, first create a branch for your new application. Copy the ```./templates/new-application.yaml``` and paste it in the ```./clusters/surveillance-green/``` folder. Fill in your application name and branch name.