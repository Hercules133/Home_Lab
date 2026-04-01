# nginx_proxy_manager

Nginx Proxy Manager reverse-proxy stack.

## Stack
- Service: `nginx_proxy_manager`
- Image: `jc21/nginx-proxy-manager:latest`
- Ports:
  - `80 -> 80` (HTTP)
  - `443 -> 443` (HTTPS)
  - `127.0.0.1:81 -> 81` (admin UI)

## Links
- Website: https://nginxproxymanager.com/
- Docker Hub: https://hub.docker.com/r/jc21/nginx-proxy-manager
- GitHub: https://github.com/NginxProxyManager/nginx-proxy-manager

## Run
```bash
docker compose up -d
```

## Notes
- Exposes `80` and `443` publicly by default.
- Keep the admin interface restricted and use strong credentials.
