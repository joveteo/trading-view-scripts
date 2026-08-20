# Weinstein Stage Analysis

[Published on TradingView](https://www.tradingview.com/script/FliTL63W-Weinstein-Stage-Analysis/). Maps Stan Weinstein’s four-stage cycle onto the chart by painting each candle’s body, border, and wick. Stages are calculated on a higher timeframe (weekly by default) from a 30-period moving average and a proximity band, then mapped onto the current chart.

This script is an interpretation of Weinstein’s method, adapted from the [TrendSpider Weinstein Stage Analysis](https://charts.trendspider.com/shared/679813ca6550e0000970233f) implementation. It will not match every discretionary rule from the original work.

## Stages

- Stage 1 (light green): basing after a decline, near a flattening or recovering average.
- Stage 2 (green): confirmed advance. The candle body holds above a rising average by more than the range band.
- Stage 3 (orange): distribution after Stage 2, until a Stage 4 breakdown.
- Stage 4 (red): confirmed decline. The candle body holds below a falling average by more than the range band.

TradingView’s `barcolor()` cannot change wicks or borders, so the script draws stage candles in front of the chart symbol. If the original green or red edges still show, hide the symbol’s Body, Wicks, and Border under Chart settings → Symbol → Style.

Use a chart timeframe at or below the stage timeframe. Bars that share a higher-timeframe period share that period’s completed stage. The current higher-timeframe bar can change until it closes.

## Inputs

| Parameter | Default | Notes |
|-----------|---------|-------|
| Stage Timeframe | W | Timeframe used for stage detection |
| MA Length | 30 | Lookback for the stage moving average |
| MA Type | SMA | SMA, EMA, WMA, RMA, VWMA, or HMA |
| Within Range % | 5 | Band around the MA used to confirm Stage 2 and Stage 4 |
| Stage 1–4 Colours | light green / green / orange / red | Candle colours for each stage |
| Colour Bars | true | Paint body, border, and wick by stage |
| Show MA | true | Plot the higher-timeframe moving average |
| Show Stage Labels | false | Label bars where the stage changes |

## Citations

| Source | Citation | Role |
|--------|----------|------|
| *Secrets for Profiting in Bull and Bear Markets* | Weinstein, S. (1988). *Secrets for Profiting in Bull and Bear Markets*. Dow Jones-Irwin. | Primary published description of the four-stage method |
| *The Professional Tape Reader* | *The Professional Tape Reader* newsletter (1972–2000). | Newsletter in which Weinstein developed and taught the method |
| TrendSpider Weinstein Stage Analysis | [TrendSpider shared chart](https://charts.trendspider.com/shared/679813ca6550e0000970233f) | Implementation this script is adapted from |

See [Installation](../README.md#installation) and [License](../README.md#license) in the repository readme. The legal disclaimer is in [DISCLAIMER.md](../DISCLAIMER.md).
