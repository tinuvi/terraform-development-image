# Terraform development image

A batteries-included Docker image for Terraform development, with the cloud and VPN tooling you typically reach for during infrastructure work.

Published at https://hub.docker.com/r/tinuvi/terraform-development-image and built for `linux/amd64` and `linux/arm64`.

## What's inside

- Terraform `1.15.1`
- Docker CLI (base image: `docker:28.5.0-alpine3.22`)
- AWS CLI
- Google Cloud CLI (`gcloud`, `gsutil`, `bq`)
- GitHub CLI (`gh`)
- Git, OpenSSH, `sshpass`, OpenVPN
- Python 3 with `pip` (system-packages override enabled)
- Utilities: `bash`, `vim`, `curl`, `wget`, `unzip`, `jq`, `groff`, `mandoc`

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
```

Your working directory is mounted at `/app`.