# 🚀 CLIProxy Manager Dashboard

<div align="center">

![CLIProxy](https://img.shields.io/badge/CLIProxy-v6.0-0075FF?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)
![Go](https://img.shields.io/badge/Go-1.21+-00ADD8?style=for-the-badge&logo=go)

**A modern, beautiful dashboard for managing your CLIProxy instances**

[Dashboard Features](#-dashboard-features) • [CLIProxy Features](#-cliproxy-features) • [Quick Start](#-quick-start) • [Documentation](#-documentation) • [Support](#-support--donations)

</div>

![CLIProxy Dashboard Preview](docs/Homepage.jpg)

---

## 📖 Documentation

| Document | Description |
|----------|-------------|
| **[Dashboard Guide](docs/DASHBOARD.md)** | Hướng dẫn sử dụng Dashboard (Tiếng Việt) |
| **[SDK Usage](docs/sdk-usage.md)** | How to use the Go SDK |
| **[SDK Advanced](docs/sdk-advanced.md)** | Advanced SDK features |
| **[SDK Access](docs/sdk-access.md)** | Access control documentation |
| **[SDK Watcher](docs/sdk-watcher.md)** | File watcher documentation |

---

## ✨ Dashboard Features

The CLIProxy Manager Dashboard provides a **premium Vision UI** experience for monitoring and managing your proxy server.

### 🎯 Overview Panel
- **Real-time Server Status** - Live connection monitoring with animated indicators
- **Usage Statistics** - Total requests, tokens, success/failure rates at a glance
- **Saved Cost Display** - Track how much you've saved with dynamic emoji indicators (🪙💸💵💰💎🚀)
- **Sparkline Charts** - Mini trend visualizations for quick insights

### 🏆 Model Leaderboard
- **Top 10 Models Ranking** - See your most-used models with medal icons (🥇🥈🥉)
- **Request & Token Badges** - Beautiful stat badges for easy comparison
- **Real-time Updates** - Data refreshes automatically every 5 seconds

### 📊 Activity Monitor
- **Usage Trends Chart** - Gradient area chart with smooth animations
- **Activity History Table** - Zebra-striped rows with status pills
- **Advanced Filtering** - Filter by model, status, and time range
- **Request Details Modal** - View full request/response data

### 🔐 Account Health Grid
- **Multi-Provider Support** - Gemini, Claude, OpenAI, Qwen, iFlow, Vertex
- **OAuth Authentication** - One-click login for supported providers
- **Status Badges** - Active, refreshing, error states with visual indicators
- **Hover Effects** - Cards scale and glow on interaction

### 💬 AI Playground
- **Multi-Model Chat** - Test any model directly in the dashboard
- **System Prompts** - Customize assistant behavior
- **Parameter Controls** - Temperature, Top P, Max Tokens sliders
- **Thinking Process** - View reasoning (for supported models)
- **Image Attachments** - Upload images for vision models

### 🎨 UI/UX Polish
- **Welcome Message** - Dynamic greeting based on time of day (☀️🌤️🌙)
- **Footer Stats Bar** - Uptime counter, last sync time, version info
- **Quick Actions FAB** - Floating button for common actions
- **Glassmorphism Design** - Modern frosted glass effects
- **Responsive Layout** - Works on desktop and mobile

---

## 🔧 CLIProxy Features

This dashboard is built for [**CLIProxyAPI**](https://github.com/router-for-me/CLIProxyAPI) - a powerful proxy server that provides **OpenAI/Gemini/Claude/Codex compatible API interfaces** for CLI tools and coding assistants.

> 📚 **Original Project:** [github.com/router-for-me/CLIProxyAPI](https://github.com/router-for-me/CLIProxyAPI)
> 
> 📖 **Documentation:** [help.router-for.me](https://help.router-for.me/)

### Core Features

- OpenAI/Gemini/Claude compatible API endpoints for CLI models
- OpenAI Codex support (GPT models) via OAuth login
- Claude Code support via OAuth login
- Qwen Code support via OAuth login
- iFlow support via OAuth login
- Amp CLI and IDE extensions support with provider routing
- Streaming and non-streaming responses
- Function calling/tools support
- Multimodal input support (text and images)
- Multiple accounts with round-robin load balancing
- Simple CLI authentication flows
- Generative Language API Key support
- OpenAI-compatible upstream providers via config (e.g., OpenRouter)
- Reusable Go SDK for embedding the proxy

### Supported Providers

| Provider | Features |
|----------|----------|
| **Google Gemini** | AI Studio & Gemini CLI multi-account |
| **Anthropic Claude** | Claude Code OAuth + load balancing |
| **OpenAI Codex** | GPT models via OAuth |
| **Alibaba Qwen** | Qwen Code support |
| **iFlow** | iFlow integration |
| **Vertex AI** | Service account authentication |

### Amp CLI Support

CLIProxyAPI includes integrated support for [Amp CLI](https://ampcode.com) and Amp IDE extensions:

- Provider route aliases for Amp's API patterns
- Management proxy for OAuth authentication
- Smart model fallback with automatic routing
- Model mapping to route unavailable models to alternatives

**→ [Complete Amp CLI Integration Guide](https://help.router-for.me/agent-client/amp-cli.html)**

---

## 🚀 Quick Start

### Option 1: Using Docker (Recommended)
The easiest way to run the dashboard and proxy.

```bash
# Clone the repository
git clone https://github.com/0xAstroAlpha/cliProxyAPI-Dashboard.git
cd cliProxyAPI-Dashboard

# Create config from example
cp config.example.yaml config.yaml

# Run with Docker Compose
docker-compose up -d
```

### Option 2: Using Go
Direct execution on your local machine.

```bash
# Clone the repository
git clone https://github.com/0xAstroAlpha/cliProxyAPI-Dashboard.git
cd cliProxyAPI-Dashboard

# Install dependencies
go mod download

# Run the server
go run cmd/server/main.go
```

### 📺 Access the Dashboard
Once the server is running, the dashboard is available at:
**[http://localhost:8317/static/management.html](http://localhost:8317/static/management.html)**

> [!TIP]
> Make sure to set a strong `secret-key` in your `config.yaml` to secure the dashboard.

---

## 💖 Support & Donations

If you find this project useful, consider supporting the development!

### ☕ Buy Me a Coffee

| Method | Address/Link |
|--------|--------------|
| 🇻🇳 **Vietnam (QR)** | Vietcombank QR available in Dashboard |
| 💳 **PayPal** | `wikigamingmovies@gmail.com` |
| 💚 **USDT (TRC20)** | `TNGsaurWeFhaPPs1yxJ3AY15j1tDecX7ya` |
| 💛 **USDT (BEP20)** | `0x463695638788279F234386a77E0afA2Ee87b57F5` |
| 💜 **Solana (SOL)** | `HkgpzujF8uTBuYEYGSFMnmGzBYmEFyajzTiZacRtXzTr` |

---

## 👨‍💻 Credits

| Role | Credit |
|------|--------|
| **Dashboard UI/UX** | [Brian Le](https://www.facebook.com/lehuyducanh/) |
| **CLIProxyAPI** | [router-for-me](https://github.com/router-for-me/CLIProxyAPI) |

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

<div align="center">

**⭐ Star the original project: [CLIProxyAPI](https://github.com/router-for-me/CLIProxyAPI)**

Made with ❤️ by the CLIProxy community

</div>
