# BTC Historical Price Data

Historical OHLCV datasets for Bitcoin, used for cycle analysis and quantitative research.

## Contents

```
bitstamp/
  1min/BTCUSD_bitstamp_1min_YYYY.csv.gz   -- 1-minute OHLCV, Bitstamp BTC/USD, 2012–2026 (split by year)
  BTCUSD_bitstamp_daily_2012-2026.csv     -- daily aggregate
  BTCUSD_bitstamp_hourly_2012-2026.csv.gz -- hourly aggregate

binance/
  1min/BTCUSDT_binance_1min_2018-2024.csv.gz
  1min/BTCUSDT_binance_1min_2025.csv.gz
  1min/BTCUSDT_binance_1min_2026.csv.gz   -- partial, missing August 2026 (not yet published by Binance)
```

## Column schema

```
datetime_utc, open, high, low, close, volume[, source, quote_currency]
```

`datetime_utc` is always UTC. Bitstamp data is denominated in USD, Binance in USDT (see `quote_currency` where present).

## Sources

- **Bitstamp**: derived from [ff137/bitstamp-btcusd-minute-data](https://github.com/ff137/bitstamp-btcusd-minute-data), a community-maintained mirror updated daily.
- **Binance**: aggregated from monthly trade data published at [data.binance.vision](https://data.binance.vision).

## Notes

- Binance trade timestamps are in milliseconds before 2025-01-01 and microseconds from that date onward; aggregation accounts for this.
- Bitstamp coverage verified continuous, with no gaps or duplicate timestamps, across the full 2012–2026 range.

---
Last updated: September 2026.
