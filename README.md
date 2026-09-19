# dck Blueprints

> Ready-to-deploy container templates for [dck](https://github.com/kuranix/dck) — a zero-daemon container runtime.

## Usage

```bash
# List all available blueprints
dck blueprint list

# Install a blueprint (creates and starts a container)
dck blueprint install nginx
dck blueprint install minecraft-server
dck blueprint install nextcloud
```

## Available Blueprints (27)

### 🗄️ Databases
| Blueprint | Image | Description |
|-----------|-------|-------------|
| [clickhouse](clickhouse.template.json) | `clickhouse/clickhouse-server:latest` | Column-oriented analytics database |
| [couchdb](couchdb.template.json) | `couchdb:3` | CouchDB 3 with persistent JSON document storage |
| [mariadb-11](mariadb-11.template.json) | `mariadb:11` | MariaDB 11 with persistent storage |
| [mongodb-7](mongodb-7.template.json) | `mongo:7` | MongoDB 7 with persistent storage |
| [mysql-8](mysql-8.template.json) | `mysql:8` | MySQL 8 with persistent storage |
| [postgres-16](postgres-16.template.json) | `postgres:16` | PostgreSQL 16 with persistent storage |
| [redis-7](redis-7.template.json) | `redis:7-alpine` | Redis 7 in-memory cache with persistence |

### 🎮 Games
| Blueprint | Image | Description |
|-----------|-------|-------------|
| [cs2-server](cs2-server.template.json) | `cm2network/csgo:latest` | Counter-Strike 2 dedicated server via SteamCMD |
| [minecraft-server](minecraft-server.template.json) | `itzg/minecraft-server:latest` | Minecraft Java Edition server with persistent world |
| [palworld-server](palworld-server.template.json) | `thijsvanloef/palworld-server-docker:latest` | Palworld dedicated server with persistent save |
| [rust-server](rust-server.template.json) | `didstopia/rust-server:latest` | Rust dedicated server via SteamCMD |
| [satisfactory-server](satisfactory-server.template.json) | `wolveix/satisfactory-server:latest` | Satisfactory dedicated server with persistent save files |
| [terraria-server](terraria-server.template.json) | `beardedio/terraria:latest` | Terraria dedicated server with persistent world |
| [valheim-server](valheim-server.template.json) | `lloesche/valheim-server:latest` | Valheim dedicated server with persistent world |

### 🌐 Web
| Blueprint | Image | Description |
|-----------|-------|-------------|
| [caddy](caddy.template.json) | `caddy:alpine` | Caddy web server with auto-HTTPS |
| [filebrowser](filebrowser.template.json) | `filebrowser/filebrowser:latest` | Web-based file manager with authentication |
| [ghost](ghost.template.json) | `ghost:latest` | Ghost blogging platform |
| [nginx](nginx.template.json) | `nginx:alpine` | Nginx web server with custom config |
| [node-app](node-app.template.json) | `node:22-alpine` | Node.js application |
| [wordpress](wordpress.template.json) | `wordpress:latest` | WordPress with persistent content |

### 📊 Monitoring
| Blueprint | Image | Description |
|-----------|-------|-------------|
| [grafana](grafana.template.json) | `grafana/grafana:latest` | Dashboards and observability platform |
| [uptime-kuma](uptime-kuma.template.json) | `louislam/uptime-kuma:latest` | Self-hosted website monitoring tool |

### 🌐 Network
| Blueprint | Image | Description |
|-----------|-------|-------------|
| [adguard-home](adguard-home.template.json) | `adguard/adguardhome:latest` | Network-wide DNS filtering for ads and trackers |
| [wireguard](wireguard.template.json) | `weejewel/wg-easy:latest` | WireGuard VPN server with web admin interface |

### 🎙️ Voice
| Blueprint | Image | Description |
|-----------|-------|-------------|
| [teamspeak-3](teamspeak-3.template.json) | `teamspeak:latest` | TeamSpeak 3 voice server |

### ☁️ Storage
| Blueprint | Image | Description |
|-----------|-------|-------------|
| [nextcloud](nextcloud.template.json) | `nextcloud:latest` | Self-hosted cloud storage and collaboration platform |

### 🎬 Media
| Blueprint | Image | Description |
|-----------|-------|-------------|
| [jellyfin](jellyfin.template.json) | `jellyfin/jellyfin:latest` | Free and open-source media streaming server |

## Adding a Blueprint

1. Create a `.template.json` file following the schema below
2. Add an entry to [`registry.json`](registry.json)
3. Submit a PR

### Schema

```json
{
  "name": "my-service",
  "category": "databases",
  "description": "Short description",
  "image": "image-name",
  "tag": "latest",
  "command": "",
  "env": "[{\"key\":\"VAR\",\"value\":\"val\"}]",
  "ports": "host:container/protocol",
  "volumes": "volume_name:/container/path",
  "memory": "512m",
  "cpus": "1.0",
  "restart": "always"
}
```

## Categories

| Category | Count |
|----------|-------|
| Databases | 7 |
| Games | 7 |
| Web | 6 |
| Monitoring | 2 |
| Network | 2 |
| Voice | 1 |
| Storage | 1 |
| Media | 1 |
