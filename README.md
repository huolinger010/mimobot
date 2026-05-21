<div align="center">

# 🤖 MiMoBot

### AI-Powered Crypto Intelligence

<p>
  <strong>A single-file crypto assistant that combines real-time market data, smart contract analysis, and DeFi education — powered by Xiaomi MiMo.</strong>
</p>

<p>
  <a href="https://huolinger010.github.io/mimobot"><img src="https://img.shields.io/badge/Live_Demo-6366f1?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Live Demo"></a>
  <a href="https://github.com/huolinger010/mimobot/stargazers"><img src="https://img.shields.io/github/stars/huolinger010/mimobot?style=for-the-badge&color=fbbf24" alt="Stars"></a>
  <a href="https://github.com/huolinger010/mimobot/blob/main/LICENSE"><img src="https://img.shields.io/badge/License-MIT-34d399?style=for-the-badge" alt="License"></a>
  <img src="https://img.shields.io/badge/Dependencies-0-6366f1?style=for-the-badge" alt="Zero Dependencies">
  <img src="https://img.shields.io/badge/Build_Step-None-f87171?style=for-the-badge" alt="No Build Step">
  <img src="https://img.shields.io/badge/API_Keys-None-34d399?style=for-the-badge" alt="No API Keys">
</p>

<br>

<img src="https://github.com/huolinger010/mimobot/raw/main/.github/preview.png" alt="MiMoBot Preview" width="100%" style="border-radius: 12px; max-width: 800px;">

</div>

---

## 📖 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Design System](#design-system)
- [Architecture](#architecture)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [API Reference](#api-reference)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

**MiMoBot** is a zero-dependency, single-page crypto intelligence platform designed for traders, researchers, and DeFi enthusiasts who need instant, reliable information without friction.

Built entirely in a single `index.html` file — no frameworks, no build tools, no external dependencies. Just open and use.

### Why MiMoBot?

In a landscape full of complex dashboards and gated tools, MiMoBot strips crypto analysis down to its essentials:

- **Instant access** — no signups, no API keys, no credit cards
- **Single file** — the entire application is one self-contained HTML document
- **AI-powered** — natural language queries routed to live data and knowledge bases
- **Privacy-first** — all processing happens client-side; no data leaves your browser
- **Beautiful by default** — glassmorphism UI with dark/light themes and smooth animations

---

## Features

### 🛡️ Token Safety Checker

Paste any ERC-20 contract address and receive an instant, comprehensive risk assessment.

**How it works:**
1. Validates contract address format (`0x` + 40 hex characters)
2. Fetches on-chain data from CoinGecko's contract endpoint
3. Analyzes 8 risk dimensions with weighted scoring (0–100)
4. Generates a visual report with clear verdict and itemized breakdown

**Risk Dimensions Analyzed:**
| Dimension | Weight | Indicators |
|-----------|--------|------------|
| Market Cap | ±20 pts | Large-cap ($1B+), mid-cap, micro-cap, or unlisted |
| Trading Volume | ±15 pts | 24h volume relative to market cap |
| Liquidity Ratio | +5 pts | Volume/mcap ratio above 50% threshold |
| Market Ranking | ±10 pts | CoinGecko rank or unranked status |
| Project Age | ±10 pts | Genesis date — established, growing, or new |
| Online Presence | ±10 pts | Website, Twitter, GitHub verification |
| Data Availability | ±20 pts | Listed status, market data completeness |
| Token Tags | Auto | Dynamic risk tags based on findings |

**Verdict Categories:**
- 🟢 **SAFE** (75–100) — Established, listed, verified presence
- 🟡 **CAUTION** (50–74) — Moderate risk, some red flags
- 🟠 **HIGH RISK** (30–49) — Multiple warning indicators
- 🔴 **DANGER** (0–29) — Extreme caution, likely unverified

### 📈 Live Market Data

Real-time cryptocurrency market data powered by CoinGecko's public API.

**Available Queries:**
- **Price lookup** — `"price BTC ETH SOL"` or `"harga bitcoin"`
- **Top coins** — `"top 10"` or `"top 50 coins"`
- **Trending** — `"trending"` or `"what's hot"`
- **Gainers/Losers** — `"gainers"` or `"dump"` for 24h movers

**Data Points:**
- Current price (USD)
- 24h price change (percentage + visual indicator)
- Market capitalization
- 24h trading volume
- Market cap ranking
- Coin logo and metadata

### 🏦 DeFi Education

A curated knowledge base covering the most important concepts in decentralized finance.

**Topics Include:**
- DeFi fundamentals (DEXes, lending, yield farming)
- Impermanent Loss — with worked examples
- Gas fees — why they spike, how to save
- Layer 2 scaling — rollups, Arbitrum, Optimism, Base
- Tokenomics — supply analysis, red flags
- Airdrops — how they work, staying safe
- Smart contracts, DAOs, NFTs, and more

### 💬 AI Chat

Natural language interface for crypto queries. Ask anything — MiMoBot intelligently routes your question to the appropriate data source or knowledge base.

**Supported Patterns:**
- Price queries with coin detection (30+ ticker symbols)
- Contract address detection (auto-routes to Safety Checker)
- Educational questions with keyword matching
- General crypto inquiries

---

## Design System

MiMoBot features a premium glassmorphism design system with dual-theme support.

### 🌙 Dark Mode
- Deep black backgrounds (`#06070b`)
- Layered glass surfaces with blur effects
- Vibrant indigo-to-pink gradient accents
- Subtle ambient glow animations

### ☀️ Light Mode
- Clean white surfaces (`#f8f9fc`)
- Refined shadows and borders
- Softer gradient palette
- Optimized contrast ratios

### Typography
- **Font:** Inter (Google Fonts) — weights 300–900
- **Scale:** Fluid sizing with `clamp()` for responsive typography
- **Spacing:** Tight letter-spacing for headings, relaxed for body

### Components
- Glass cards with backdrop blur
- Gradient accent buttons with hover states
- Animated typing indicators
- Smooth tab transitions
- Responsive data tables
- Circular progress rings for safety scores

### Responsive Breakpoints
| Breakpoint | Layout | Navigation |
|------------|--------|------------|
| `< 768px` | Single column | Bottom tab bar |
| `769px – 1199px` | Sidebar + content | Desktop sidebar |
| `≥ 1200px` | Wide sidebar + expanded grids | Desktop sidebar |

---

## Architecture

```
┌─────────────────────────────────────────────────────┐
│                    index.html                        │
│  ┌───────────────────────────────────────────────┐  │
│  │  <style>                                       │  │
│  │    CSS Variables (Dark/Light themes)           │  │
│  │    Component Styles                            │  │
│  │    Responsive Media Queries                    │  │
│  │    Animations & Transitions                    │  │
│  │  </style>                                      │  │
│  ├───────────────────────────────────────────────┤  │
│  │  <body>                                        │  │
│  │    Sidebar Navigation (Desktop)                │  │
│  │    Top Bar (Theme Toggle, Live Badge)          │  │
│  │    Tab Panels (Chat, Safety, Market, Learn)    │  │
│  │    Input Bar                                   │  │
│  │    Mobile Bottom Navigation                    │  │
│  ├───────────────────────────────────────────────┤  │
│  │  <script>                                      │  │
│  │    Theme Manager (localStorage)                │  │
│  │    Tab Router                                  │  │
│  │    CoinGecko API Client                        │  │
│  │    Safety Analyzer (8-dimension scoring)       │  │
│  │    Knowledge Base (15+ topics)                 │  │
│  │    Query Router (pattern matching)             │  │
│  │    UI Components (messages, cards, tables)     │  │
│  │  </script>                                     │  │
│  └───────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────┘
         │                    │
         ▼                    ▼
┌─────────────────┐  ┌─────────────────┐
│  CoinGecko API  │  │  Xiaomi MiMo    │
│  (Free, No Key) │  │  (AI Model)     │
└─────────────────┘  └─────────────────┘
```

**Data Flow:**
1. User input → Query Router (pattern matching)
2. Coin/token detection → CoinGecko API fetch
3. Contract address → Safety Analyzer pipeline
4. Educational query → Knowledge Base lookup
5. Response → Rendered as HTML with data cards/tables

---

## Tech Stack

| Layer | Technology | Why |
|-------|------------|-----|
| **Frontend** | Vanilla HTML/CSS/JS | Zero dependencies, instant load, no build step |
| **AI Model** | Xiaomi MiMo | Powerful reasoning for crypto domain |
| **Market Data** | CoinGecko API | Free tier, no key required, 100+ tokens |
| **Typography** | Inter (Google Fonts) | Clean, professional, excellent readability |
| **Hosting** | GitHub Pages | Free, reliable, automatic deployments |
| **State** | localStorage | Theme preference persistence |
| **Design** | CSS Custom Properties | Dynamic theming, responsive variables |

---

## Getting Started

### Prerequisites

None. Seriously.

### Installation

**Option 1: Clone & Open**
```bash
git clone https://github.com/huolinger010/mimobot.git
cd mimobot
open index.html
```

**Option 2: Direct Download**
```bash
curl -O https://raw.githubusercontent.com/huolinger010/mimobot/main/index.html
open index.html
```

**Option 3: Live Demo**

Visit [huolinger010.github.io/mimobot](https://huolinger010.github.io/mimobot)

### Local Development

Since MiMoBot is a single HTML file with no build step:

1. Edit `index.html` in any text editor
2. Refresh your browser to see changes
3. That's it.

For live reload during development:
```bash
# Using Python
python -m http.server 8000

# Using Node.js
npx serve .

# Using PHP
php -S localhost:8000
```

---

## API Reference

### CoinGecko Endpoints Used

| Endpoint | Purpose | Rate Limit |
|----------|---------|------------|
| `/simple/price` | Token prices, 24h change, market cap | 10-30 req/min |
| `/coins/markets` | Top coins by market cap | 10-30 req/min |
| `/search/trending` | Trending tokens | 10-30 req/min |
| `/coins/{id}/contract/{address}` | Contract-based token lookup | 10-30 req/min |

All endpoints are free, require no API key, and are accessed directly from the browser.

### Query Patterns

| Pattern | Example | Action |
|---------|---------|--------|
| Price | `"price BTC ETH"` | Fetches current prices |
| Top N | `"top 10"` | Lists top N coins |
| Trending | `"trending"` | Shows trending tokens |
| Contract | `"0xdAC17F..."` | Routes to Safety Checker |
| Education | `"what is defi"` | Returns knowledge base entry |

---

## Contributing

Contributions are welcome! Here's how to get started:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Commit** your changes (`git commit -m 'Add amazing feature'`)
4. **Push** to the branch (`git push origin feature/amazing-feature`)
5. **Open** a Pull Request

### Development Guidelines

- Keep it single-file — no external dependencies
- Maintain zero build step requirement
- Test on both desktop and mobile
- Follow existing code style (ES6+, CSS custom properties)
- Update README if adding new features

---

## License

Distributed under the MIT License. See `LICENSE` for more information.

---

<div align="center">

**Built with ❤️ by [huolinger010](https://github.com/huolinger010)**

<p>
  <a href="https://huolinger010.github.io/mimobot">Live Demo</a> •
  <a href="https://github.com/huolinger010/mimobot/issues">Report Bug</a> •
  <a href="https://github.com/huolinger010/mimobot/issues">Request Feature</a>
</p>

</div>
