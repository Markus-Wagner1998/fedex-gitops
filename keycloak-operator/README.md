# Keycloak Operator

This directory contains the configuration to install the Keycloak Operator using Helm through FluxCD.

## Installation

The Keycloak Operator is installed using the official Helm chart from CodeCentric:
- Helm Repository: https://codecentric.github.io/helm-charts
- Chart Name: keycloak-operator
- Version: 19.0.1

## Configuration

Customize the `helm-release.yaml` file to adjust:
- Image tags
- Replicas
- Resource limits
- Other operator-specific settings

## Usage

After installation, you can create Keycloak instances using the CustomResourceDefinition:
```yaml
apiVersion: keycloak.org/v1alpha1
kind: Keycloak
metadata:
  name: example-keycloak
spec:
  instances: 1
```