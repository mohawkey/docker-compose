services:
  databasus:
    container_name: databasus
    image: databasus/databasus:latest
    ports:
      - 4005:4005
    volumes:
      - databasus-data:/databasus-data
    restart: unless-stopped

  db:
    image: postgres:18
    container_name: postgres
    restart: unless-stopped
    network_mode: bridge
    environment:
      POSTGRES_USER: '${PG_USER}'
      POSTGRES_PASSWORD: '${PG_PASS}'
      POSTGRES_DB: 'postgres'
      TZ: Europe/Brussels
    volumes:
      - postgres-data:/var/lib/postgresql
    ports:
      - 5432:5432

volumes:
  postgres-data:
  databasus-data:
