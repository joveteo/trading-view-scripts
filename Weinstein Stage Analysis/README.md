# Weinstein Stage Analysis Indicator

Weinstein Stage Analysis is a TradingView Pine Script v6 indicator that maps Stan Weinstein's four-stage cycle onto the chart by recolouring the candles themselves. It is adapted from the [TrendSpider Weinstein Stage Analysis](https://charts.trendspider.com/shared/679813ca6550e0000970233f) implementation, using a 30-period moving average (weekly by default) and a configurable proximity band.

## 📋 Overview

The indicator classifies price into one of four stages and paints the **entire candle** (body, border, and wick) in that stage colour. A stage moving average is plotted for reference.

- **Stage 1** (light green): Basing / accumulation after a decline, near a flattening or recovering average.
- **Stage 2** (green): Confirmed advance. The candle body holds above a rising average by more than the range band.
- **Stage 3** (orange): Distribution / topping after Stage 2, until a Stage 4 breakdown.
- **Stage 4** (red): Confirmed decline. The candle body holds below a falling average by more than the range band.

Stages are calculated on the selected higher timeframe (weekly by default) and mapped onto every bar on the current chart.

## ✨ Features

- Pine Script v6 overlay that paints body, border, and wick in the stage colour (`plotcandle` drawn in front of the chart symbol)
- Higher-timeframe calculation (default weekly) so the same stage can be viewed on any chart timeframe
- Configurable MA type (SMA, EMA, WMA, RMA, VWMA, HMA) and length
- Adjustable proximity band around the MA
- Customisable stage colours
- Optional stage-change labels and alert conditions for each stage

## 🚀 Installation

1. Open TradingView and navigate to the Pine Editor
2. Copy the contents of `weinstein-stage-analysis-indicator-script`
3. Paste into the Pine Editor
4. Click "Add to Chart"
5. Configure your preferred settings in the indicator inputs
6. If the original green/red candle edges still show, hide the symbol’s Body, Wicks, and Border under Chart settings → Symbol → Style (or click the eye icon next to the ticker)

## ⚙️ Configuration

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Stage Timeframe | Timeframe | W | Timeframe used for stage detection. Weekly is the classic Weinstein setting. |
| MA Length | Integer | 30 | Lookback for the stage moving average. |
| MA Type | String | SMA | Moving average algorithm. |
| Within Range % | Float | 5 | Percentage band around the MA used to confirm Stage 2 and Stage 4. |
| Stage 1–4 Colours | Colour | light green / green / orange / red | Candle colours for each stage. |
| Colour Bars | Boolean | true | Paint each candle’s body, border, and wick by stage. |
| Show MA | Boolean | true | Plot the higher-timeframe moving average. |
| Show Stage Labels | Boolean | false | Label bars where the stage changes. |

## ⚠️ Important Notes

- TradingView’s `barcolor()` function cannot change wicks or borders, so this script draws stage candles in front of the chart. If any of the original candle still shows through, hide the symbol’s Body, Wicks, and Border in Chart settings → Symbol → Style.
- This is an interpretation of Weinstein stage analysis and will not match every discretionary rule from the original method.
- Stages are computed on the selected higher timeframe. Use a chart timeframe that is the same or lower (for example daily or weekly with the default weekly stages).
- Historical bars in the same higher-timeframe period share that period's completed stage. The current (forming) higher-timeframe bar can change stage until it closes.
- Use with other confirmation and risk management. This tool does not constitute financial advice.

## ⚠️ Disclaimer

This indicator is for educational and informational purposes only. It does not constitute financial advice. Trading involves risk, and past performance does not guarantee future results. Always conduct your own research and consider consulting with a financial advisor before making trading decisions. See [DISCLAIMER.md](../DISCLAIMER.md).

## 📄 License

This project is licensed under the [Mozilla Public License 2.0](https://www.mozilla.org/MPL/2.0/). See the [LICENSE](../LICENSE) file for details.
