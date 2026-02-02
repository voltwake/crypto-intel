---
name: crypto-intel
description: >
  Crypto market intelligence toolkit. Real-time prices, trading signals, cross-exchange data,
  macro indicators, and price alerts. Use when the user asks about crypto prices, market conditions,
  trading signals, fear & greed index, funding rates, open interest, or needs price alerts.
  Supports BTC, ETH, SOL, and 20+ coins. Data from CoinGecko, OKX, Binance, Yahoo Finance.
---

# Crypto Intel

Turn your agent into a crypto market analyst. Zero mandatory dependencies — works out of the box.

## Quick Reference

All scripts are in `{baseDir}/scripts/`. Run with `node`.

| Command | What it does |
|---------|-------------|
| `node {baseDir}/scripts/crypto.js` | BTC/ETH/SOL prices (USD+CNY, 24h change, market cap) |
| `node {baseDir}/scripts/crypto.js btc eth doge` | Specific coins |
| `node {baseDir}/scripts/crypto.js --top 10` | Top 10 by market cap |
| `node {baseDir}/scripts/signal.js` | BTC composite trading signal (-100 to +100) |
| `node {baseDir}/scripts/signal.js eth --detail` | ETH signal with per-dimension breakdown |
| `node {baseDir}/scripts/signal.js btc --json` | JSON output for programmatic use |
| `node {baseDir}/scripts/market-data.js` | Full market dashboard (macro + crypto + sentiment) |
| `node {baseDir}/scripts/market-data.js macro` | Macro only (VIX, DXY, S&P, gold, oil, bonds) |
| `node {baseDir}/scripts/market-data.js sentiment` | Fear & Greed Index |
| `node {baseDir}/scripts/market-data.js funding` | Funding rates & open interest |
| `node {baseDir}/scripts/market-data.js derivatives` | Deep derivatives (long/short ratio, liquidations) |
| `node {baseDir}/scripts/alert.js set BTC below 75000` | Set price alert |
| `node {baseDir}/scripts/alert.js set ETH above 3000` | Set breakout alert |
| `node {baseDir}/scripts/alert.js set SOL change 10` | 24h volatility alert (±10%) |
| `node {baseDir}/scripts/alert.js list` | List active alerts |
| `node {baseDir}/scripts/alert.js check` | Check if any alerts triggered |

## Signal Scoring System

`signal.js` produces a composite score from -100 (extreme bearish) to +100 (extreme bullish):

| Score Range | Interpretation | Suggested Action |
|-------------|---------------|-----------------|
| +60 to +100 | Strong bullish | Consider long positions |
| +20 to +59 | Mild bullish | Accumulate on dips |
| -19 to +19 | Neutral | Wait for clearer signal |
| -59 to -20 | Mild bearish | Reduce exposure |
| -100 to -60 | Strong bearish | Consider hedging/shorts |

Dimensions: RSI, MACD, funding rate trend, liquidation imbalance, fear & greed, open interest change.

For detailed metric explanations, read `{baseDir}/references/indicators.md`.

## Dependencies

**Core (zero deps):** `crypto.js`, `signal.js`, `alert.js` — pure Node.js, works immediately.

**Enhanced (optional):** `market-data.js` macro features need `yahoo-finance2`:
```bash
npm install yahoo-finance2
```
Crypto/sentiment/funding/derivatives features work without it.

## Data Sources (all free, no API keys needed)

- CoinGecko — prices, market caps, 24h changes
- OKX Public API — funding rates, open interest, long/short ratio, liquidations
- Binance Public API — funding rates, OI cross-reference
- Alternative.me — Fear & Greed Index
- DefiLlama — stablecoin market caps
- Yahoo Finance — VIX, DXY, S&P500, gold, oil, bonds (requires yahoo-finance2)
