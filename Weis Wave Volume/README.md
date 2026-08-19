# Weis Wave Volume Indicator

Weis Wave Volume is a TradingView Pine Script indicator that recolors the chart’s native candlesticks by Weis wave direction.

## ✨ Features

- **Native bar colours**: Changes the chart’s own candlesticks (does not draw a second candle series on top)
- **Four colours**:
  - Bright teal: up-wave bar that closes at or above its open
  - Dark teal: up-wave bar that closes below its open
  - Bright red: down-wave bar that closes at or below its open
  - Maroon: down-wave bar that closes above its open
- **Renko assignment methods**: ATR, Traditional, or Part of Price brick sizing
- **Price source options**: Close, Open / Close, or High / Low
- **Main chart only**: No separate volume pane

This uses native bar colouring. For wicks and borders to match the body, open Chart settings → Symbol and set wick and border colours to follow the candle (or the same as the body). Keep the chart type on Candles.

## 🚀 Installation

1. Open TradingView and navigate to the Pine Editor
2. Copy the contents of `weis-wave-volume-indicator-script`
3. Paste into the Pine Editor
4. Click "Add to Chart"
5. Configure your preferred settings in the indicator inputs

## 📄 License

This project is licensed under the [Mozilla Public License 2.0](https://www.mozilla.org/MPL/2.0/). See the [LICENSE](../LICENSE) file for details.
