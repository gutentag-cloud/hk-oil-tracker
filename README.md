# Hong Kong Oil & Petrol Tracker

A single-file, zero-build dashboard for oil markets and Hong Kong energy:

- **Crude & products** — Brent, WTI, RBOB, heating oil, natural gas
- **Oil indexes** — Arca Oil (XOI), Oil Services (OSX), Natural Gas (XNG), S&P Oil&Gas E&P, HSI, S&P 500
- **ETFs** — USO, BNO, USL, UCO, SCO (inverse), XLE, XOP, OIH, VDE, IYE, AMLP
- **HK energy** — Sinopec, PetroChina, CNOOC, COSL, Kunlun, Towngas, China Gas, ENN, Shenhua…
- **Global majors & US O&G** — majors, services, refiners, E&P
- **HK pump prices** — editable, saved in your browser

## Forecasting

Every instrument can be projected with an **8-model ensemble** (Naive, Drift,
Linear, Holt, Holt-Winters, ARIMA, Kalman, Seasonal-Naive) that is:

1. trained on the instrument's own history,
2. cross-validated by rolling-origin backtest (5 folds),
3. weighted by inverse out-of-sample MAPE (weights capped at 40%),
4. reported with OOB MAPE + directional hit-rate and empirical P10–P90 bands.

The **Screener** page runs the same ensemble across the whole universe and
ranks predicted up/down moves with confidence metrics.

## Technicals

MA (SMA/EMA, day-based periods auto-converted to weekly/monthly bars),
RSI, MACD, Bollinger Bands, Stochastic, OBV, volume, log-free group compare,
zoom controls (`+` `-` `0`).

## Run

```bash
open index.html          # that's it — data from Yahoo Finance via CORS proxies
```

No build step, no server, no dependencies. Charts by
[Lightweight Charts](https://tradingview.github.io/lightweight-charts/).

*Market data may be delayed; forecasts are statistical estimates, not investment advice.*
