# eRPC Railway Deployment Guide

## Build and Deploy Commands
- Deploy to Railway: Click the "Deploy on Railway" button in README.md
- Local Docker build: `docker build -f Dockerfile.erpc -t erpc-server .`
- Local monitoring build: `docker build -f Dockerfile.monitoring -t erpc-monitoring .`
- Run locally: `docker-compose -f compose-dev.yaml up`

## Environment Variables
- Required: `REDIS_ADDR`, `REDIS_PASSWORD`, `RPC_API_SECRET`
- Optional: Various API keys for RPC providers (ALCHEMY_API_KEY, INFURA_API_KEY, etc.)

## Container Structure
- eRPC server: Handles RPC requests, runs on port 4000
- Metrics endpoint: Port 4001
- Monitoring stack: Grafana (port 3000), Prometheus (port 9090)

## Code Style Guidelines
- Configuration files use YAML format
- Environment variables use UPPERCASE_WITH_UNDERSCORES
- Containerization follows multi-stage build patterns
- Docker images should be minimal and secure