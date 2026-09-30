# VOID SURGE — Neon Arena

## Overview
Single-file HTML5 canvas game ("VOID SURGE — Neon Arena"). No build step, no backend, no dependencies — just one static HTML file (`VOID SURGE.html`) with inline CSS and JavaScript.

## Running in Base44
- Served via `nginx:alpine` on host port 3000 (see `docker-compose.base44.yml`).
- The file is bind-mounted read-only into the container; edits to `VOID SURGE.html` appear immediately on browser refresh (no rebuild needed).
- `nginx.conf` is mounted as the main nginx config (`/etc/nginx/nginx.conf`) with `user root;` so the nginx worker can read the bind-mounted file (the sandbox repo root has restrictive 0700 permissions).
- The filename contains a space; nginx `index` and `try_files` reference it as `"VOID SURGE.html"`.

## Notes
- The git history shows the file was accidentally wiped to near-empty in the second commit. The full 1124-line game was restored from the first commit (`0367d73`).
- No external credentials or secrets are needed.
