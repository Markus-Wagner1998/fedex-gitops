# FedEx GitOps Repository

This repository contains the GitOps configuration for managing our Kubernetes cluster using Flux CD.

## Structure

- `flux-system/` - Core Flux components and configuration
- `vault/` - HashiCorp Vault deployment via Helm

## Vault Deployment

Added HashiCorp Vault deployment using Helm chart with the following features:
- Standalone Vault server (version 1.13.1)
- Vault Injector for Kubernetes integration
- Vault UI enabled
- Resource limits and requests configured
- Node affinity and tolerations for master nodes
- Proper namespace creation and management

### Deployment Steps
1. Flux will automatically deploy Vault from the `vault/` directory
2. Vault will be installed in the `vault` namespace
3. Access the Vault UI via service `vault-ui.vault.svc.cluster.local`

### Configuration
- Helm chart: hashicorp/vault (version 0.24.0)
- Server image: hashicorp/vault:1.13.1
- Injector image: hashicorp/vault-k8s:1.1.0