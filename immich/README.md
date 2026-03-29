# immich

Self-hosted photo and video management stack.

## Project Status

This stack is runnable, but post-boot Immich configuration is still needed.
The repository goal is to make all stacks fully ready-to-run with minimal manual setup.

## Stack
- Services:
  - `immich-server`
  - `immich-machine-learning`
  - `redis`
  - `database`
- Main Port: `2283 -> 2283`
- Volumes:
  - `${UPLOAD_LOCATION}:/data`
  - `${DB_DATA_LOCATION}:/var/lib/postgresql/data`
  - `${EXTERNAL_LIBRARY_LOCATION}:/external:ro`

## Links
- Website: https://immich.app/
- Docs: https://immich.app/docs/install/docker-compose
- GitHub: https://github.com/immich-app/immich

## Run
```bash
docker compose up -d
```

## Required Environment
- File: `.env` in this folder
- Important keys:
  - `UPLOAD_LOCATION`
  - `DB_DATA_LOCATION`
  - `IMMICH_VERSION`
  - `DB_PASSWORD`
  - `DB_USERNAME`
  - `DB_DATABASE_NAME`
  - `EXTERNAL_LIBRARY_LOCATION`

## Notes
- `env_file` now points to `.env` (fixed).
- Never commit private media paths or real database passwords.
