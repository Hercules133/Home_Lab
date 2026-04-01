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
| `homeAssistant/` | Home Assistant container | `homeAssistant/README.md` |
| `homepage/` | Service dashboard | `homepage/README.md` |
| `immich/` | Photo/video management | `immich/README.md` |
| `actual_budget/` | Actual Budget local-first finance app | `actual_budget/README.md` |
| `audiobookshelf/` | Audiobook and podcast server | `audiobookshelf/README.md` |
| `authentik/` | SSO and identity provider | `authentik/README.md` |
| `authelia/` | SSO/access control portal | `authelia/README.md` |
| `crowdsec/` | Behavior-based security engine | `crowdsec/README.md` |
| `hoarder/` | Hoarder/Karakeep bookmark manager | `hoarder/README.md` |
| `media_server/` | Sonarr/Radarr/Prowlarr/qBittorrent/Readarr/Lidarr | `media_server/README.md` |
| `mealie/` | Recipe manager and meal planner | `mealie/README.md` |
| `minecraft/` | Minecraft server | `minecraft/README.md` |
| `n8n/` | Workflow automation | `n8n/README.md` |
| `nginx_proxy_manager/` | Nginx Proxy Manager reverse proxy | `nginx_proxy_manager/README.md` |
| `netBox/` | NetBox + Postgres + Valkey | `netBox/README.md` |
| `nzyme/` | nzyme (community image) | `nzyme/README.md` |
| `ollama_webui/` | Ollama + Open WebUI | `ollama_webui/README.md` |
| `pdftools/` | Stirling-PDF | `pdftools/README.md` |
| `portainer/` | Docker management UI | `portainer/README.md` |
| `paperless_ngx/` | Document management and OCR workflow | `paperless_ngx/README.md` |
| `scrutiny/` | S.M.A.R.T. disk health dashboard | `scrutiny/README.md` |
| `uptime_kuma/` | Uptime and endpoint monitoring | `uptime_kuma/README.md` |
| `vaultwarden/` | Bitwarden-compatible password manager | `vaultwarden/README.md` |
| `vikunja/` | Project/task management | `vikunja/README.md` |
| `wazuh/` | Wazuh single-node (manager/indexer/dashboard) | `wazuh/README.md` |
| `watchtower/` | Automated container update watcher | `watchtower/README.md` |
| `zabbix/` | Zabbix + MySQL | `zabbix/README.md` |

## Roadmap Status

> Disclaimer: This roadmap status section is 100% AI-generated and should be reviewed/validated manually before production use.

| Project | Category | Why add it? | Status |
|---|---|---|---|
| `Nginx Proxy Manager` | Networking | Simplifies SSL and custom domains. | Baseline stack added (`nginx_proxy_manager/`) |
| `Uptime Kuma` | Monitoring | Instant alerts when a container crashes. | Baseline stack added (`uptime_kuma/`) |
| `Vaultwarden` | Security | Secure, self-hosted password storage. | Baseline stack added (`vaultwarden/`) |
| `Paperless-ngx` | Productivity | Digitizes all your physical mail/records. | Baseline stack added (`paperless_ngx/`) |
| `Authentik` | Security | Centralized SSO with MFA for self-hosted apps. | Baseline stack added (`authentik/`) |
| `Authelia` | Security | Lightweight alternative for SSO and access control in front of services. | Baseline stack added (`authelia/`) |
| `CrowdSec` | Security | Detects and blocks malicious IPs using behavior-based log analysis. | Baseline stack added (`crowdsec/`) |
| `Watchtower` | Monitoring | Automatically updates running containers when new images are available. | Baseline stack added (`watchtower/`) |
| `Scrutiny` | Monitoring | S.M.A.R.T. disk health dashboard and early failure alerting. | Baseline stack added (`scrutiny/`) |
| `Audiobookshelf` | Media | Self-hosted audiobook and podcast server with progress sync. | Baseline stack added (`audiobookshelf/`) |
| `Mealie` | Productivity | Recipe manager and meal planner with web-recipe import. | Baseline stack added (`mealie/`) |
| `Actual Budget` | Productivity | Privacy-focused local-first personal finance management. | Baseline stack added (`actual_budget/`) |
| `Vikunja` | Productivity | Flexible project and task management (Kanban, lists, timeline). | Baseline stack added (`vikunja/`) |
| `Hoarder` | Productivity | AI-powered bookmark manager with auto-tagging (can integrate with local LLMs). | Baseline stack added (`hoarder/`) |

## Quick Start

Run any stack from its folder:

```bash
cd <stack-folder>
docker compose up -d
```

For stacks requiring environment files, see the folder README first.
After first boot, complete each app's own setup wizard/configuration in the web UI.

Most environment-driven stacks now include `.env.example` templates.

## Configuration Audit (March 2026)

### Misconfiguration checks
- Fixed `homepage/docker-compose.yml` by adding missing top-level `services:`.
- Fixed host-port conflict between Homepage and Open WebUI by moving Homepage to `127.0.0.1:3001`.
- Fixed `immich/docker-compose.yml` `env_file` path to `.env`.
- Replaced hard-coded n8n auth credentials in `n8n/docker-compose.yml` with environment-variable based values.
- Removed deprecated `version` key from `minecraft/docker-compose.yml`.
- Added missing restart policy to `fileWizard/docker-compose.yml`.
- Added official single-node layout files for `wazuh/` (`docker-compose.yml`, cert generator, and required config files).
- Made `netBox/` and `zabbix/` credentials configurable via environment variables.

### Privacy and secret checks
- Personal filesystem paths and secrets should stay in `.env` files, not in compose YAML.
- Added root `.gitignore` to prevent committing local `.env` and runtime data directories.
- Review auth-related values before publishing this repository.
- `wazuh/` ships with official example credentials by default; rotate them before exposing outside trusted networks.

## Stack-Specific Prerequisites

- `immich/`: requires local `.env` with upload/database paths and DB credentials.
- `netBox/`: set `NETBOX_SECRET_KEY`, `NETBOX_DB_PASSWORD`, `NETBOX_REDIS_PASSWORD`.
- `wazuh/`: run `sudo sysctl -w vm.max_map_count=262144`, then generate certs with `docker compose -f generate-indexer-certs.yml run --rm generator` before `docker compose up -d`.
- `zabbix/`: recommended to override default DB credentials via `.env` (`ZABBIX_MYSQL_*`).

## Security Notes
- Avoid exposing admin interfaces (Portainer, n8n, media apps) directly to the internet.
- Keep strong passwords in local `.env` files only.
- Be careful with `/var/run/docker.sock` mounts; they grant elevated host control.
