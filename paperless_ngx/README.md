# paperless_ngx

Paperless-ngx document management stack.

## Stack
- Services: `paperless`, `paperless_db`, `paperless_redis`
- Main image: `paperlessngx/paperless-ngx:latest`
- URL: `http://127.0.0.1:8002`

## Links
- Website: https://paperless-ngx.readthedocs.io/
- Docker Hub: https://hub.docker.com/r/paperlessngx/paperless-ngx
- GitHub: https://github.com/paperless-ngx/paperless-ngx

## Run
```bash
cp .env.example .env
docker compose up -d
```

## Required Environment
- `PAPERLESS_SECRET_KEY`
- `PAPERLESS_DB_PASSWORD`
- `PAPERLESS_ADMIN_PASSWORD`

## Notes
- Put files to import into `./consume`.
