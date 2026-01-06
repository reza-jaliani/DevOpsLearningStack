# EFK Logging Stack with Docker Compose

This part of the project focuses on implementing a complete **EFK
(Elasticsearch, Fluentd, Kibana) logging stack** using **Docker
Compose**, with **Nginx** as a log source and **Fluent Bit** as a
lightweight log forwarder.

The main goal of this phase was to deeply understand how container logs
flow from application level to centralized log storage, before moving to
infrastructure provisioning with Terraform in later phases.

------------------------------------------------------------------------

## Architecture Overview

Nginx → Fluent Bit → Fluentd → Elasticsearch → Kibana

------------------------------------------------------------------------

## Services Used

-   Nginx -- Log source
-   Fluent Bit -- Log collector
-   Fluentd -- Log router
-   Elasticsearch -- Log storage
-   Kibana -- Visualization
-   Docker Compose -- Orchestration

------------------------------------------------------------------------

## Docker Compose Commands

``` bash
docker compose up -d
docker compose ps
docker compose logs fluent-bit
docker compose logs fluentd
docker compose down
```

------------------------------------------------------------------------

## Validation

-   Nginx log generation verified
-   Fluent Bit log forwarding confirmed
-   Fluentd receiving logs
-   Elasticsearch index creation
-   Logs visible in Kibana

------------------------------------------------------------------------

## Challenges

-   Volume mounting correctness
-   stdout vs file-based logging
-   Debugging silent pipeline failures

------------------------------------------------------------------------

## Author

Monitoring Engineer learning DevOps with focus on observability.
