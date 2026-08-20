# Custom Supertrend

Combined SuperTrend and Weinstein stage-analysis overlay. SuperTrend supplies ATR-based trend changes and entry/exit markers, while Weinstein analysis maps the broader four-stage market cycle from a higher timeframe.

## What was customised

- SuperTrend calculations produce buy and sell labels without plotting a connecting trend line.
- Only the Weinstein stage moving average is plotted.
- Current Weinstein stage in the Data Window and status line.
- Optional bar colouring by SuperTrend direction or Weinstein stage.
- Buy and sell labels when the SuperTrend direction flips.
- Optional labels and alerts when the Weinstein stage changes.

The SuperTrend and Weinstein calculations remain independent: buy and sell labels mark SuperTrend flips and are not filtered by the current Weinstein stage.

## Weinstein stages

- Stage 1 (light green): basing after a decline.
- Stage 2 (green): the candle body is above a rising stage average by more than the configured band.
- Stage 3 (orange): distribution after Stage 2 and before a Stage 4 breakdown.
- Stage 4 (red): the candle body is below a falling stage average by more than the configured band.

The classic defaults are a weekly timeframe and 30-week SMA. Use a chart timeframe at or below the selected stage timeframe. The current higher-timeframe stage can change until that candle closes.

When both candle-colouring options are enabled, the fully drawn Weinstein stage candles appear in front of the native candles and take visual priority over the lighter SuperTrend tint.

## Inputs

SuperTrend settings include the ATR period, multiplier, source, labels, and candle colouring. Weinstein settings include the stage timeframe, MA length and type, confirmation-band percentage, stage colours, candle colouring, MA display, and stage labels.

## Citations

| Source | Citation | Role |
|--------|----------|------|
| SuperTrend | [TradingView SuperTrend](https://www.tradingview.com/support/solutions/43000634738-supertrend/) | Implementation this script is adapted from |
| *Secrets for Profiting in Bull and Bear Markets* | Weinstein, S. (1988). *Secrets for Profiting in Bull and Bear Markets*. Dow Jones-Irwin. | Primary published description of the four-stage method |
| TrendSpider Weinstein Stage Analysis | [TrendSpider shared chart](https://charts.trendspider.com/shared/679813ca6550e0000970233f) | Stage-analysis implementation this script is adapted from |

See [Installation](../../README.md#installation) and [License](../../README.md#license) in the repository readme. The legal disclaimer is in [DISCLAIMER.md](../../DISCLAIMER.md).
