# Weis Wyckoff Method

Weis Wyckoff Method is a TradingView Pine Script indicator that plots cumulative volume for each directional price wave in a separate pane.

The construction comes from **David H. Weis**, who adapted **Richard D. Wyckoff’s** wave-chart teaching for modern markets. Weis did not publish a closed-form equation. He described a method: split price into alternating up and down swings, then sum volume inside each swing so effort can be compared with result, rather than with clock time.

Wyckoff told students to think in waves. Weis recast that idea as wave volume and published it in *Trades About to Happen: A Modern Adaptation of the Wyckoff Method* (Wiley, 2013). In the book he also states that if an instrument has no volume, **true range** should be used in its place.

## Construction

Waves are built from **closes**, not highs and lows:

- Stay in the current wave until the close reverses by a chosen amount (points, ticks, or a wave size).
- On that reversal, close the wave and start a new one in the opposite direction.
- Wave volume is the **sum of bar volume** (or true range) from the first bar of the swing through the last.

Later ports encode that rule set as a zigzag plus cumulative volume. Reversal units such as ATR, percent, or a fixed price amount are implementation choices, not a formula published by Weis.

Default inputs in this script match a common ATR 14, Close, Auto true-range setup on the chart timeframe. Oscillating is on by default; Normalize is off.

## ✨ Features

- **Wave volume histogram**: Accumulates volume (or true range) until the wave reverses, then resets
- **Renko assignment methods**: ATR, Traditional, or Part of Price brick sizing
- **Price source options**: Close, Open / Close, or High / Low
- **True range fallback**: Always / Auto / Never (Auto uses true range when volume is unavailable)
- **Oscillating**: Optional signed histogram with down-waves below zero
- **Normalize**: Optional average volume per bar in the current wave

## 📚 Citations

| Source | Citation | Role |
|--------|----------|------|
| *Trades About to Happen* | Weis, D. H. (2013). *Trades About to Happen: A Modern Adaptation of the Wyckoff Method*. Hoboken, NJ: John Wiley & Sons. ISBN 978-0-470-48780-8. | First full published description of Weis Wave |
| *Studies in Tape Reading* | Wyckoff, R. D. (1910). *Studies in Tape Reading*. | Conceptual predecessor: wave charts, not Weis Wave itself |
| Weis Wave Plugin | [weisonwyckoff.com/weis-wave](http://weisonwyckoff.com/weis-wave/) | Author’s official software implementation and worked chart examples |

This repository’s script is an independent Pine implementation of the published construction, not the official Weis Wave plugin.

## 🚀 Installation

1. Open TradingView and navigate to the Pine Editor
2. Copy the contents of `weis-wyckoff-method-indicator-script`
3. Paste into the Pine Editor
4. Click "Add to Chart"
5. Configure your preferred settings in the indicator inputs

## 📄 License

This project is licensed under the [Mozilla Public License 2.0](https://www.mozilla.org/MPL/2.0/). See the [LICENSE](../LICENSE) file for details.
