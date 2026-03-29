# portainer

Container management UI using Portainer CE.

## Project Status

This stack is runnable, but first-login admin setup and endpoint checks are still needed.
The repository goal is to make all stacks fully ready-to-run with minimal manual setup.

## Stack
- Service: `portainer`
- Image: `portainer/portainer-ce:latest`
- Port: `9443 -> 9443`
- Volumes:
  - `./data:/data`
  - `/var/run/docker.sock:/var/run/docker.sock`

## Links
- Website: https://www.portainer.io/
- Docs: https://docs.portainer.io/start/install/server/docker/linux
- GitHub: https://github.com/portainer/portainer

## Run
```bash
docker compose up -d
```

## Notes
- Docker socket mount gives broad Docker host control. Keep this service restricted.
