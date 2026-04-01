# authelia

Authelia SSO and access-control stack.

## Stack
- Services: `authelia`, `authelia_redis`
- Main image: `authelia/authelia:latest`
- Port: `127.0.0.1:9091 -> 9091`

## Links
- Website: https://www.authelia.com/
- Docker Hub: https://hub.docker.com/r/authelia/authelia
- GitHub: https://github.com/authelia/authelia

## Run
```bash
cp .env.example .env
docker compose up -d
```

## Required Files
- `config/configuration.yml`
- `config/users_database.yml`

## Notes
- Replace the placeholder password hash in `config/users_database.yml` before production.
- This is a baseline deployment that you should integrate behind a reverse proxy.
