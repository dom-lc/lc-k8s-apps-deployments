# lc-k8s-apps-deployments

Repository that mocks the lc-k8s-apps-deployments. </br></br>
*Note that this repository will be used to demonstrate concepts and does not follow the best security practices.*

## Charts/app-management

Here lives a Helm Chart to produce applicationand applicationsets for our clusters. The objective is to use this Chart to deploy our applications via an applicationset using a git generator, hence producing our applications automatically for all path in our charts/* sub-directories.

</br></br>
To deploy the base applicationset for a cluster use:

```
helm template . -f ../../clusters/surveillance-green/applicationset-values.yaml | k apply -f -
```

## Clusters/

The cluster directorycontains subdirectories with our cluster names. In each clusters name directory, you will find the desired values to apply to the app-management Chart.

## Problematics

Since I am generating the applications with the applicationset via the git generator and an exprission to englobe all the paths, I can not point to a specific revision. Now it is time to propose a solution for managing the target revision for release-please.