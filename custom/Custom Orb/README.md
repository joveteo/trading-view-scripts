# Custom Orb

Custom opening range breakout. A typical ORB drawing marks the high and low of the first N minutes and leaves the rest to the trader. This script adds session rules, one-minute scoring, filters, and a points table for a specific workflow.

## What was customised

- Opening range, breakouts, and points are scored from confirmed one-minute bars, even on a higher chart timeframe.
- Market hours, custom range, cutoff, and daylight saving use an explicit IANA timezone.
- Days can be marked untradable when the range is too narrow or when the daily VIX open is above a threshold (or missing).
- Session outcome uses a points system, first-breakout priority, and a statistics table.
- Signal arrows can follow No Bias or Daily Bias; bias does not change scoring.

![Opening Range Breakout on SPY](/media/opening-range-breakout-spy-sample.png)

By default the range starts at Market Hours and lasts for the Opening Range Period (60 minutes). Custom Range replaces that with an explicit session window. The range and the breakout cutoff must sit inside Market Hours.

**No Bias** fires one arrow per direction on the first one-minute close beyond ORH or ORL. **Daily Bias** may wait until an extended target is reached.

## Scoring

Breakouts are one-minute closes beyond ORH or ORL during Market Hours. If both sides are hit, the first breakout decides the day. The last confirmed one-minute close in Market Hours finalises the outcome.

| Outcome | Meaning |
|---------|---------|
| Untradable | Width or VIX filter failed |
| Profit | Breakout, and the close did not cross the opposite OR boundary |
| Loss | Breakout, then the close crossed the opposite boundary |
| Error | No breakout before session end, or none before the cutoff |

Default points: +100 for a profit. Loss deducts 100 points for each started $1 beyond the opposite boundary, capped at −1500. A high-first day stays a profit if the close is at or above ORL; a low-first day stays a profit if the close is at or below ORH.

`request.security_lower_tf()` supplies the one-minute series. Non-professional TradingView plans currently cap that request at 100,000 intrabars. The table’s **1m From** date is the first complete scored session; the oldest partial session is dropped. Missing one-minute data is not replaced with coarser chart OHLC.

## Alerts

- ORB High Breakout
- ORB Low Breakout
- Any ORB Breakout

On charts above one minute, use Once Per Bar so the alert can fire on the first qualifying one-minute event. Alerts do not fire on untradable days, or after the cutoff when no breakout has occurred.

## Inputs

| Parameter | Default | Notes |
|-----------|---------|-------|
| Opening Range Period | 60 | First N minutes from market open |
| Use Custom Range / Custom Session | off / 0930–1030 | Explicit OR window when enabled |
| Timezone | America/New_York | IANA zone for OR, market hours, and cutoff |
| Market Hours | 0930–1600 | Scoring session and final close |
| Opening Range Width Threshold % | 0.2 | Below this, the day is untradable |
| VIX Untradable Threshold | 20 | Daily VIX open above this is untradable |
| Signal Bias | No Bias | No Bias vs Daily Bias arrows |
| Breakout Cutoff | 12:00 | Ignore new breakouts after this if none occurred |
| Profit / Loss / Max Loss Points | 100 / 100 / 1500 | Session point rules |
| Show Statistics Table / Show Backtest | true | Table and backtest columns |

US cash equities typically use 60 minutes, `America/New_York`, and 0930–1600. Forex and futures usually need Custom Range and the matching timezone.

See [Installation](../../README.md#installation) and [License](../../README.md#license) in the repository readme. The legal disclaimer is in [DISCLAIMER.md](../../DISCLAIMER.md).
