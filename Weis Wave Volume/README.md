# Weis Wave Volume Indicator

Weis Wave Volume is a TradingView Pine Script indicator that recolors the chart’s native candlesticks by Weis wave direction and volume strength.

## ✨ Features

- **Four native bar colours**: Bright green / dark green for up-waves and bright red / dark red for down-waves
- **Volume strength**: Strong colours when the current wave’s cumulative volume exceeds the previous wave; weak colours otherwise
- **Renko assignment methods**: ATR, Traditional, or Part of Price brick sizing
- **Price source options**: Close, Open / Close, or High / Low
- **True range fallback**: Optionally use true range instead of volume (Always / Auto / Never)
- **Customisable colours**: Choose all four wave colours
- **Main chart only**: No separate volume pane

This recolors the native candle bodies. If wicks or borders still use the chart theme, set those Symbol colours to match the body in TradingView chart settings.

## 🚀 Installation

1. Open TradingView and navigate to the Pine Editor
2. Copy the contents of `weis-wave-volume-indicator-script`
3. Paste into the Pine Editor
4. Click "Add to Chart"
5. Configure your preferred settings in the indicator inputs

## 📄 License

This project is licensed under the [Mozilla Public License 2.0](https://www.mozilla.org/MPL/2.0/). See the [LICENSE](../LICENSE) file for details.
