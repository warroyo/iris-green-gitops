# Iris green gitops

This repo is part of the [TMC Multitentant flux example](https://github.com/warroyo/flux-tmc-multitenant). This is the Iris green team's boootstrap repo. This is the intial repo that will be configured to be synced when a tenant is created. The team can use this repo to control namespaces in the clusters as well as add other `kustomizations` to deploy their apps.


## Repo structure

see the repo structure details in the main repo [here](https://github.com/warroyo/flux-tmc-multitenant#tenant-repo-structure)


## Usage

### Namespaces

This allows for namespace self service. Place any namespace configs under the `/clusters/<clustername>/namespaces/` directory and they will be automatically created.

example namespace config:

```yaml
apiVersion: tmc.tanzufield.vmware.com/v1
kind: TMCNamespace
metadata:
  name: iris-green-apps
  labels:
    version: v1
spec:
  fullName:
    name: iris-green-apps
  meta:
    labels:
      team: iris-green
```


### 