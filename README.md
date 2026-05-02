# Builder

This repository is the public distribution surface for Builder.

It intentionally contains only:

- `README.md`
- `compose.yaml`
- published release artifacts

The source code stays in the private upstream repository.

## Quick start

```bash
# Start the local PostgreSQL dependency
docker compose -f compose.yaml up -d postgres

# Download the Builder binary from the Releases page for this repository
# and make it executable. Rename the downloaded asset to `builder` or run it
# by its downloaded filename.

export BUILDER_DATABASE_URL="postgres://postgres:postgres@127.0.0.1:1207/builder"
./builder --help
```

## Release layout

The public release should publish the platform binaries under the release assets
for this repository. The binary names follow the existing release matrix:

- `builder-x86_64-unknown-linux-musl`
- `builder-aarch64-unknown-linux-musl`
- `builder-x86_64-unknown-linux-gnu`
- `builder-aarch64-unknown-linux-gnu`
- `builder-x86_64-apple-darwin`
- `builder-aarch64-apple-darwin`
- `builder-x86_64-pc-windows-msvc.exe`
- `builder-aarch64-pc-windows-msvc.exe`
- `builder-aarch64-linux-android`

## What is private

- Source code
- Internal CI wiring
- Private release automation
