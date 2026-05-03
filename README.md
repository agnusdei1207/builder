# Builder

This repository is the public distribution surface for Builder.

## Quick start

```bash
# Clone this repo (or just download compose.yaml)
curl -O https://raw.githubusercontent.com/agnusdei1207/builder/main/compose.yaml

# Start PostgreSQL + Builder
docker compose up -d

# Run builder in your project directory
BUILDER_PROJECT_DIR=/path/to/your/project docker compose run builder

# Or run with arguments
docker compose run builder --help
```

## Docker image

The official Docker image is available on Docker Hub:

```bash
docker pull agnusdei1207/builder:latest
```

### Run standalone (without compose)

```bash
docker run --rm -it \
  -v "$(pwd):/workspace" \
  -w /workspace \
  -e BUILDER_DATABASE_URL="postgres://postgres:postgres@host.docker.internal:1207/builder" \
  agnusdei1207/builder:latest
```

## What's included

| Component | Description |
|---|---|
| `compose.yaml` | Docker Compose with PostgreSQL + Builder |
| Docker image | `agnusdei1207/builder:latest` on Docker Hub |
| GitHub Releases | Platform-specific binaries mirrored from the private release pipeline |

## Binary downloads

Platform binaries are published on the public GitHub Releases page:

```bash
curl -LO https://github.com/agnusdei1207/builder/releases/download/<version>/builder-x86_64-unknown-linux-gnu
chmod +x builder-x86_64-unknown-linux-gnu
./builder-x86_64-unknown-linux-gnu --help
```

## Architecture

- **Runtime**: Ubuntu 24.04 minimal (~80 MB image)
- **Database**: PostgreSQL 18 + pgvector
- **Volume mount**: Your local project is mounted at `/workspace`

## What is private

- Source code
- Internal CI wiring
- Private release automation
