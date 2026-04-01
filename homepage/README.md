# homepage

Dashboard service using the `gethomepage/homepage` project.

## Project Status

This stack is runnable, but post-boot dashboard configuration is still needed.
The repository goal is to make all stacks fully ready-to-run with minimal manual setup.

## Stack
- Service: `homepage`
- Image: `ghcr.io/gethomepage/homepage:latest`
- Port: `127.0.0.1:3001 -> 3000`
- Volumes:
  - `./config:/app/config`
  - `/var/run/docker.sock:/var/run/docker.sock`

## Links
- Website: https://gethomepage.dev/
- Docs: https://gethomepage.dev/latest/
- GitHub: https://github.com/gethomepage/homepage

## Run
```bash
cp .env.example .env
docker compose up -d
```

## Optional Environment
- `HOMEPAGE_ALLOWED_HOSTS` (comma-separated hostnames/IPs)

## Notes
- Compose file requires a top-level `services:` key (fixed).
- Docker socket mount grants container visibility into local Docker; keep this trusted-only.
