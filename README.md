# Builder

Builder is a runtime-owned coding agent CLI. The runtime, not the model, owns routing, tool policy, verification, and completion.

## Quick start

```bash
# 1. Start PostgreSQL + Builder via Docker Compose
curl -O https://raw.githubusercontent.com/agnusdei1207/builder/main/compose.yaml
docker compose up -d

# 2. Run builder in your project directory
BUILDER_PROJECT_DIR=$(pwd) docker compose run builder
```

## Binary downloads

Platform binaries are published on [GitHub Releases](https://github.com/agnusdei1207/builder/releases).

```bash
curl -LO https://github.com/agnusdei1207/builder/releases/latest/download/builder-x86_64-unknown-linux-musl
chmod +x builder-x86_64-unknown-linux-musl
./builder-x86_64-unknown-linux-musl --help
```

## Docker image

```bash
docker pull agnusdei1207/builder:latest
docker run --rm -it -v "$(pwd):/workspace" -w /workspace agnusdei1207/builder:latest
```
