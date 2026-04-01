# vikunja

Vikunja task/project management stack.

## Stack
- Services: `vikunja`, `vikunja_db`, `vikunja_redis`
- Main image: `vikunja/vikunja:latest`
- URL: `http://127.0.0.1:3456`

## Links
- Website: https://vikunja.io/
- Docker Hub: https://hub.docker.com/r/vikunja/vikunja
- Docs: https://vikunja.io/docs/installing/#docker

## Run
```bash
cp .env.example .env
docker compose up -d
```

## Required Environment
- `VIKUNJA_SERVICE_JWTSECRET`
- `VIKUNJA_DB_PASSWORD`
- `VIKUNJA_DB_ROOT_PASSWORD`
