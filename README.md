# Benz+Walter GmbH Certificate Revocation Lists

The CRLs are located in the `src/crls` folder and are packaged into an NginX image.
To update those certificates, replace the files with the new version and rebuild the image.

The build process is automated using GitHub Actions.
Further on, on a new git tag/release, a Helm chart is built and uploaded to `ghcr.io/benz-walter/charts/benz-walter-crls` (https://github.com/benz-walter/charts).

## Deployment

See `helm/values.yaml` for a list of possible values.

At least `ingress.host` should be adjusted for deployment.

Install via:
```bash
helm install benz-walter-crls --set ingress.host="...." oci://ghcr.io/benz-walter/charts/benz-walter-crls
```

Upgrade via (reusing previous values):
```bash
helm upgrade benz-walter-crls --reuse-values oci://ghcr.io/benz-walter/charts/benz-walter-crls
```
