<div align="center">

![ManiLuaHub — The Open Steam Manifest & Lua Registry](og-home.png)

# ⚡ ManifestHub by ManiLuaHub

**The Central Open-Source Steam Manifest & Lua Script Registry powering [ManiLuaHub.com](https://maniluahub.com).**

[![Official Website](https://img.shields.io/badge/Website-maniluahub.com-6366f1?style=for-the-badge&logo=google-chrome&logoColor=white)](https://maniluahub.com)
[![Catalog](https://img.shields.io/badge/Catalog-62%2C257%20Verified%20Branches-10b981?style=for-the-badge&logo=steam&logoColor=white)](https://maniluahub.com/explore)
[![OpenAPI](https://img.shields.io/badge/API-Free%20%26%20Keyless-8b5cf6?style=for-the-badge&logo=openapi-initiative&logoColor=white)](https://maniluahub.com/docs)
[![Loaders](https://img.shields.io/badge/Compatible-Watt%20Toolkit%20%7C%20SteamTools-0284c7?style=for-the-badge&logo=linux&logoColor=white)](https://maniluahub.com/download)
[![Booster](https://img.shields.io/badge/Game_Booster-GearUP_5x_Speed-ff4655?style=for-the-badge&logo=fastlane&logoColor=white)](https://gearup.gg/aff?p=KTeQ719IlU3u)
[![License](https://img.shields.io/badge/License-MIT-amber?style=for-the-badge)](LICENSE)

<p align="center">
  <a href="https://maniluahub.com">🌐 <b>Web Explorer</b></a> •
  <a href="https://maniluahub.com/explore">🎮 62k Game Catalog</a> •
  <a href="https://maniluahub.com/docs">🔌 OpenAPI Docs</a> •
  <a href="https://maniluahub.com/how-to-use">📖 Tutorial</a> •
  <a href="https://maniluahub.com/download">💻 Client Center</a> •
  <a href="https://maniluahub.com/faq">❓ FAQ</a>
</p>

<p align="center">
  <b>English</b> • <a href="README.zh-CN.md">简体中文 (含雷神加速器免费福利)</a>
</p>

</div>

---

> [!TIP]
> ### ⚡ Don't Clone 62,000 Git Branches — Use the Free Web Explorer!
> 
> You do **not** need to manually clone 62,000 Git branches to inspect or download game manifests.
> 
> Visit **[ManiLuaHub.com](https://maniluahub.com)** to instantly search any title, inspect Lua blueprints, and download ready-to-use bundles:
> 
> 👉 **[Launch ManiLuaHub Web Explorer](https://maniluahub.com)**
> 
> - 🔍 **Instant Search**: Look up any game title (e.g. *Black Myth: Wukong*, *Cyberpunk 2077*, *ELDEN RING*) or numeric Steam AppID.
> - 👁️ **Live Code Inspection**: Preview syntax-highlighted Lua blueprints and Depot decryption key trees in your browser.
> - 📦 **1-Click Clean ZIP**: Download ready-to-use `<AppID>.lua` + `key.vdf` ZIP archives without running Git commands.
> - 🔌 **Free OpenAPI v1**: High-performance REST endpoints for Discord bots, community scripts, and developer tools.

---

## 📖 What is ManifestHub?

**ManifestHub** is a decentralized, open-access Git repository indexing Steam depot manifest descriptors and verified Lua blueprints for over **62,257 Steam games and DLCs**.

- **Branch-per-AppID Architecture**: Every cataloged Steam title is assigned an independent Git branch matching its numeric AppID (e.g. `origin/730` for *Counter-Strike 2*, `origin/2358720` for *Black Myth: Wukong*).
- **Zero Binary Tampering**: Only plain-text `<AppID>.lua` instruction scripts and standard `key.vdf` Valve Data Format decryption descriptors are stored. No executable files, DLLs, or third-party loaders are ever hosted.
- **Universal Loader Compatibility**: Compatible with all standard Steam manifest routing tools including **Watt Toolkit**, **SteamTools**, **GreenLuma**, **SmokeAPI**, **Koaloader**, macOS **Whisky**, and **SteamOS (Steam Deck)**.

---

## 🛠️ Architecture & Edge Data Flow

```text
       ManiLuaHub.com Web App & OpenAPI Gateway (Cloudflare Edge)
                                 │
                ┌────────────────┴────────────────┐
                ▼                                 ▼
    1. Multi-Tier Cache Layer             2. Raw Manifest Stream
     - Cloudflare Edge Cache (HIT)         github.com/manilua-hub/ManifestHub3
     - Cloudflare D1 Database              (62,257+ AppID Isolated Branches)
                │                                 │
                └────────────────┬────────────────┘
                                 ▼
                     Verified Manifest Package
                      ├── <AppID>_public.lua
                      ├── key.vdf (DepotKey AES-256)
                      └── README.txt
```

---

## ⚡ Key Highlights

- 🔍 **Live Code Inspector** — Review syntax-highlighted Lua blueprints before downloading to ensure total transparency.
- 🌳 **Interactive Depot Tree** — Visualize encrypted chunk mappings, depot IDs, and corresponding AES-256 keys.
- 🌐 **Sub-35ms Edge Latency** — Globally distributed Anycast edge network with intelligent caching.
- 🛡️ **Cryptographic Integrity** — All manifests are verified against public SHA-256 checksums.
- 🔓 **Free & Keyless REST API** — Zero API keys and zero rate limiting on public manifest endpoints.

---

## 🚀 Quick Start in 3 Steps

1. Navigate to **[ManiLuaHub.com](https://maniluahub.com)**.
2. Search by game title (e.g. *Terraria* or *Elden Ring*) or numeric AppID (e.g. `1245620`).
3. Click **Download ZIP Bundle**, extract `<AppID>.lua` and `key.vdf` into your loader directory, and launch Steam.

---

## 🔌 Free OpenAPI 3.0 REST Endpoints

Developers can consume ManiLuaHub data programmatically for bots, CLI utilities, and community extensions:

### 1. Game Metadata & Manifest Status
```bash
curl -s "https://maniluahub.com/api/v1/manifest/2358720" | jq .
```

### 2. Stream Raw Lua Blueprint
```bash
curl -s "https://maniluahub.com/api/files/2358720/lua" -o 2358720.lua
```

### 3. Fetch Decryption Keys (key.vdf)
```bash
curl -s "https://maniluahub.com/api/files/2358720/key" -o key.vdf
```

### 4. Download Full Manifest ZIP Archive
```bash
curl -s -O -J "https://maniluahub.com/api/files/2358720/zip"
```

Interactive OpenAPI Swagger specifications and full schema references are available at **[maniluahub.com/docs](https://maniluahub.com/docs)**.

---

## ⚡ Recommended Network Optimizer (Global Players)

For gamers experiencing high ping, packet loss, or slow Steam CDN downloads, we recommend **GearUP Booster**:
- 🚀 **Patented Adaptive Intelligent Routing** — Dynamic multi-path latency reduction directly to Steam CDN & multiplayer game server clusters.
- 📥 **Accelerated Depot Downloads** — Up to 5x faster manifest binary chunks synchronization.
- 🎮 **Zero Configuration** — Fully optimized for Windows 10/11, macOS, and handheld gaming.
- 👉 **[Download GearUP Booster (Free Trial)](https://gearup.gg/aff?p=KTeQ719IlU3u)**

---

## 🤝 Contributing

We welcome community contributions to keep game branches up-to-date:

- **Request New App ID** → [Open an App Request](https://github.com/manilua-hub/ManifestHub3/issues)
- **Report Outdated / Broken Manifest** → [Report an Issue](https://github.com/manilua-hub/ManifestHub3/issues)
- **Submit Pull Requests** → Branch off as `<AppID>`, commit `<AppID>.lua` and `key.vdf`, and submit a PR.

---

## 📄 License & Disclaimer

- **Dataset & Code License**: [MIT License](LICENSE) © 2026 ManiLuaHub Team.
- **Trademark Notice**: Steam, SteamOS, and Valve are registered trademarks of Valve Corporation. ManiLuaHub is an independent open-source project and is neither affiliated with, endorsed by, nor sponsored by Valve Corporation.

---

<div align="center">

Made with ❤️ for the global gaming community • **[ManiLuaHub.com](https://maniluahub.com)**

</div>
