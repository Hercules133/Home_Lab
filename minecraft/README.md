# minecraft

Vanilla Minecraft server using `itzg/docker-minecraft-server`.

## Project Status

This stack is runnable, but server tuning/admin setup is still needed after first boot.
The repository goal is to make all stacks fully ready-to-run with minimal manual setup.

## Stack
- Service: `minecraft`
- Image: `itzg/minecraft-server:latest`
- Port: `25565 -> 25565`
- Volume: `./data:/data`

## Links
- Image docs: https://docker-minecraft-server.readthedocs.io/
- GitHub: https://github.com/itzg/docker-minecraft-server
- Minecraft: https://www.minecraft.net/

## Run
```bash
docker compose up -d
```

## Notes
- `EULA` is set to `TRUE`; ensure this matches your intent.
- Compose file is on modern format (no top-level `version` key).
