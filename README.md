# MiMoBot

> AI-powered crypto assistant built for clarity in a noisy market.

**Live →** [huolinger010.github.io/mimobot](https://huolinger010.github.io/mimobot)

---

## What It Does

MiMoBot is a single-page crypto intelligence tool that combines real-time market data, contract analysis, and DeFi education into one clean interface — no API keys, no signups, no friction.

### Token Safety Checker
Paste any ERC-20 contract address. Get an instant risk score (0–100) based on market cap, volume, holder distribution, liquidity depth, and online presence. Each token receives a clear verdict: **SAFE**, **CAUTION**, **HIGH RISK**, or **DANGER** — backed by transparent, itemized analysis.

### Live Market Data
Real-time prices, 24h changes, market caps, and volume for 100+ tokens. Quick filters for top coins, trending, gainers, and losers — all powered by CoinGecko's public API.

### DeFi Education
Curated knowledge base covering yield farming, impermanent loss, gas optimization, Layer 2 scaling, airdrops, tokenomics, and more. Click any topic to start a conversation.

### AI Chat
Ask anything about crypto in natural language. MiMoBot routes queries to the appropriate data source or knowledge base and returns structured, actionable answers.

---

## Design Philosophy

**Minimal surface, maximum utility.** One HTML file. Zero dependencies. No build step. The entire application ships as a single `index.html` — CSS, JavaScript, and markup in one self-contained document.

- **Dark & light themes** with smooth transitions and localStorage persistence
- **Responsive layout** — sidebar navigation on desktop, bottom tab bar on mobile
- **Glassmorphism UI** with layered blur, ambient gradients, and micro-interactions
- **Accessible** — keyboard navigable, semantic markup, safe area insets for mobile

---

## Tech Stack

| Layer | Choice |
|-------|--------|
| Frontend | Vanilla HTML/CSS/JS — no frameworks |
| AI Model | Xiaomi MiMo |
| Market Data | CoinGecko (free tier, no key) |
| Hosting | GitHub Pages |

---

## Quick Start

```bash
git clone https://github.com/huolinger010/mimobot.git
open mimobot/index.html
```

No install. No build. Open and use.

---

## License

MIT
