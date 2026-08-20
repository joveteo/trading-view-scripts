# Custom Supertrend

Custom SuperTrend overlay. A standard SuperTrend is an ATR trailing line that flips with price. This version adds an SMA and a time-in-trend table for a specific chart setup.

## What was customised

- SMA overlay on the same pane (length 200 by default).
- Table of the share of loaded bars spent in green versus red, plus the current streak.
- Optional bar colouring by SuperTrend direction.
- Buy and sell labels when the SuperTrend direction flips.

ATR period, multiplier, source, SMA length, and table position are inputs.

## Citations

| Source | Citation | Role |
|--------|----------|------|
| SuperTrend | [TradingView SuperTrend](https://www.tradingview.com/support/solutions/43000634738-supertrend/) | Implementation this script is adapted from |

See [Installation](../../README.md#installation) and [License](../../README.md#license) in the repository readme. The legal disclaimer is in [DISCLAIMER.md](../../DISCLAIMER.md).
