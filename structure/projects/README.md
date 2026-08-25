# ArgoCD Projects

Five AppProjects, replacing the old wildcard `default`/`tooling` projects:

- `default.yaml`: overrides Argo CD's built-in wildcard `default` project down to only what the
  bootstrap `apps/default.yml` Application needs (create the root/templates/ Applications) - see
  the comment in that file for why the bootstrap Application can't reference a custom project.
- `platform.yaml`: Cilium, Gateway API CRDs, cert-manager, external-secrets, ArgoCD itself, and
  this directory's own structural bootstrap (AppProjects/ApplicationSets/coredns/certificates).
- `observability.yaml`: Grafana and Datadog.
- `secrets.yaml`: the `argocd-k3s-secrets` repo only, restricted to
  `ExternalSecret`/`SecretStore`/`ClusterSecretStore`/`PushSecret` kinds - no ability to create
  Deployments, RBAC, etc.
- `workloads.yaml`: every app deployed from `values/` via `kamuchart`, restricted to the fixed set
  of namespaces `structure/apps/apps.yaml` actually generates and to the resource kinds
  `kamuchart` can render.

Each restricts `sourceRepos`, `destinations`, and `clusterResourceWhitelist` (and, for
`secrets`/`workloads`, `namespaceResourceWhitelist`) explicitly instead of using `"*"` - a
misconfigured or compromised app in one project can't touch another project's namespaces or
create cluster-scoped resources it has no business creating.

Reference:

<https://argo-cd.readthedocs.io/en/stable/user-guide/projects/>
