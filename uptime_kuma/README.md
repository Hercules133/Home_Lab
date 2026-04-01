# uptime_kuma

Uptime Kuma monitoring stack.

## Stack
- Service: `uptime_kuma`
- Image: `louislam/uptime-kuma:2`
- Port: `127.0.0.1:3002 -> 3001`
- Volume: `./data:/app/data`

## Links
- Website: https://uptime.kuma.pet/
- Docker Hub: https://hub.docker.com/r/louislam/uptime-kuma
- GitHub: https://github.com/louislam/uptime-kuma

## Run
```bash
docker compose up -d
```

## Notes
- The image maintainer recommends versioned tags instead of `latest`.
