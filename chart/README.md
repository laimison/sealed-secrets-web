# sealed-secrets-web

![Version: 2.8.4](https://img.shields.io/badge/Version-2.8.4-informational?style=flat-square) ![AppVersion: v2.8.4](https://img.shields.io/badge/AppVersion-v2.8.4-informational?style=flat-square)

A web interface for Sealed Secrets by Bitnami.

## Installation

```console
helm repo add bakito https://charts.bakito.net
helm install sealed-secrets-web bakito/sealed-secrets-web
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` | Assign custom [affinity] rules to the deployment |
| disableLoadSecrets | bool | `false` | If set to true secrets cannot be read from this tool, only seal new ones |
| format | string | `"yaml"` | Secret format - either json or yaml |
| fullnameOverride | string | `""` | String to fully override "argo-rollouts.fullname" template |
| image.pullPolicy | string | `"IfNotPresent"` | Image pull policy |
| image.repository | string | `"ghcr.io/bakito/sealed-secrets-web"` | Repository to use |
| image.tag | string | `nil` | Overrides the image tag (default is the chart appVersion) |
| imagePullSecrets | list | `[]` | Secrets with credentials to pull images from a private registry. Registry secret names as an array. |
| includeLocalNamespaceOnly | bool | `false` | If set to true, the application has only the permission to view sealed secrets in the current namespace |
| ingress.annotations | object | `{}` | Ingress annotations |
| ingress.className | string | `""` | Ingress class name |
| ingress.defaultTls | bool | `false` | set this to true and leave tls an empty array to use the default TLS certificate (works at least in openshift) |
| ingress.enabled | bool | `false` | Enable ingress support |
| ingress.hosts | list | `[]` | Ingress hosts |
| ingress.tls | list | `[]` | Ingress tls |
| initialSecretFile | string | `nil` | Define you custom initial secret file |
| nameOverride | string | `""` | String to partially override "argo-rollouts.fullname" template |
| nodeSelector | object | `{}` | [Node selector] |
| rbac.create | bool | `true` | Specifies whether rbac should be created |
| replicaCount | int | `1` | The number of pods to run |
| resources | object | `{}` | Resource limits and requests for the pods. |
| sealedSecrets.certURL | string | `""` | URL sealed secrets certificate (required if sealed secrets is not reachable with in cluster service) |
| sealedSecrets.namespace | string | `"sealed-secrets"` | Namespace of the sealed secrets service |
| sealedSecrets.serviceName | string | `"sealed-secrets"` | Name of the sealed secrets service |
| service.port | int | `80` | Service port |
| service.type | string | `"ClusterIP"` | Sets the type of the Service |
| serviceAccount.create | bool | `true` | Specifies whether a service account should be created |
| serviceAccount.name | string | `"sealed-secrets-web"` | The name of the service account to use. |
| tolerations | list | `[]` | [Tolerations] for use with node taints |
| volumeMounts | list | `[]` | Additional volumeMounts to the image updater main container |
| volumes | list | `[]` | Additional volumes to the image updater pod |
| webContext | string | `nil` | Secret format - either json or yaml |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs](https://github.com/norwoodj/helm-docs)