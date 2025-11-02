# Flux GitOps Repository

This repository follows Flux best practices for GitOps-based Kubernetes deployments.

## Structure
```
├── clusters/          # Cluster configurations (entry points)
│   ├── production/
│   ├── staging/
│   └── development/
├── infrastructure/    # Platform services (ingress, monitoring, etc.)
│   ├── base/
│   ├── production/
│   ├── staging/
│   └── development/
└── apps/             # Application deployments
    ├── base/
    ├── production/
    ├── staging/
    └── development/
```

## Getting Started

1. Install Flux CLI: https://fluxcd.io/flux/installation/
2. Bootstrap Flux to your cluster:
```bash
   flux bootstrap github \
     --owner=<github-username> \
     --repository=<repo-name> \
     --branch=main \
     --path=clusters/production \
     --personal
```

## Workflow

1. Add your infrastructure components to `infrastructure/base/`
2. Add your applications to `apps/base/`
3. Create environment-specific overlays in respective directories
4. Commit and push - Flux will automatically sync!
