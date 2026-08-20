# Custom VixFix

Custom [Larry Williams VixFix](../../Larry%20Williams%20VixFix/README.md) pane combining three buy lookbacks, Weis Wyckoff wave volume, and `TVC:VIX`.

## What was customised

- Keeps only the three green VixFix buy plots; inverse sell plots and trade statistics are omitted.
- Shades the background green while a VixFix value is below zero. The 132-bar lookback has the brightest shade, followed by 66 and 22.
- Layers translucent yellow over the green background on every bar where `TVC:VIX` is above 20.
- Adds Weis wave-volume columns while retaining the standalone Weis indicator’s method, price-source, volume, oscillation, and normalization settings.
- Adds the `TVC:VIX` close as an orange line.

The pane uses fixed display bands:

- VixFix: -5 to 50, with zero at 0
- VIX: 50 to 100
- Weis: 100 to 200, with zero at 150

VixFix and VIX values are clipped to their bands. Weis uses a fixed divisor before it is offset and clipped. A fixed divisor preserves the original bars’ relative proportions until a column reaches a boundary; adjust it per instrument so clipping is uncommon.

## Inputs

| Parameter | Default | Notes |
|-----------|---------|-------|
| Length 1 / 2 / 3 | 22 / 66 / 132 | About one, three, and six months of trading days |
| Renko Assignment Method | ATR | ATR, fixed-price, or part-of-price Weis reversal assignment |
| Value | 14 | ATR length, fixed brick size, or price divisor, depending on the method |
| Price Source | Close | Close, open/close, or high/low Weis reversal source |
| Use True Range instead of Volume | Auto | Uses true range when configured or when volume is unavailable |
| Oscillating | true | Places down-wave columns below the Weis zero line |
| Normalize | false | Shows average rather than cumulative wave volume |
| Display Divisor | 15,000,000 | Scales Weis columns to fit their display band |

The three VixFix lengths are lookbacks on the chart timeframe, not separate requested timeframes. The indicator recalculates on an open bar; evaluate signals after the bar closes.

## Citations

| Source | Citation | Role |
|--------|----------|------|
| Larry Williams VixFix | [`larry-williams-vixfix`](../../Larry%20Williams%20VixFix/) | Base indicator in this repository that this script is adapted from |
| Williams’ VixFix | Williams, L. [VixFix](https://www.ireallytrade.com/newsletters/VIXFix.pdf). | Original published description of the method |
| Weis Wyckoff Method | [`weis-wyckoff-method`](../../Weis%20Wyckoff%20Method/weis-wyckoff-method) | Source of the integrated wave-volume calculations and configuration |

See [Installation](../../README.md#installation) and [License](../../README.md#license) in the repository readme. The legal disclaimer is in [DISCLAIMER.md](../../DISCLAIMER.md).
