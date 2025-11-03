# Athena K3s Fleet

GitOps repository for managing Kubernetes clusters with FluxCD.

## Repository Structure
```
.
├── apps/
│   ├── base/              # Base app configurations
│   ├── staging/           # Staging overlays
│   └── production/        # Production overlays
├── infrastructure/
│   ├── base/              # Base infrastructure
│   ├── staging/           # Staging overlays
│   └── production/        # Production overlays
└── clusters/
    ├── staging/
    │   ├── flux-system/   # Flux components (auto-generated)
    │   ├── infrastructure.yaml
    │   └── apps.yaml
    └── production/
        ├── flux-system/   # Flux components (auto-generated)
        ├── infrastructure.yaml
        └── apps.yaml
```

## Bootstrap

### Staging
```bash
flux bootstrap github \
  --owner=shiferaxa \
  --repository=athena-k3s-fleet \
  --branch=main \
  --personal \
  --path=clusters/staging
```

### Production
```bash
flux bootstrap github \
  --owner=shiferaxa \
  --repository=athena-k3s-fleet \
  --branch=main \
  --personal \
  --path=clusters/production
```
