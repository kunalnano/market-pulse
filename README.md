# <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Chart%20Increasing.png" alt="Chart" width="32" /> Market Pulse

[![Python](https://img.shields.io/badge/Python-3.10+-3776ab?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)
[![Stars](https://img.shields.io/github/stars/kunalnano/market-pulse?style=for-the-badge&color=yellow)](https://github.com/kunalnano/market-pulse/stargazers)

> **Your personal stock market radar** — Technical indicators, news tracking, and signal scoring in one CLI.

<p align="center">
  <img src="screenshot.png" alt="Market Pulse Demo" width="700">
</p>

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| 📊 **Technical Indicators** | RSI, MACD, Bollinger Bands, Moving Averages (50/200-day) |
| 🔀 **Cross Detection** | Golden Cross / Death Cross alerts |
| 📈 **Sparklines** | 10-day visual trend at a glance |
| 🎯 **Signal Scoring** | Green/Yellow/Red with BULLISH/NEUTRAL/BEARISH verdict |
| 📰 **News Tracking** | Keywords across HN, TechCrunch, The Verge, Ars Technica |
| 🌐 **Browser Integration** | Open TradingView/Yahoo/Google Finance directly |
| 📚 **Built-in Education** | `pulse legend` explains every indicator |

---

## 🚀 Quick Start

```bash
# Clone
git clone https://github.com/kunalnano/market-pulse.git
cd market-pulse

# Setup (Python 3.10+ required)
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# Run
python pulse.py
```

**Pro tip:** Add an alias for quick access:
```bash
echo 'alias pulse="$(pwd)/venv/bin/python $(pwd)/pulse.py"' >> ~/.zshrc
source ~/.zshrc
```

---

## 📖 Usage

```bash
pulse                              # Full scan (default)
pulse stocks                       # Detailed analysis
pulse news                         # News matching keywords
pulse legend                       # Indicator explanations
pulse open AAPL                    # Open chart in browser
pulse open MSFT --source yahoo     # Yahoo Finance
pulse config --show                # View settings
pulse config --add-stock NVDA      # Add to watchlist
pulse config --remove-stock NVDA   # Remove from watchlist
pulse config --add-keyword "Tesla" # Track keyword
```

---

## 🎨 Signal Reference

| Indicator | 🟢 Bullish | 🔴 Bearish |
|-----------|-----------|-----------|
| **RSI** | < 30 (oversold) | > 70 (overbought) |
| **MACD** | Bullish crossover | Bearish crossover |
| **MA Cross** | Golden (50 > 200) | Death (50 < 200) |
| **vs SMA200** | Price above | Price below |
| **52w Range** | < 25% (near low) | > 85% (near high) |
| **Bollinger** | < 20% (oversold) | > 80% (overbought) |
| **P/E Ratio** | < 15 (cheap) | > 35 (expensive) |

Run `pulse legend` for detailed explanations with analogies.

---

## ⚙️ Configuration

First run creates `config.json` with defaults:
- **Stocks:** AAPL, GOOGL
- **Keywords:** Google, Apple, AI, OpenAI, Claude, Anthropic, Gemini
- **Feeds:** Hacker News, TechCrunch, The Verge, Ars Technica

Config is gitignored (contains your personal watchlist).

---

## 🔧 Dependencies

- `yfinance` — Stock data & fundamentals
- `feedparser` — RSS parsing
- `rich` — Beautiful terminal UI
- `pandas` / `numpy` — Data crunching

---

## 📄 License

MIT — Do whatever you want with it.

---

<p align="center">
  <sub>Built in one conversation with Claude Opus. The kind of tool that used to take a weekend now takes an hour.</sub>
</p>
