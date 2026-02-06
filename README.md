# Argo CD GitOps Repository

This repository contains Kubernetes manifests for deploying applications and infrastructure using GitOps principles with Argo CD.

## Project Structure

The repository is organized into two main directories:

- **app/**: Contains the application deployment manifests.
- **infra/**: Contains the infrastructure configuration manifests.

### Applications (`app/`)

Currently, this directory contains configuration for:

- **api**: A Go API service (`go-api-service`) deployed to the `development` namespace.

### Infrastructure (`infra/`)

This directory manages cluster-wide or shared infrastructure components:

- **cert-manager**: Configuration for Certificate Manager resources.
- **ingress**: Ingress resources for exposing services.
    - `api`
    - `argocd`
    - `grafana`
    - `nginx`

## Usage

This repository is intended to be monitored by Argo CD. Changes pushed to this repository will be automatically synchronized to the target Kubernetes cluster by Argo CD.

### Prerequisites

- Kubernetes cluster
- Argo CD installed and configured to watch this repository.

## Directory Layout

```
├── app
│   ├── api
│   │   ├── config.yaml
│   │   ├── deployment.yaml
│   │   ├── kustomization.yaml
│   │   └── service.yaml
│   └── kustomization.yaml
├── infra
│   ├── cert-manager
│   │   └── ...
│   ├── ingress
│   │   └── ...
│   └── kustomization.yaml
└── README.md
```