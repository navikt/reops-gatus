# Reops Gatus

Minimal Gatus setup with low memory footprint..

## Local run

```bash
docker build -t reops-gatus .
docker run --rm -p 8080:8080 reops-gatus
```

Open http://localhost:8080

## Config

Edit `config.yaml` and add your own endpoints.

## NAIS

- Dev: `.nais/nais-dev.yaml`
- Prod: `.nais/nais-prod.yaml`

The dev workflow builds and pushes the container with `nais/docker-build-push@v0`.
NAIS will reject images from registries like `ghcr.io`, so deploy images must come
from the registry returned by that action.

The manifests are intentionally minimal and set low memory:

- request: `64Mi`
- limit: `128Mi`
