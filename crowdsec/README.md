# crowdsec

CrowdSec security engine stack.

## Stack
- Service: `crowdsec`
- Image: `crowdsecurity/crowdsec:latest`
- API Port: `127.0.0.1:8081 -> 8080`

## Links
- Website: https://www.crowdsec.net/
- Docker Hub: https://hub.docker.com/r/crowdsecurity/crowdsec
- Docs: https://docs.crowdsec.net/u/getting_started/installation/docker/

## Run
```bash
cp .env.example .env
docker compose up -d
```

## Notes
- Persistent mount of `/var/lib/crowdsec/data` is required.
- Add acquisition files under `config/` as you onboard more log sources.
