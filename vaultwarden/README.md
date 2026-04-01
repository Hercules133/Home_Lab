# vaultwarden

Vaultwarden password manager stack.

## Stack
- Service: `vaultwarden`
- Image: `vaultwarden/server:latest`
- Port: `127.0.0.1:8082 -> 80`
- Volume: `./data:/data`

## Links
- Website: https://github.com/dani-garcia/vaultwarden
- Docker Hub: https://hub.docker.com/r/vaultwarden/server
- Docs: https://github.com/dani-garcia/vaultwarden/wiki

## Run
```bash
cp .env.example .env
docker compose up -d
```

## Required Environment
- `ADMIN_TOKEN`
- `DOMAIN`

## Notes
- Run behind HTTPS before exposing to clients.
