# pdftools

PDF tools stack using Stirling-PDF.

## Stack
- Service: `pdftools`
- Image: `stirlingtools/stirling-pdf:latest`
- URL: `http://127.0.0.1:8084`
- Volumes:
  - `./stirling-data/configs:/configs`
  - `./stirling-data/logs:/logs`
  - `./stirling-data/pipeline:/pipeline`
  - `./stirling-data/tessdata:/usr/share/tessdata`

## Run
```bash
cd pdftools
docker compose up -d
```

## Notes
- `MODE=BOTH` is enabled (single-container frontend/backend).
- `SECURITY_ENABLELOGIN=false` is currently set; enable login for multi-user/shared environments.
