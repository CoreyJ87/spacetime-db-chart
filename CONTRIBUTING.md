# Contributing to SpacetimeDB Helm Chart

Thank you for your interest in contributing!

## How to Contribute

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Test your changes locally:
   ```bash
   helm lint .
   helm template test . --debug
   ```
5. Commit your changes (`git commit -m 'Add some amazing feature'`)
6. Push to the branch (`git push origin feature/amazing-feature`)
7. Open a Pull Request

## Chart Guidelines

- Follow [Helm best practices](https://helm.sh/docs/chart_best_practices/)
- Update `Chart.yaml` version following [Semantic Versioning](https://semver.org/)
- Update `README.md` if adding new parameters
- Add/update tests for new features
- Ensure all tests pass before submitting PR

## Testing Locally

### Lint the chart
```bash
helm lint .
```

### Template the chart
```bash
helm template test . --debug
```

### Install locally (requires Kubernetes cluster)
```bash
helm install test . --namespace spacetimedb --create-namespace
```

## Reporting Issues

- Use GitHub Issues
- Provide clear description
- Include steps to reproduce
- Include relevant logs/output

## Code of Conduct

Be respectful and constructive in all interactions.
