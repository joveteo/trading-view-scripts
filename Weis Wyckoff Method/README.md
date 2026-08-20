# Weis Wyckoff Method

[Published on TradingView](https://www.tradingview.com/script/tZZMmy1P-Weis-Wyckoff-Method/). Plots cumulative volume for each directional price wave in a separate pane.

The construction comes from David H. Weis, who adapted Richard D. Wyckoff’s wave-chart teaching for modern markets. Weis did not publish a closed-form equation. He described a method: split price into alternating up and down swings, then sum volume inside each swing so effort can be compared with result, rather than with clock time.

Wyckoff told students to think in waves. Weis recast that idea as wave volume in *Trades About to Happen: A Modern Adaptation of the Wyckoff Method* (Wiley, 2013). If an instrument has no volume, the book says to use true range instead.

## Construction

Waves are built from closes, not highs and lows:

- Stay in the current wave until the close reverses by a chosen amount (points, ticks, or a wave size).
- On that reversal, close the wave and start a new one in the opposite direction.
- Wave volume is the sum of bar volume (or true range) from the first bar of the swing through the last.

Later ports encode that rule set as a zigzag plus cumulative volume. Reversal units such as ATR, percent, or a fixed price amount are implementation choices, not a formula published by Weis.

Default inputs match a common ATR 14, Close, Auto true-range setup on the chart timeframe. Oscillating is on by default; Normalize is off.

ATR, Traditional, or Part of Price sets the brick size. Close, Open / Close, or High / Low sets the reversal source. Auto true-range uses true range only when volume is missing.

## Citations

| Source | Citation | Role |
|--------|----------|------|
| *Trades About to Happen* | Weis, D. H. (2013). *Trades About to Happen: A Modern Adaptation of the Wyckoff Method*. Hoboken, NJ: John Wiley & Sons. ISBN 978-0-470-48780-8. | First full published description of Weis Wave |
| *Studies in Tape Reading* | Wyckoff, R. D. (1910). *Studies in Tape Reading*. | Conceptual predecessor: wave charts, not Weis Wave itself |
| Weis Wave Plugin | [weisonwyckoff.com/weis-wave](http://weisonwyckoff.com/weis-wave/) | Author’s official software implementation and worked chart examples |

This script is an independent Pine implementation of the published construction, not the official Weis Wave plugin.

See [Installation](../README.md#installation) and [License](../README.md#license) in the repository readme. The legal disclaimer is in [DISCLAIMER.md](../DISCLAIMER.md).
