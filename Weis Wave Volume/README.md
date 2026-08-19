# Weis Wave Volume Indicator

Weis Wave Volume is a TradingView Pine Script indicator that plots cumulative volume for each directional price wave in a separate pane.

## ✨ Features

- **Wave volume histogram**: Accumulates volume (or true range) until the wave reverses, then resets
- **Renko assignment methods**: ATR, Traditional, or Part of Price brick sizing
- **Price source options**: Close, Open / Close, or High / Low
- **True range fallback**: Always / Auto / Never (Auto uses true range when volume is unavailable)
- **Oscillating**: Optional signed histogram with down-waves below zero
- **Normalize**: Optional average volume per bar in the current wave

Default inputs match the common ATR 14, Close, Auto true-range setup on the chart timeframe. Oscillating and Normalize are off by default.

## 🚀 Installation

1. Open TradingView and navigate to the Pine Editor
2. Copy the contents of `weis-wave-volume-indicator-script`
3. Paste into the Pine Editor
4. Click "Add to Chart"
5. Configure your preferred settings in the indicator inputs

## 📄 License

This project is licensed under the [Mozilla Public License 2.0](https://www.mozilla.org/MPL/2.0/). See the [LICENSE](../LICENSE) file for details.
