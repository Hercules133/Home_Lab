# ollama_webui

Local AI stack with Ollama and Open WebUI.

## Project Status

This stack needs post-boot configuration after startup (admin user/auth settings, model pulls, and provider defaults).
The repository goal is to make all stacks fully ready-to-run with minimal manual setup.

## Stack
- Services:
  - `ollama`
  - `open-webui`
- Ports (localhost only):
  - Ollama API: `127.0.0.1:11434`
  - Open WebUI: `127.0.0.1:3000`
- Volumes:
  - `./ollama:/root/.ollama`
  - `./openwebui:/app/backend/data`

## Links
- Ollama: https://ollama.com/ and https://github.com/ollama/ollama
- Open WebUI: https://openwebui.com/ and https://github.com/open-webui/open-webui

## Run
```bash
docker compose up -d
```

## Notes
- `WEBUI_AUTH=False` disables Open WebUI authentication. Enable auth before exposing beyond localhost.
