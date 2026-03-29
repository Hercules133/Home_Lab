# fileWizard

Small file conversion/processing utility based on `loredcast/filewizard`.

## Project Status

This stack is runnable, but post-boot checks/configuration may still be needed.
The repository goal is to make all stacks fully ready-to-run with minimal manual setup.

## Stack
- Service: `filewizard`
- Image: `loredcast/filewizard:latest`
- Port: `6969 -> 8000`
- Volumes:
  - `./uploads_data:/app/uploads`
  - `./processed_data:/app/processed`

## Links
- Website: https://loredcast.github.io/
- GitHub: https://github.com/loredcast/filewizard
- Docker image: https://hub.docker.com/r/loredcast/filewizard

## Run
```bash
docker compose up -d
```

## Notes
- `LOCAL_ONLY=True` keeps access local by default.
- Do not commit uploaded/processed runtime data.
