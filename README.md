# Benz+Walter GmbH Certificate Revocation Lists

The CRLs are located in the `src/crls` folder and are packaged into an NginX image.
To update those certificates, replace the files with the new version and rebuild the image.

The build process is automated using GitHub Actions.
Further on, on a new git tag/release, a Helm chart is built and uploaded to `ghcr.io/benz-walter/charts/crls` (https://github.com/benz-walter/charts).
