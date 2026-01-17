# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.1.0] - 2026-01-17

### Added
- Initial release of SpacetimeDB Helm chart
- Support for persistent storage with configurable storage class
- Configurable resource requests and limits
- Support for node affinity, tolerations, and node selectors
- Optional JWT authentication support
- Health checks (liveness and readiness probes)
- Service account creation
- Values schema validation
- Comprehensive documentation

### Features
- Uses `clockworklabs/spacetime:latest` docker image
- Default ClusterIP service on port 3000
- Persistent volume support with 10Gi default size
- Security context with non-root user
- Configurable log levels and disk logging options
