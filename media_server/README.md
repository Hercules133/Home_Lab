# media_server

Media automation stack based on LinuxServer containers.

## Project Status

This stack needs post-boot configuration after startup (indexers, download client, root folders, quality profiles, app-to-app integration).
The repository goal is to make all stacks fully ready-to-run with minimal manual setup.

## Stack
- Services:
  - `sonarr` (TV)
  - `radarr` (Movies)
  - `prowlarr` (Indexers)
  - `qbittorrent` (Downloads)
  - `readarr` (Books)
  - `lidarr` (Music)
- Ports (localhost only):
  - Sonarr: `127.0.0.1:8989`
  - Radarr: `127.0.0.1:7878`
  - Prowlarr: `127.0.0.1:9696`
  - qBittorrent: `127.0.0.1:8080`
  - Readarr: `127.0.0.1:8787`
  - Lidarr: `127.0.0.1:8686`
- Network: `media_net`

## Links
- Sonarr: https://sonarr.tv/ and https://github.com/Sonarr/Sonarr
- Radarr: https://radarr.video/ and https://github.com/Radarr/Radarr
- Prowlarr: https://wiki.servarr.com/prowlarr and https://github.com/Prowlarr/Prowlarr
- qBittorrent: https://www.qbittorrent.org/ and https://github.com/qbittorrent/qBittorrent
- Readarr: https://readarr.com/ and https://github.com/Readarr/Readarr
- Lidarr: https://lidarr.audio/ and https://github.com/Lidarr/Lidarr

## Run
```bash
docker compose --env-file .env up -d
```

## Required Environment
- File: `.env`
- Key: `VD_PATH` (base path for config/media/download folders)

## Notes
- Default `.env.example` uses `VD_PATH=./data`; adjust if your media lives elsewhere.
- Keep `.env` private if it contains personal filesystem paths.
