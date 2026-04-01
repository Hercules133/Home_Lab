# scrutiny

Scrutiny S.M.A.R.T. disk-health monitoring stack.

## Stack
- Service: `scrutiny`
- Image: `ghcr.io/analogj/scrutiny:latest-omnibus`
- UI Port: `127.0.0.1:8088 -> 8080`

## Links
- Website: https://github.com/AnalogJ/scrutiny
- Docs: https://github.com/AnalogJ/scrutiny#docker
- Container image: https://github.com/AnalogJ/scrutiny/pkgs/container/scrutiny

## Run
```bash
cp .env.example .env
docker compose up -d
```

## Notes
- Official images are distributed via GHCR.
- Device access requirements depend on your disk/controller setup.
