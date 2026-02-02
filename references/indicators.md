# Indicator Reference

## Signal Dimensions

### RSI (Relative Strength Index)
- Range: 0-100. Below 30 = oversold (bullish), above 70 = overbought (bearish)
- Calculated from OKX 4H candlestick data using 14-period RSI
- Weight in composite: ~20%

### MACD (Moving Average Convergence Divergence)
- Positive histogram = bullish momentum, negative = bearish
- Calculated from OKX candlestick close prices (12/26/9)
- Weight: ~15%

### Funding Rate
- Positive = longs pay shorts (market is long-heavy, slightly bearish)
- Negative = shorts pay longs (market is short-heavy, slightly bullish)
- Extreme values (>0.1% or <-0.1%) signal potential reversals
- Source: OKX + Binance
- Weight: ~15%

### Open Interest (OI)
- Rising OI + rising price = strong trend (bullish in uptrend)
- Rising OI + falling price = bearish pressure building
- Falling OI = positions unwinding, trend weakening
- Source: OKX
- Weight: ~15%

### Long/Short Ratio
- >1.5 = crowded long (contrarian bearish)
- <0.7 = crowded short (contrarian bullish)
- Source: OKX Rubik API
- Weight: ~15%

### Fear & Greed Index
- 0-25 = Extreme Fear (contrarian buy signal)
- 25-45 = Fear
- 45-55 = Neutral
- 55-75 = Greed
- 75-100 = Extreme Greed (contrarian sell signal)
- Source: Alternative.me
- Weight: ~10%

### Liquidation Imbalance
- More long liquidations = bearish pressure (longs getting wrecked)
- More short liquidations = bullish pressure (shorts getting squeezed)
- Source: OKX Rubik API
- Weight: ~10%

## Market Data Modules

### Macro
VIX (volatility fear gauge), DXY (dollar strength), S&P500, Nasdaq, Gold, Crude Oil, 10Y/2Y Treasury yields.

### Stablecoins
Total stablecoin market cap and top stablecoins by market cap. Rising stablecoin supply = capital inflow to crypto.

### Derivatives
Funding rate history, insurance fund trends, leveraged borrowing rates. Comprehensive derivatives analysis for gauging market leverage and positioning.
