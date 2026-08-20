# Custom VixFix

Custom [Larry Williams VixFix](../../Larry%20Williams%20VixFix/README.md). The published indicator plots buy and sell deviation from recent highs and lows. This version adds a statistics table that scores signals after a chosen trade duration.

## What was customised

- Win/loss statistics table after a configurable trade duration.
- Hierarchical signal counting so a longer lookback is not also counted as a shorter one.

Buy values go negative when price stretches below recent lows. Sell values go positive when price stretches above recent highs. The longest lookback that triggers wins, so a 132-day signal is not also counted as 66 or 22.

The indicator reprints. Act after the bar closes.

## Inputs

| Parameter | Default | Notes |
|-----------|---------|-------|
| Length 1 / 2 / 3 | 22 / 66 / 132 | About one, three, and six months of trading days |
| Show Statistics Table | true | Win/loss counts after the trade duration |
| Trade Duration (Days) | 30 | Bars to wait before scoring a signal |

Stocks often use 22/66/132 with a 30-day duration. Shorter lookbacks suit faster markets.

## Citations

| Source | Citation | Role |
|--------|----------|------|
| Williams’ VixFix | Williams, L. [VixFix](https://www.ireallytrade.com/newsletters/VIXFix.pdf). | Original published description of the method |

See [Installation](../../README.md#installation) and [License](../../README.md#license) in the repository readme. The legal disclaimer is in [DISCLAIMER.md](../../DISCLAIMER.md).
