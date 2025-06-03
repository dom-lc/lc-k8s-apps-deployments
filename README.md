# K8S Apps Deployments

Repository that mocks the lc-k8s-apps-deployments. </br></br>
*Note that this repository will be used to demonstrate concepts and does not follow the best security practices.*

## Charts/app-management

Here lives a Helm Chart to produce applicationand applicationsets for our clusters. The objective is to use this Chart to deploy our applications via an applicationset.</br>
Since we are using release-please, and want to target specific versions of our app, I decided to make the use of a list generator specifying the apps and versions to deploy.
</br></br>
To deploy the base applicationset for a cluster use:

```
helm template . -f ../../surveillance-green/applicationset-values.yaml | k apply -f -
```

## Clusters/