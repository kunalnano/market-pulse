# Market Pulse 📈

A CLI tool for personal stock watchlist monitoring with technical indicators and news tracking.

Built for quick daily triage: see which stocks need attention, understand why, then drill down.

![Market Pulse Screenshot](https://via.placeholder.com/800x400?text=pulse+scan+screenshot)

## Features

- **Technical Indicators**: RSI, MACD, Bollinger Bands, Moving Averages (50/200), Golden/Death Cross detection
- **Signal Scoring**: Green/Yellow/Red signals with overall BULLISH/NEUTRAL/BEARISH verdict
- **10-Day Sparklines**: Visual trend at a glance
- **News Monitoring**: Track keywords across Hacker News, TechCrunch, The Verge, Ars Technica
- **Browser Integration**: Open TradingView/Yahoo/Google Finance charts directly
- **Built-in Education**: `pulse legend` explains what each indicator means

## Installation

```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/market-pulse.git
cd market-pulse

# Create virtual environment (requires Python 3.10+)
python3 -m venv venv
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Optional: Add alias to your shell
echo 'alias pulse="/path/to/market-pulse/venv/bin/python /path/to/market-pulse/pulse.py"' >> ~/.zshrc
source ~/.zshrc
```

## Usage

```bash
pulse                              # Run full scan (default)
pulse scan                         # Same as above - scorecard for all stocks
pulse stocks                       # Detailed analysis with all metrics
pulse news                         # Recent news matching your keywords
pulse legend                       # Explain what each indicator means
pulse open AAPL                    # Open TradingView chart in browser
pulse open MSFT --source yahoo     # Open Yahoo Finance instead
pulse config --show                # View current configuration
pulse config --add-stock NVDA      # Add stock to watchlist
pulse config --remove-stock NVDA   # Remove stock from watchlist
pulse config --add-keyword "Tesla" # Add keyword to track
```

## Example Output

```
╭──────────────────────────────────────────────────────────────────────────────╮
│ AAPL - Apple Inc.  |  $243.85  |  ● NEUTRAL  (3 green / 3 red)               │
│ 10-day: ▄▇▁▄█▆▇▆▃▁  → -0.4%                                                  │
╰──────────────────────────────────────────────────────────────────────────────╯
                                                                         
  Indicator           Value   Signal     Meaning                         
 ─────────────────────────────────────────────────────────────────────── 
  RSI                  31.1   🟡         Neutral zone                    
  MACD              Bearish   🔴         Momentum falling                
  MA Cross           Golden   🟢         50-day above 200-day            
  vs SMA200           Above   🟢         In long-term uptrend            
  52w Range             85%   🔴         Near 52-week high               
  Bollinger             18%   🟢         Near lower band                 
  P/E Ratio            36.4   🔴         Expensive                       
  Volume           0.9x avg   🟡         Normal volume                   
```

## Indicators Explained

| Indicator | What It Measures | 🟢 Green (Bullish) | 🔴 Red (Bearish) |
|-----------|------------------|-------------------|-----------------|
| **RSI** | Momentum exhaustion | < 30 (oversold) | > 70 (overbought) |
| **MACD** | Trend momentum | Bullish crossover | Bearish crossover |
| **MA Cross** | 50-day vs 200-day | Golden Cross | Death Cross |
| **vs SMA200** | Long-term trend | Price above | Price below |
| **52w Range** | Position in yearly range | < 25% (near low) | > 85% (near high) |
| **Bollinger** | Volatility position | < 20% (oversold) | > 80% (overbought) |
| **P/E Ratio** | Valuation | < 15 (cheap) | > 35 (expensive) |

Run `pulse legend` for detailed explanations with analogies.

## Configuration

On first run, `config.json` is created with defaults:

- **Stocks**: AAPL, GOOGL (customize with `--add-stock`)
- **Keywords**: Google, Apple, AI, OpenAI, Claude, etc.
- **News feeds**: HN, TechCrunch, The Verge, Ars Technica

The config file is gitignored since it contains your personal watchlist.

## Automation (Optional)

Run hourly via cron:

```bash
0 * * * * /path/to/venv/bin/python /path/to/pulse.py scan >> /tmp/pulse.log 2>&1
```

## Dependencies

- `yfinance` - Stock data and fundamentals
- `feedparser` - RSS feed parsing
- `rich` - Terminal UI (tables, panels, colors)
- `pandas` / `numpy` - Data analysis

## License

MIT - Do whatever you want with it.

## Credits

Built in one conversation with Claude (Opus). The kind of tool that used to take a weekend now takes an hour.
