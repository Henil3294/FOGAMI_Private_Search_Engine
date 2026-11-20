# 🔍 FOGAMI Search

A self-hosted, privacy-respecting metasearch engine powered by **SearXNG**. FOGAMI aggregates results from multiple search engines without tracking or profiling users.

<p align="center">
  <img src="https://github.com/user-attachments/assets/b86c45d7-ac72-491e-a02d-75a85156883a" alt="FOGAMI Search Interface" width="90%" />
</p>

---

## ✨ Features

- 🔒 **Privacy First** — No tracking, no profiling, no ads
- 🔎 **Multiple Search Engines** — Google, DuckDuckGo, Bing, Wikipedia, Reddit, GitHub and more
- ⚡ **Fast & Lightweight** — Docker-based, runs locally or on any server
- 📦 **Fully Dockerized** — One command to spin up everything
- 🔄 **Auto-complete** — DuckDuckGo-powered search suggestions
- 🛡️ **SafeSearch** — Strict safe search enabled by default

---

## 📁 Project Structure

```
FOGAMI-Search/
├── searxng/
│   └── settings.yml         # SearXNG instance configuration
├── fogami-logo.svg          # Custom FOGAMI logo
├── docker-compose.yml       # Docker Compose (SearXNG + Redis + Caddy)
├── Caddyfile                # Caddy reverse proxy config
├── .env.example             # Environment variables template
├── .gitignore
└── README.md
```

---

## 🚀 Quick Start

### Prerequisites
- [Docker](https://www.docker.com/get-started) installed
- [Docker Compose](https://docs.docker.com/compose/) installed

### 1. Clone the repo
```bash
git clone https://github.com/Henil3294/FOGAMI_Private_Search_Engine.git
cd FOGAMI_Private_Search_Engine
```

### 2. Set up environment
```bash
cp .env.example .env
```
Generate a secret key and paste it into `.env`:
```bash
openssl rand -hex 32
```
Also update `searxng/settings.yml` — replace `REPLACE_WITH_YOUR_OWN_SECRET_KEY` with the same key.

### 3. Start the stack
```bash
docker compose up -d
```

### 4. Open in browser
Visit **[http://localhost:8080](http://localhost:8080)** 🎉

---

## ⚙️ Configuration

All instance settings are in `searxng/settings.yml`:

| Setting | Default |
|---------|---------|
| Instance Name | FOGAMI Search |
| SafeSearch | Strict |
| Autocomplete | DuckDuckGo |
| HTTP Method | GET |
| Image Proxy | Enabled |
| Theme | Simple (auto light/dark) |

### Enabled Search Engines

| Engine | Shortcut |
|--------|----------|
| Google | `go` |
| DuckDuckGo | `ddg` |
| Bing | `bi` |
| Wikipedia | `wp` |
| GitHub | `gh` |
| Reddit | `rd` |

---

## 🛑 Stopping

```bash
docker compose down
```

---

## 📜 License

Built on top of [SearXNG](https://github.com/searxng/searxng) — MIT Licensed.
