# XAUUSD Signal Desk

A static, single-page gold dashboard built around **1H market structure**.

- Live gold price and a 1H candlestick chart (TradingView Lightweight Charts)
- Trend channel, support/resistance, EMA context
- Rule-based structure model: HH+HL = bullish, LH+LL = bearish, otherwise no trades
- Bias only flips on a 1H close beyond the key swing **plus** a confirmed higher low / lower high
- Sells only in bearish structure, buys only in bullish structure
- Entry / Stop / TP1–TP3, risk calculator, local signal log
- No backend, no API key required

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The complete self-contained site (CSS, JS and chart library inlined). |
| `xauusd-signals.zip` | Modular source: `index.html`, `assets/css`, `assets/js`, README, `.nojekyll`. |

## Deploy

The site is published with GitHub Pages from the repository root. To host it elsewhere, drop `index.html` on any static host, or unzip `xauusd-signals.zip` and serve that folder.

## Data

The live quote is the Coinbase PAXG-USD bid/ask midpoint and the candles come from the same market, so price and chart stay on one coherent gold-tracking feed. gold-api.com is the fallback. Twelve Data can be added in Settings for XAU/USD candles.

## Rules (short)

1. Read the last confirmed 1H swing high and swing low.
2. Bias changes only when the full flip sequence completes; a single close beyond the key level puts structure "under question" and blocks new trades.
3. Trade only with the bias, at a retest of the key level or after a failed breakout.
4. Stops go just beyond the key structure level.

Not financial advice. Public data can be delayed or wrong; trading gold carries a high risk of loss.
