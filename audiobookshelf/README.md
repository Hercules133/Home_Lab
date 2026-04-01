# audiobookshelf

Audiobookshelf audiobook and podcast server stack.

## Stack
- Service: `audiobookshelf`
- Image: `advplyr/audiobookshelf:latest`
- Port: `127.0.0.1:13378 -> 80`

## Links
- Website: https://www.audiobookshelf.org/
- Docker Hub: https://hub.docker.com/r/advplyr/audiobookshelf
- GitHub: https://github.com/advplyr/audiobookshelf

## Run
```bash
docker compose up -d
```

## Notes
- Websocket support is required when running behind a reverse proxy.
