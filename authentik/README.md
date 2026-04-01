# authentik

authentik SSO and identity provider stack.

## Stack
- Services: `authentik_server`, `authentik_worker`, `authentik_postgresql`, `authentik_redis`
- Main image: `ghcr.io/goauthentik/server`
- URL: `http://127.0.0.1:9000`

## Links
- Website: https://goauthentik.io/
- Install docs: https://docs.goauthentik.io/install-config/install/docker-compose/
- GitHub: https://github.com/goauthentik/authentik

## Run
```bash
cp .env.example .env
docker compose up -d
```

## Required Environment
- `PG_PASS`
- `AUTHENTIK_SECRET_KEY`

## Notes
- Official docs provide generated compose files; this repository keeps a local baseline stack.
- Docker socket mount is optional but required for automatic Docker outpost management.
