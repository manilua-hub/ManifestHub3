<div align="center">

![ManiLuaHub — The Open Steam Manifest & Lua Registry](og-home.png)

# ⚡ ManifestHub by ManiLuaHub

**The Central Open-Source Steam Manifest & Lua Script Registry powering [ManiLuaHub.com](https://maniluahub.com).**

[![Official Website](https://img.shields.io/badge/Website-maniluahub.com-6366f1?style=for-the-badge&logo=google-chrome&logoColor=white)](https://maniluahub.com)
[![Catalog](https://img.shields.io/badge/Catalog-62%2C288%20Game%20Branches-10b981?style=for-the-badge&logo=steam)](https://maniluahub.com/explore)
[![OpenAPI](https://img.shields.io/badge/API-Free%20%26%20Keyless-8b5cf6?style=for-the-badge&logo=openapi-initiative)](https://maniluahub.com/docs)
[![License](https://img.shields.io/badge/License-MIT-amber?style=for-the-badge)](LICENSE)

<p align="center">
  <a href="https://maniluahub.com">🌐 Web Search & Inspector</a> •
  <a href="https://maniluahub.com/explore">🎮 62k Manifest Catalog</a> •
  <a href="https://maniluahub.com/docs">🔌 OpenAPI Endpoints</a> •
  <a href="https://maniluahub.com/how-to-use">📖 Tutorial</a> •
  <a href="https://maniluahub.com/faq">❓ FAQ</a> •
  <a href="https://maniluahub.com/download">💻 Client Hub</a>
</p>

</div>

---

> [!TIP]
> **Online Code Inspection & Fast Downloads**
> You do **not** need to manually clone 62,000 Git branches to get your game manifests.
> 
> Visit **[ManiLuaHub.com](https://maniluahub.com)** to instantly search any game title or AppID, inspect syntax-highlighted Lua blueprints, explore Depot decryption key trees, and download clean ZIP bundles in one click.

---

## 📖 What is ManiLuaHub ManifestHub?

**ManifestHub** is a decentralized, open-access Git repository indexing Steam depot manifest descriptors and verified Lua blueprints for over **62,288 Steam games and DLCs**.

- **Branch-per-AppID Storage**: Every cataloged Steam title is assigned a standalone Git branch matching its numeric AppID (e.g. `origin/730` for *Counter-Strike 2*, `origin/2358720` for *Black Myth: Wukong*).
- **Zero Binary Tampering**: Only plain-text `<AppID>.lua` instruction scripts and `key.vdf` Valve Data Format encryption keys are stored. No executable files, DLLs, or third-party loaders are ever hosted.
- **Universal Client Compatibility**: Compatible with all standard Steam manifest routing tools including **Watt Toolkit**, **SteamTools**, **GreenLuma**, **SmokeAPI**, **Koaloader**, macOS **Whisky**, and **SteamOS (Steam Deck)**.

---

## 🛠️ Architecture & Edge Data Flow

```text
       ManiLuaHub.com Web App & OpenAPI (Edge CDN)
                         │
        ┌────────────────┴────────────────┐
        ▼                                 ▼
1. Branch Existence Check       2. Raw Data Stream
   api.github.com/.../branches/{appId}   raw.githubusercontent.com/.../{appId}/{file}
   (Multi-layer Edge Cache)        (Unthrottled High-Speed Fastly CDN)
        │                                 │
        └────────────────┬────────────────┘
                         ▼
             Complete App Manifest Package
              ├── <AppID>_public.lua
              ├── key.vdf (DepotKey AES-256)
              └── README.txt
```

---

## ⚡ Key Highlights

- 🔍 **Live Code Inspector** — Review syntax-highlighted Lua code before downloading.
- 🌳 **Interactive Depot Tree** — View encrypted chunk mappings and associated depot keys.
- 🌐 **Sub-35ms Edge Resolution** — Globally accelerated API endpoints backed by Cloudflare & Fastly edge caches.
- 🛡️ **Cryptographic Integrity** — All manifests verified against public SHA-256 hashes.
- 🔓 **Free & Keyless REST API** — Zero API keys, zero rate limiting on public manifest endpoints.

---

## 🚀 Quick Usage in 3 Steps

1. Go to **[ManiLuaHub.com](https://maniluahub.com)**.
2. Enter your game title (e.g. *Terraria*) or numeric Steam App ID (e.g. `105600`).
3. Click **Download ZIP Bundle**, extract `<AppID>_public.lua` and `key.vdf` into your loader root directory, and launch Steam.

---

## 🔌 Free OpenAPI 3.0 REST Endpoints

ManiLuaHub provides public REST endpoints for bot developers and community tool authors:

### 1. Game Catalog & Search
```bash
curl -s "https://maniluahub.com/api/search?q=cyberpunk" | jq
```

### 2. Stream Raw Lua Blueprint
```bash
curl -s "https://maniluahub.com/api/files/1091500/lua" > 1091500_public.lua
```

### 3. Download Full Manifest ZIP Archive
```bash
curl -s -O -J "https://maniluahub.com/api/files/1091500/zip"
```

Interactive OpenAPI Swagger specifications and schema definitions are available at [maniluahub.com/docs](https://maniluahub.com/docs).

---

## 🤝 Contributing

We welcome community contributions to keep game branches up-to-date!

- **Request New App ID** → [Open an App Request](https://github.com/maniluahub/ManifestHub/issues/new?template=request-app-id.yml)
- **Report Outdated / Broken Manifest** → [Report an Issue](https://github.com/maniluahub/ManifestHub/issues/new?template=report-broken-file.yml)
- **Submit Pull Requests** → Branch off as `<AppID>`, commit `<AppID>.lua` and `key.vdf`, and submit a PR.

---

## 📄 License & Disclaimer

- **Code & Dataset License**: [MIT License](LICENSE) © 2026 ManiLuaHub Team.
- **Trademark Notice**: Steam, SteamOS, and Valve are registered trademarks of Valve Corporation. ManiLuaHub is an independent open-source project and is not affiliated with Valve Corporation.
