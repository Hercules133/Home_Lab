# wazuh

Official Wazuh single-node layout (`v4.14.4`) with manager, indexer, and dashboard.

## Files
- `docker-compose.yml`
- `generate-indexer-certs.yml`
- `config/` (cluster, indexer, dashboard config)

## Prerequisite
```bash
sudo sysctl -w vm.max_map_count=262144
```

## Run
```bash
cd wazuh
docker compose -f generate-indexer-certs.yml run --rm generator
docker compose up -d
```

## Access
- Dashboard: `https://<host-ip>`
- Default user: `admin`
- Default password: `SecretPassword`

## Notes
- This stack includes default credentials from official examples; change them before internet exposure.
