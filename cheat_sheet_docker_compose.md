# Docker Compose — Commands Quick Ref

## Information & Help

```bash
docker compose version          # Show CLI version
docker compose help             # List available commands
```

## Working With Projects

```bash
docker compose ps -a            # All services (incl. stopped)
docker compose up -d            # Start (detached); add --build to force build
docker compose down --remove-orphans
docker compose build [svc]      # Build only selected service
docker compose exec svc bash    # Shell into running container
docker compose logs -f          # Follow logs
docker compose scale web=3      # Set replica count
```

## Images & Export

```bash
docker compose pull             # Pull images
docker compose push             # Push to registry
docker compose config           # Validate + show merged config
docker compose export > fs.tar  # Snapshot container FS (v2.24+)
```

## Observability

```bash
docker compose top              # Running processes
docker compose stats            # Resource usage
docker compose watch            # Auto‑rebuild on file changes
```
