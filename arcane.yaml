# ----------------------------------------------------------------------------------------------------
# SENCRYPTION_KEY: openssl rand -hex 32
# JWT_SECRET: openssl rand -hex 32
# ----------------------------------------------------------------------------------------------------
services:
  arcane:
    container_name: arcane
    image: ghcr.io/getarcaneapp/manager:latest
    network_mode: bridge
    restart: unless-stopped
    ports:
      - '3552:3552'
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
      - arcane-data:/app/data
    environment:
      - ENCRYPTION_KEY=your-32-char-encryption-key
      - JWT_SECRET=your-jwt-secret
      - TZ=Europe/Brussels
    cgroup: host

volumes:
  arcane-data:
