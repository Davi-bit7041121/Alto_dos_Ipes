# Base44 Dev Environment

## Project
Static HTML landing page ("Alto dos Ipês — Loteamento Premium"). Single `index.html` with inline CSS/JS, local images in `imagens/`, and external images from Google Fonts, Unsplash, and ibb.co. No backend, no build step, no dependencies.

## Running
- `docker compose -f docker-compose.base44.yml up -d` — serves the site via nginx:alpine on port 3000.
- Source is bind-mounted read-only at `/usr/share/nginx/html`.
- No live-reload needed; edit `index.html` and call `reload_preview` to see changes.

## Setup Quirk
The repo root directory has `700` permissions by default, which blocks nginx's non-root worker. Run `chmod 755 . imagens` if you get a 403 after a fresh clone.

## Health Check
`curl -s -o /dev/null -w "%{http_code}" http://localhost:3000/` should return `200`.

## Secrets
None required.
