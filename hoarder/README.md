# hoarder

Hoarder/Karakeep bookmark manager stack.

## Stack
- Services: `hoarder`, `hoarder_chrome`, `hoarder_meilisearch`
- Main image: `ghcr.io/karakeep-app/karakeep`
- URL: `http://127.0.0.1:3010`

## Links
- Website: https://karakeep.app/
- Install docs: https://docs.karakeep.app/installation/docker/
- GitHub: https://github.com/karakeep-app/karakeep

## Run
```bash
cp .env.example .env
docker compose up -d
```

## Required Environment
- `NEXTAUTH_SECRET`
- `MEILI_MASTER_KEY`
- `NEXTAUTH_URL`

## Notes
- Project was previously named Hoarder and is now Karakeep.
- Official images are published on GHCR.
