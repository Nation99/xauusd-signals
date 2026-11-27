# XAUUSD Signal Desk

A static, single-page gold dashboard built around **1H market structure**.

- Live XAU/USD spot quote (TradingView OANDA feed, refreshed every 3 s)
- 1H candlestick chart (TradingView Lightweight Charts)
- Trend channel, support/resistance, EMA context
- Rule-based structure model: HH+HL = bullish, LH+LL = bearish, otherwise no trades
- Bias only flips on a 1H close beyond the key swing **plus** a confirmed higher low / lower high
- Sells only in bearish structure, buys only in bullish structure
- Entry / Stop / TP1–TP3, risk calculator, local signal log
- No backend, no API key required

## Live

<https://nation99.github.io/xauusd-signals/>

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The complete self-contained site (CSS, JS and chart library inlined). |
| `xauusd-signals.zip` | Modular source: `index.html`, `assets/css`, `assets/js`, README. |

## Deploy

The site is published with GitHub Pages from the repository root. To host it elsewhere, drop `index.html` on any static host, or unzip `xauusd-signals.zip` and serve that folder.

## Data

The spot quote — price, daily open / high / low and change % — comes from TradingView's OANDA:XAUUSD feed, polled every 3 seconds. Candles are built from Coinbase's PAXG-USD market (gold-backed token) and rescaled onto the live spot quote so chart levels, entries and stops agree with the displayed price. gold-api.com is the fallback quote. Twelve Data can be added in Settings for native XAU/USD candles.

## Rules (short)

1. Read the last confirmed 1H swing high and swing low.
2. Bias changes only when the full flip sequence completes; a single close beyond the key level puts structure "under question" and blocks new trades.
3. Trade only with the bias, at a retest of the key level or after a failed breakout.
4. Stops go just beyond the key structure level.

Not financial advice. Public data can be delayed or wrong; trading gold carries a high risk of loss.
