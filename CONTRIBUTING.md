# Contributing to ManiLuaHub ManifestHub

Thank you for your interest in contributing to **ManiLuaHub**! We welcome verified manifest descriptors, bug reports, and dataset enrichments from the community.

## 🚀 How to Contribute

### 1. Requesting a New Game / App ID
If a game is not yet cataloged:
- Check if the game is released on Steam and has public Depot records.
- Open an issue using the [Request App ID template](.github/ISSUE_TEMPLATE/request-app-id.yml).

### 2. Submitting Manifest & Lua Blueprints
1. Fork this repository: `git clone git@github.com:maniluahub/ManifestHub.git`
2. Create a new branch named exactly as the numeric Steam App ID:
   ```bash
   git checkout -b <AppID>
   ```
3. Add the following files in the root of the branch:
   - `<AppID>.lua`: Verified Lua routing script.
   - `key.vdf`: Valve Data Format depot decryption credentials.
4. Verify file integrity:
   - Ensure `<AppID>.lua` uses valid `addappid()` and `setManifestid()` syntax.
   - Ensure `key.vdf` contains valid 64-character hexadecimal decryption keys.
5. Push the branch and open a Pull Request against `main`.

### 3. Reporting Broken or Outdated Files
If an existing manifest fails after an official game update:
- Open an issue using the [Report Broken File template](.github/ISSUE_TEMPLATE/report-broken-file.yml).
- Include the exact Steam App ID, depot number, and client error logs.

## 🛡️ Code of Conduct
- Be respectful and constructive.
- Never upload malicious executables, trojans, or bundled binary loaders. This repository only accepts plain text `.lua` and `key.vdf` files.

---

Live Registry & Web Inspector: [https://maniluahub.com](https://maniluahub.com)
