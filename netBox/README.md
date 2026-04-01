# netBox

NetBox stack with PostgreSQL and Valkey.

## Stack
- Services: `netBox`, `netbox-worker`, `netbox-postgres`, `netbox-redis`
- Main URL: `http://127.0.0.1:8000`

## Run
```bash
cd netBox
cp .env.example .env
docker compose up -d
```

## Recommended Environment
Set these before first run (in `.env`, starting from `.env.example`):
- `NETBOX_SECRET_KEY`
- `NETBOX_DB_PASSWORD`
- `NETBOX_REDIS_PASSWORD`

## First Login
Create an admin user:
```bash
docker compose exec netBox /opt/netbox/netbox/manage.py createsuperuser
```
