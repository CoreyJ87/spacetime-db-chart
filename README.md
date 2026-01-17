# SpacetimeDB Helm Chart

A Helm chart for deploying SpacetimeDB to Kubernetes.

## What is SpacetimeDB?

SpacetimeDB is a database + server platform built by Clockwork Labs. It lets you write application logic (called *modules*) in WebAssembly (Rust and C# supported) and upload them so that clients connect directly to the database.

## Installation

```bash
helm install spacetimedb ./spacetime-db-chart
```

Or with custom values:

```bash
helm install spacetimedb ./spacetime-db-chart \
  --set persistence.storageClass=your-storage-class \
  --set resources.requests.memory=1Gi
```

## Configuration

The following table lists the configurable parameters and their default values.

| Parameter | Description | Default |
|-----------|-------------|---------|
| `replicaCount` | Number of replicas | `1` |
| `image.repository` | Image repository | `clockworklabs/spacetime` |
| `image.tag` | Image tag | `latest` |
| `image.pullPolicy` | Image pull policy | `Always` |
| `persistence.enabled` | Enable persistence | `true` |
| `persistence.storageClass` | Storage class (uses cluster default if empty) | `""` |
| `persistence.size` | Storage size | `10Gi` |
| `spacetimedb.inMemory` | Run in memory mode (no persistence) | `false` |
| `spacetimedb.logLevel` | Log level | `info` |
| `resources.requests.memory` | Memory request | `512Mi` |
| `resources.requests.cpu` | CPU request | `500m` |
| `resources.limits.memory` | Memory limit | `2Gi` |
| `resources.limits.cpu` | CPU limit | `2000m` |

## JWT Authentication

To enable JWT authentication, create a Kubernetes secret with your private and public keys:

```bash
kubectl create secret generic spacetimedb-jwt-keys \
  --from-file=id_ecdsa=./private_key \
  --from-file=id_ecdsa.pub=./public_key
```

Then enable JWT in your values:

```yaml
jwt:
  enabled: true
  secretName: spacetimedb-jwt-keys
```

## Documentation

For more information, visit: https://spacetimedb.com/docs/
# spacetime-db-chart
