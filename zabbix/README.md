# zabbix

Zabbix stack with MySQL, Zabbix server, and web frontend.

## Stack
- Services: `zabbix-mysql`, `zabbix-server`, `zabbix-web`
- Web URL: `http://127.0.0.1:8085`

## Run
```bash
cd zabbix
cp .env.example .env
docker compose up -d
```

## Recommended Environment
Create `.env` from `.env.example` in this folder and override:
- `ZABBIX_MYSQL_USER`
- `ZABBIX_MYSQL_PASSWORD`
- `ZABBIX_MYSQL_ROOT_PASSWORD`
- `ZABBIX_MYSQL_DATABASE`

## Notes
- Server trapper port `10051` is exposed on the host.
- Default example credentials should be changed for persistent deployments.
