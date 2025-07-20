# Nginx Multi-Config Setup

This repository contains multiple Nginx configurations and Docker setups to support various functionalities such as load balancing, rate limiting, and serving static content.


## Overview

### Load Balancer

- Implements reverse proxy load balancing with weighted backend servers.
- Supports WebSocket connections.
- Uses environment variable templating for flexible configuration.
- Built on the lightweight `nginx:alpine` image.

### Rate Limiting

- Implements request rate limiting to prevent abuse.
- Defines zones and limits using Nginx directives.
- Can be integrated with other Nginx servers to protect backend services.

### Static Server

- Builds an Ubuntu 22.04 based image with Nginx installed.
- Serves custom static HTML content.
- Uses a custom Nginx configuration.

## Environment Variables

Environment variables are used primarily in the load balancer setup. These include:

- `SERVER_HOST_1`, `SERVER_PORT_1` — Backend server 1 address and port.
- `SERVER_HOST_2`, `SERVER_PORT_2` — Backend server 2 address and port.
- `SERVER_HOST_3`, `SERVER_PORT_3` — Backend server 3 address and port.
- `NGINX_PORT` — Port for Nginx to listen on.
- `NGINX_HOST` — Server domain or hostname.

Set these variables in a `.env` file or your deployment environment.

## How to Build and Run

### Load Balancer

```bash
cd load-balancer
docker build -t nginx-load-balancer .
docker run --env-file ../.env -p 9090:9090 nginx-load-balancer
