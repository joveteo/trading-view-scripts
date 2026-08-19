# Weis Wave Volume Indicator

Weis Wave Volume is a TradingView Pine Script indicator that calculates cumulative volume for ATR-defined price waves and recolors the chart’s native candlesticks.

## ✨ Features

- **Native bar colours**: Changes the chart’s own candlesticks (does not draw a second candle series on top)
- **Four colours**:
  - Bright green: up-wave bar that closes at or above its open
  - Orange: up-wave bar that closes below its open
  - Bright red: down-wave bar that closes at or below its open
  - Light green: down-wave bar that closes above its open
- **Reference defaults**: ATR 14, Close price source, Auto true-range fallback, chart timeframe, and oscillating wave volume
- **Renko assignment methods**: ATR, Traditional, or Part of Price brick sizing
- **Price source options**: Close, Open / Close, or High / Low
- **Weis Wave Volume calculation**: Accumulates volume within each detected wave and resets when direction changes
- **Main chart only**: No separate volume pane

The oscillating wave-volume result is calculated but hidden so the indicator stays on the main chart. This uses native `barcolor()` only—there is no candle overlay or highlight. TradingView controls wick and border colours separately; in Chart settings → Symbol, set them to follow the candle or match the body. Keep the chart type on Candles.

## 🚀 Installation

1. Open TradingView and navigate to the Pine Editor
2. Copy the contents of `weis-wave-volume-indicator-script`
3. Paste into the Pine Editor
4. Click "Add to Chart"
5. Configure your preferred settings in the indicator inputs

## 📄 License

This project is licensed under the [Mozilla Public License 2.0](https://www.mozilla.org/MPL/2.0/). See the [LICENSE](../LICENSE) file for details.
