# actual_budget

Actual Budget local-first finance stack.

## Stack
- Service: `actual_budget`
- Image: `actualbudget/actual-server:latest`
- Port: `127.0.0.1:5007 -> 5006`
- Volume: `./data:/data`

## Links
- Website: https://actualbudget.org/
- Docker Hub: https://hub.docker.com/r/actualbudget/actual-server
- GitHub: https://github.com/actualbudget/actual

## Run
```bash
cp .env.example .env
docker compose up -d
```
