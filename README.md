# Config Connector

A collection of Google Cloud Config Connector (KCC) resources and Helm charts for managing GCP infrastructure as code.

## Overview

This repository contains:
- **Config Connector setup** - Core KCC configuration files
- **Helm charts** - Reusable charts for common GCP resources
- **Examples** - Ready-to-use configurations for different scenarios
- **Multi-tenant setups** - Tenant-specific configurations

## Quick Start

### 1. Setup Config Connector
```bash
kubectl apply -f config-connector/
```

### 2. Deploy Infrastructure
```bash
# Deploy a complete GKE setup (VPC + GKE Standard)
helm install my-cluster charts/examples/combined

# Or deploy individual components
helm install my-network charts/examples/network
helm install my-gke charts/examples/gke-standard
```

## Available Charts

| Chart | Description |
|-------|-------------|
| `gke-standard` | GKE Standard cluster with node pools |
| `gke-autopilot` | GKE Autopilot cluster |
| `vpc-subnet` | VPC with subnet and secondary ranges |
| `combined` | Complete setup (VPC + GKE) |

## Examples

- **`charts/examples/combined/`** - Complete GKE setup with VPC
- **`charts/examples/gke-autopilot/`** - Autopilot cluster example
- **`charts/examples/network/`** - VPC and subnet configuration

## Project Structure

```
├── config-connector/          # Core KCC setup files
├── charts/                    # Helm charts
│   ├── examples/             # Example configurations
│   ├── gke-standard/         # GKE Standard chart
│   └── gke-autopilot/        # GKE Autopilot chart
├── resources/                 # Sample resource definitions
└── tenant-*/                 # Tenant-specific configurations
```

## Prerequisites

- Kubernetes cluster with Config Connector installed
- GCP service account with appropriate permissions
- Helm 3.x

## Maintainer

Gabriel Garoz
