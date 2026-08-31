# 🔍 FOGAMI Search

A self-hosted, privacy-respecting search engine powered by **SearXNG** with a custom **cyber/dark aesthetic** — neon green accents, pure black background, and a branded FOGAMI mascot.

---

## ✨ Features

- 🔒 **Privacy First** — No tracking, no profiling, meta-search engine
- 🎨 **Custom FOGAMI Theme** — Cyber dark mode with neon green (#00ff87) accents
- 🤖 **FOGAMI Mascot** — Custom branded logo on the homepage
- ⚡ **Fast & Lightweight** — Docker-based, runs locally or on any server
- 🔎 **Multiple Search Engines** — Google, Brave, DuckDuckGo and more aggregated
- 📦 **Fully Dockerized** — One command to spin up everything

---

## 📁 Project Structure

```
FOGAMI-Search/
├── custom_branding/         # All custom theme files
│   ├── FOGAMI.svg           # FOGAMI mascot logo
│   ├── fogami-wordmark.svg  # FOGAMI text wordmark
│   ├── custom_theme.css     # Full custom CSS (cyber dark theme)
│   ├── base.html            # Custom base template
│   ├── index.html           # Custom homepage template
│   ├── page_with_header.html# Header template with wordmark
│   ├── searxng-wordmark.min.svg
│   └── bg.jpg               # Background image
├── searxng/
│   └── settings.yml         # SearXNG instance configuration
├── docker-compose.yml       # Docker Compose (SearXNG + Redis + Caddy)
├── Caddyfile                # Caddy reverse proxy config
├── .env.example             # Environment variables template
└── README.md
```

---

## 🚀 Quick Start

### Prerequisites
- [Docker](https://www.docker.com/get-started) installed
- [Docker Compose](https://docs.docker.com/compose/) installed

### 1. Clone the repo
```bash
git clone https://github.com/YOUR_USERNAME/fogami-search.git
cd fogami-search
```

### 2. Set up environment
```bash
cp .env.example .env
```
Then open .env and replace SEARXNG_SECRET with a random key:
```bash
# Generate a secure secret key:
openssl rand -hex 32
```
Also update searxng/settings.yml and replace REPLACE_WITH_YOUR_OWN_SECRET_KEY with the same key.

### 3. Start the stack
```bash
docker compose up -d
```

### 4. Open in browser
Visit **[http://localhost:8080](http://localhost:8080)** 🎉

---

## 🎨 Customization

All branding is in the custom_branding/ folder:

| File | Purpose |
|------|---------|
| custom_theme.css | All colors, fonts, layout overrides |
| FOGAMI.svg | The homepage mascot logo |
| ogami-wordmark.svg | Header text logo |
| index.html | Homepage template |
| ase.html | Base layout template |

After any change, restart the container:
```bash
docker compose up -d --force-recreate searxng
```

---

## 🛑 Stopping

```bash
docker compose down
```

---

## 📜 License

Built on top of [SearXNG](https://github.com/searxng/searxng) — MIT Licensed.
Custom branding & theme by FOGAMI.
