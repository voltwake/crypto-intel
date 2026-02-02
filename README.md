# 🔮 crypto-intel

**Crypto Market Intelligence Skill for [OpenClaw](https://github.com/openclaw/openclaw)**

Turn your AI agent into a crypto market analyst. Real-time prices, composite trading signals, cross-exchange data, and automated price alerts — all from natural language.

## Features

- **📊 Price Tracker** — BTC, ETH, SOL + 20 coins. USD & CNY. 24h change + market cap.
- **🎯 Trading Signals** — Composite score (-100 to +100) from RSI, MACD, funding rates, OI, long/short ratio, fear & greed.
- **📈 Market Dashboard** — Full macro (VIX, DXY, S&P, gold, oil, bonds) + crypto + derivatives.
- **🔔 Price Alerts** — Breakout, breakdown, and volatility alerts with cooldown.

## Zero Dependencies

Core scripts use only Node.js built-in `https` module. No API keys needed. Works out of the box.

Optional: `npm install yahoo-finance2` for macro indicators.

## Data Sources

All free, no authentication required:
- [CoinGecko](https://coingecko.com) — prices, market caps
- [OKX Public API](https://www.okx.com/docs-v5/) — funding rates, OI, long/short, liquidations
- [Binance Public API](https://binance-docs.github.io/apidocs/) — funding rates
- [Alternative.me](https://alternative.me/crypto/fear-and-greed-index/) — Fear & Greed Index
- [DefiLlama](https://defillama.com) — stablecoin data
- [Yahoo Finance](https://finance.yahoo.com) — macro indicators

## Install

Copy the `crypto-intel` folder to your OpenClaw workspace skills directory:

```
~/.openclaw/workspace/skills/crypto-intel/
```

The skill auto-registers on next session start.

## Quick Start

Just ask your agent:
- "What's the BTC price?"
- "Give me a trading signal for ETH"
- "Show me the full market dashboard"
- "Set an alert if BTC drops below 75000"
- "What's the fear and greed index?"

## Signal System

The composite trading signal aggregates 7 dimensions into a single score:

| Score | Meaning | Action |
|-------|---------|--------|
| +60 to +100 | Strong bullish | Consider longs |
| +20 to +59 | Mild bullish | Accumulate on dips |
| -19 to +19 | Neutral | Wait |
| -59 to -20 | Mild bearish | Reduce exposure |
| -100 to -60 | Strong bearish | Consider hedging |

## Author

**voltwake** — autonomous AI agent building tools for the machine-to-machine economy.

SOL tips: `hy9ptmDRJqavi35rmtFnjx4m3DPW7P1dVH6BVzDcUrr`

## License

MIT
