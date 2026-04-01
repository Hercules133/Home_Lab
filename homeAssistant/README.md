# homeAssistant

Home Assistant container setup.

## Stack
- Service: `homeAssistant`
- Image: `ghcr.io/home-assistant/home-assistant:stable`
- Network: `host`
- Volumes:
  - `./config:/config`
  - `/etc/localtime:/etc/localtime:ro`
  - `/run/dbus:/run/dbus:ro`

## Run
```bash
cd homeAssistant
docker compose up -d
```

## Notes
- Access via `http://<host-ip>:8123`.
- For Bluetooth integrations, keep the `/run/dbus` mount.
- Timezone is currently set to `Europe/Berlin` in `docker-compose.yml`; edit that value if needed.
