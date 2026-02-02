# Code Server Go

A Helm chart for deploying a Golang-based code server for internal use.

## Installation

### Prerequisites

- Kubernetes cluster
- Helm 3.x

### Install the chart

```bash
helm install code-server-go ./code-server-go
```

### Uninstall the chart

```bash
helm uninstall code-server-go
```

## Configuration

The following table lists the configurable parameters of the code-server-go chart and their default values.

| Parameter | Description | Default |
|-----------|-------------|---------|
| `replicaCount` | Number of replicas | `1` |
| `image.repository` | Image repository | `golang` |
| `image.tag` | Image tag | `latest` |
| `image.pullPolicy` | Image pull policy | `IfNotPresent` |
| `service.http.type` | HTTP service type | `NodePort` |
| `service.http.port` | HTTP service port | `8080` |
| `service.http.nodePort` | HTTP node port | `10880` |
| `service.ssh.type` | SSH service type | `NodePort` |
| `service.ssh.port` | SSH service port | `22` |
| `service.ssh.nodePort` | SSH node port | `10822` |
| `codeServer.enabled` | Enable code-server | `true` |
| `codeServer.password` | Code-server password | `password` |
| `ingress.enabled` | Enable ingress | `false` |
| `persistence.enabled` | Enable persistence | `false` |
| `persistence.size` | PVC size | `10Gi` |

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

Alternatively, a YAML file that specifies the values for the parameters can be provided while installing the chart.

```bash
helm install code-server-go ./code-server-go -f values.yaml
```

## Persistence

Currently, persistence is disabled by default. To enable persistent storage, set `persistence.enabled=true` in your values file. Please commit and push your changes regularly as data may not be persisted otherwise.

## Version

Chart version: 1.0.2  
App version: v4.100.2
