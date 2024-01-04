# ArgoCD Helm Tests

## Folder structure

The charts folder will store all charts needed for our projects. For example, we have an ArgoCD chart that is an umbrella chart for ArgoCD to be able to manage itself.

Apps folder contains informations about ArgoCD applications files, defining the location where the kuberentes files are stored.

There'll be a projects folder that will be organized by namespace, where each namespace contains the projects that will be run on our Kubernetes cluster.

# Info

This project is part of a series of study about Kubernetes on ARM, cloud, ArgoCD, Helm, Ansible and much more. All the information about the project is stored in the https://github.com/kamuridesu/oracle-k3s-config
