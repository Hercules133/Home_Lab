# n8n

Workflow automation service.

## Project Status

This stack is runnable, but post-boot workflow/auth configuration is still needed.
The repository goal is to make all stacks fully ready-to-run with minimal manual setup.

## Stack
- Service: `n8n`
- Image: `n8nio/n8n`
- Port: `127.0.0.1:5678 -> 5678`
- Volume: `./data:/home/node/.n8n`

## Links
- Website: https://n8n.io/
- Docs: https://docs.n8n.io/hosting/installation/docker/
- GitHub: https://github.com/n8n-io/n8n

## Run
```bash
cp .env.example .env
docker compose up -d
```

## Required Environment (recommended)
- File: `.env` (you can start from `.env.example`)
- `N8N_BASIC_AUTH_USER`
- `N8N_BASIC_AUTH_PASSWORD`

## Notes
- Hard-coded credentials were replaced with environment-variable based values.
- Keep auth password out of version control.
