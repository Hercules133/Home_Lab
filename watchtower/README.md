# watchtower

Watchtower automatic image update stack.

## Stack
- Service: `watchtower`
- Image: `containrrr/watchtower:latest`
- Polling: `WATCHTOWER_POLL_INTERVAL` seconds

## Links
- Docs: https://containrrr.dev/watchtower/
- Docker Hub: https://hub.docker.com/r/containrrr/watchtower
- GitHub: https://github.com/containrrr/watchtower

## Run
```bash
cp .env.example .env
docker compose up -d
```

## Notes
- Requires Docker socket access and therefore elevated control over Docker.
