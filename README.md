# Home_Lab

Collection of self-hosted Docker Compose stacks for home-lab services.

## Project Status

This repository is still at an early stage.
Current goal: move every stack toward a ready-to-run setup with minimal manual steps.

Most stacks can boot, but still require post-boot application configuration.
This is especially true for `media_server/` and `ollama_webui/`.

## Compose Stack Index

| Folder | Purpose | Docs |
|---|---|---|
| `fileWizard/` | File conversion/processing utility | `fileWizard/README.md` |
| `homepage/` | Service dashboard | `homepage/README.md` |
| `immich/` | Photo/video management | `immich/README.md` |
| `media_server/` | Sonarr/Radarr/Prowlarr/qBittorrent/Readarr/Lidarr | `media_server/README.md` |
| `minecraft/` | Minecraft server | `minecraft/README.md` |
| `n8n/` | Workflow automation | `n8n/README.md` |
| `ollama_webui/` | Ollama + Open WebUI | `ollama_webui/README.md` |
| `portainer/` | Docker management UI | `portainer/README.md` |

## Quick Start

Run any stack from its folder:

```bash
cd <stack-folder>
docker compose up -d
```

For stacks requiring environment files, see the folder README first.
After first boot, complete each app's own setup wizard/configuration in the web UI.

## Configuration Audit (March 2026)

### Misconfiguration checks
- Fixed `homepage/docker-compose.yml` by adding missing top-level `services:`.
- Fixed host-port conflict between Homepage and Open WebUI by moving Homepage to `127.0.0.1:3001`.
- Fixed `immich/docker-compose.yml` `env_file` path to `.env`.
- Replaced hard-coded n8n auth credentials in `n8n/docker-compose.yml` with environment-variable based values.

### Privacy and secret checks
- Personal filesystem paths and secrets should stay in `.env` files, not in compose YAML.
- Added root `.gitignore` to prevent committing local `.env` and runtime data directories.
- Review auth-related values before publishing this repository.

## Security Notes
- Avoid exposing admin interfaces (Portainer, n8n, media apps) directly to the internet.
- Keep strong passwords in local `.env` files only.
- Be careful with `/var/run/docker.sock` mounts; they grant elevated host control.
