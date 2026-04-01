# nzyme

nzyme stack using a community Docker image.

## Stack
- Service: `nzyme`
- Image: `graafnet/nzyme-node:latest`
- URL: `http://127.0.0.1:8090`
- Volume: `./data:/var/lib/nzyme`

## Run
```bash
cd nzyme
docker compose up -d
```

## Note
- No clearly documented official `nzymedefense/*` Docker Hub image was found. This setup uses a community image and may require adjustments depending on your nzyme version/feature needs.
