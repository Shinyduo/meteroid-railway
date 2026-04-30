# Meteroid on Railway

Open-source billing and subscription management platform for SaaS — usage-based billing, invoicing, and revenue analytics built in Rust.

[![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/new/template/meteroid)

## Services

- **meteroid-web** — frontend dashboard (port 80)
- **meteroid-api** — main API server (gRPC port 50061, REST port 8084)
- **meteroid-scheduler** — background job scheduler
- **metering-api** — usage metering and event ingestion (port 50062)
- **PostgreSQL** — primary database (custom image with extensions)
- **ClickHouse** — analytics and metering data store
- **Redpanda** — Kafka-compatible event streaming

## Environment Variables

### Required Secrets

| Variable | Description |
|----------|-------------|
| `JWT_SECRET` | Secret for JWT token signing |
| `INTERNAL_API_SECRET` | Internal service-to-service auth |
| `SECRETS_CRYPT_KEY` | 32-character encryption key |
| `DATABASE_PASSWORD` | PostgreSQL password |

### Service Config

| Variable | Description |
|----------|-------------|
| `DATABASE_URL` | PostgreSQL connection string |
| `CLICKHOUSE_HTTP_ADDRESS` | ClickHouse HTTP endpoint |
| `KAFKA_BOOTSTRAP_SERVERS` | Redpanda/Kafka broker address |
| `METEROID_PUBLIC_URL` | Public URL of the web frontend |
| `VITE_METEROID_API_EXTERNAL_URL` | API URL for frontend |
| `VITE_METEROID_REST_API_EXTERNAL_URL` | REST API URL for frontend |

## How to use

1. Click the Deploy on Railway button above
2. Railway provisions PostgreSQL, ClickHouse, and Redpanda automatically
3. Access the Meteroid dashboard at your generated domain
4. Create your organization and start configuring billing

## Notes

- Built in Rust for high-performance processing of usage events
- Supports usage-based billing, subscriptions, and hybrid models
- S3-compatible storage optional for object storage (default: filesystem)
- Licensed under AGPL v3
