# Logging Role

This role deploys Loki and Promtail using Docker Compose.

## Default Variables
- `logging_network_name`: Docker network for logging services.
- `loki_data_path`: Directory to store Loki data.
- `promtail_config_path`: Directory to store Promtail config.
- `docker_compose_logging_path`: Path for the Docker Compose file.

## Tasks
1. Create necessary directories.
2. Deploy `docker-compose.logging.yml` template.
3. Run `docker-compose up -d`.

