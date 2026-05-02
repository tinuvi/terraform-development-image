# Terraform development image

A batteries-included Docker image for Terraform development, with the cloud and VPN tooling you typically reach for during infrastructure work.

Published at https://hub.docker.com/r/tinuvi/terraform-development-image and built for `linux/amd64` and `linux/arm64`.

## Usage

The repository ships a `docker-compose.yml` that runs a privileged Docker daemon alongside the Terraform image, so you can build and run containers from inside the workflow:

```bash
docker compose run --rm terraform bash
```

Inside the container:

```bash
terraform version
gcloud --version
aws --version
kubectl version --client=false
```

Your working directory is mounted at `/app`.