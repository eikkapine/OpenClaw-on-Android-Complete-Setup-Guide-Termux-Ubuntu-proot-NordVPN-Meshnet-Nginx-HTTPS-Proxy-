<div align="center">

```
╔═══════════════════════════════════════════════════════════╗
║                                                           ║
║    🦞  O P E N C L A W   O N   A N D R O I D  🦞         ║
║                                                           ║
║    Termux · Ubuntu proot · NordVPN Meshnet               ║
║    nginx HTTPS · 24/7 AI Agent Cluster                   ║
║                                                           ║
╚═══════════════════════════════════════════════════════════╝
```

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
![Platform](https://img.shields.io/badge/platform-Android-green)
![Node](https://img.shields.io/badge/Node.js-22-brightgreen)
![Status](https://img.shields.io/badge/status-battle--tested-ff4d6d)

### → **[Read the Full Guide](https://eikkapine.github.io/OpenClaw-on-Android-Complete-Setup-Guide-Termux-Ubuntu-proot-NordVPN-Meshnet-Nginx-HTTPS-Proxy-/openclaw-definitive-android-meshnetwork-and-https-proxy-guide.html)** ←

*Turn any Android phone into a 24/7 AI agent. Built from real failures, not documentation.*

</div>

---

## What this is

A complete, honest guide to running [OpenClaw](https://github.com/openclaw/openclaw) on Android — the version that actually works, written after breaking it every possible way first.

Bare Termux doesn't work. The bash installer doesn't work. NordVPN inside Ubuntu doesn't work. This guide tells you exactly what does, why, and in what order.

## What you'll have at the end

- OpenClaw running 24/7 inside Ubuntu proot on your phone
- Accessible from any linked device via NordVPN Meshnet
- Secured with a self-signed HTTPS nginx proxy
- Surviving reboots, battery kills, and Android's memory manager
- Optimized for sustained phone server operation (battery, swap, thermals)

## Quick overview of the stack

```
Android Phone
└── Termux (F-Droid)
    └── Ubuntu proot (proot-distro)
        ├── Node.js 22 (NodeSource)
        ├── OpenClaw gateway (tmux session)
        └── nginx (HTTPS proxy → Meshnet IP:8443)

NordVPN Android app
└── Meshnet (free, no subscription)
    └── Stable 100.64.x.x IPs across linked devices

SWAP — No ROOT (Play Store)
└── 2GB swap on internal storage
    └── Prevents Android from killing the gateway under memory pressure
```

## What this guide covers

| Section | What you'll do |
|---|---|
| Battery setup | Charge limit to 85% — extend lifespan for 24/7 use |
| Expand RAM | SWAP No ROOT — 2GB swap on internal storage |
| Keep it cool | Fan, case removal, thermal throttle prevention |
| PC control | scrcpy setup, Alt+Shift+V paste for Nordic keyboards |
| Permissions | Battery optimization, wake lock, Termux:Boot |
| Ubuntu proot | Why it's mandatory and how to install it |
| Node.js 22 | NodeSource install inside Ubuntu |
| OpenClaw | npm install, what the warnings mean, --ignore-scripts fallback |
| Network fix | hijack.js patch for Android's os.networkInterfaces() |
| Onboarding | Wizard answers, Telegram bug workaround |
| Gateway | tmux, kill/restart, reconnect after reboot |
| NordVPN Meshnet | Setup, gotchas, battery optimization |
| nginx HTTPS | Self-signed cert, Meshnet-bound proxy |
| Dashboard | Token injection, device pairing |
| Troubleshooting | 17 documented errors with exact fixes |

## Key lessons (the short version)

- **Ubuntu proot is mandatory** — Bionic libc in bare Termux breaks koffi every time
- **Use NodeSource for Node.js 22** — don't use `apt install nodejs` directly
- **NordVPN runs as the Android app** — not inside Ubuntu proot
- **npm warn deprecated is harmless** — wait for `added 847 packages`
- **Telegram is a channel, not a plugin** — the wizard has a bug, configure it manually
- **`nginx -s reload` not `nginx`** — if nginx is already running
- **Alt+Shift+V** — to paste from PC clipboard into scrcpy

---

<div align="center">

**→ [Open the Guide](https://eikkapine.github.io/OpenClaw-on-Android-Complete-Setup-Guide-Termux-Ubuntu-proot-NordVPN-Meshnet-Nginx-HTTPS-Proxy-/openclaw-definitive-android-meshnetwork-and-https-proxy-guide.html) ←**

*CC BY 4.0 — share freely, credit appreciated*

🦞

</div>
