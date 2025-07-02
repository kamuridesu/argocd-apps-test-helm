# ArgoCD Helm Tests

## Folder structure

The charts folder will store all charts needed for our projects. For example, we have an ArgoCD chart that is an umbrella chart for ArgoCD to be able to manage itself.

The `apps` folder contains the default manifest which is an entrypoint to manage other resources such as the ArgoCD itself.

On the `root` we have some Applications pointing to the configs to be applied.

The `structure` folder stores some management files for ArgoCD like groups and ApplicationSets.

On `values` I put my values files for my Helm Chart. It's structured like: `values/namespace/values.yaml`, where namespace will be the namespace for the project.

# Info

This project is part of a series of study about Kubernetes on ARM, cloud, ArgoCD, Helm, Ansible and much more. All the information about the project is stored in the https://github.com/kamuridesu/oracle-k3s-config
