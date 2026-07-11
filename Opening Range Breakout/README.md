# Opening Range Breakout (ORB) Indicator

Opening Range Breakout Indicator is a TradingView Pine Script indicator that identifies and tracks opening range breakouts. The motivation for this script stems from the limitation of many broker's charting software. They only limit to preset indicators and drawings, which are not frequently updated or lack customisation options that aid users' experience. I found that a custom TradingView script can resolve this gap in my workflow.

## 📚 Table of Contents

- [📋 Overview](#-overview)
- [🎯 Recommended Trading Actions](#-recommended-trading-actions)
- [✨ Features](#-features)
- [🚀 Installation](#-installation)
- [⚙️ Configuration](#️-configuration)
- [🔔 Setting Up Alerts](#-setting-up-alerts)
- [🛠️ Troubleshooting](#️-troubleshooting)
- [📊 Understanding the Statistics](#-understanding-the-statistics)
- [⚠️ Important Notes](#️-important-notes)
- [⚠️ Disclaimer](#️-disclaimer)
- [🤝 Contributing](#-contributing)
- [📄 License](#-license)

## 📋 Overview
![opening-range-breakout-spy-sample](/media/opening-range-breakout-spy-sample.png)
The Opening Range Breakout indicator captures the high and low of the first N minutes after market open and draws horizontal lines to view potential breakouts. Opening ranges, breakout outcomes, and points are calculated from confirmed **1-minute intrabars**, even when the chart uses a higher timeframe. With **No Bias** mode, one arrow fires per direction on the first close beyond ORH/ORL. With **Daily Bias** mode, signals may be delayed until an extended target is reached.

## 🎯 Recommended Trading Actions

> **⚠️ IMPORTANT DISCLAIMER**: The following are educational examples only. Always implement proper risk management with stop losses and take profits. See [DISCLAIMER.md](../DISCLAIMER.md) for full legal disclaimers. The author is not liable for any trading decisions or outcomes.

### 📈 Breakout Scenarios

#### 🔴 Opening Range High Breakout
- **Logic**: Breakout above the opening range high suggests that price might move further upwards.

#### 🔵 Opening Range Low Breakout
- **Logic**: Breakout below the opening range low suggests that price might move further downwards.

#### 🟡 Width Error Days
- **Logic**: Width less then 0.2% of the opening suggests that the traded range might not be valid and chances of reversal will be higher. 

#### ✅ Essential Requirements
- **Position Sizing**: Never risk more than 1-2% of account per trade
- **Take Profits**: Set realistic targets based on historical range data
- **Volatility Awareness**: Adjust strategies based on width error frequency

#### ⛔ Trading Warnings
- **Not Financial Advice**: These are educational examples only
- **Individual Responsibility**: All trading decisions are your own
- **Risk Disclosure**: Trading involves substantial risk of loss
- **Professional Advice**: Consult licensed advisors for personalised guidance

## ✨ Features

### Core Functionality
- **Customisable Duration**: Set opening range from 1 to 480 minutes
- **Deterministic Sessions**: Market hours and custom ranges use an explicit IANA timezone
- **One-Minute Scoring**: Higher chart timeframes retain one-minute OR and breakout calculations
- **Real-time Tracking**: Monitors breakouts as they happen
- **Enhanced Breakout Logic**: Handles multiple breakouts with first-signal priority
- **Statistical Analysis**: Tracks success rates and patterns over time

### Visual Elements & Customisation
- **Dynamic Range Fill**: Colour-coded area between opening range lines based on session status
- **Customisable Session Colours**: Full control over width error, profit, loss, and error day colours
- **Flexible Table Display**: Show/hide statistics table for cleaner charts
- **Range Lines**: Customisable colours and transparency for high/low lines

### Advanced Analytics & Statistics
- **Performance Categorisation**: Width error, profit, loss, and error day tracking
- **Enhanced Statistics Table**: Colour-coordinated metrics with custom colours
- **Percentage Breakdowns**: Detailed success rate analysis with visual feedback
- **First Breakout Priority**: Accurate profit/loss calculation when both levels are hit
- **Mobile-Friendly**: Optional table hiding for mobile chart viewing

## 🚀 Installation

1. Open TradingView and navigate to the Pine Editor
2. Copy the contents of `opening-range-breakout-indicator-script`
3. Paste into the Pine Editor
4. Click "Add to Chart"
5. Configure your desired settings in the indicator inputs

## ⚙️ Configuration

### Input Parameters

#### Opening Range Period
| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Opening Range Period | Timeframe | 60 | Duration for calculating the opening range (e.g. 60 = first hour) |
| Use Custom Range | Boolean | false | Override the market-open-derived range with a custom time session |
| Custom Session | Session | 0930-1030 | Custom opening range window (HHMM-HHMM) when enabled |
| Timezone | String | America/New_York | IANA timezone for OR, market hours, cutoff, and DST |
| Market Hours | Session | 0930-1600 | Restricts breakout tracking and supplies the final scoring close |
| Opening Range Width Threshold % | Float | 0.2 | Minimum OR width as % of session open; below = untradable |
| VIX Untradable Threshold | Float | 20.0 | Daily VIX open above this marks the day untradable |

**Session behavior:** By default, the opening range begins at the configured Market Hours start and lasts for the Opening Range Period. Enable **Use Custom Range** to define an explicit session window. Chart regular/extended-session selection does not change scoring over the same available one-minute period.

The opening range and breakout cutoff must be contained within Market Hours. Invalid combinations stop with a runtime error rather than producing partial-session statistics.

#### Historical Display
| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Show Historical Data | Boolean | true | Display data from previous sessions |

#### Breakout Signals & Style
| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Show Breakout Signals | Boolean | true | Display triangular signals on breakout |
| Signal Bias | String | No Bias | No Bias: first close beyond ORH/ORL. Daily Bias: delayed signals at extended targets |
| Signal Size / Colours | Various | — | Customise signal appearance |
| OR Levels / Target Colours | Colour | Various | Customise range lines, targets, and fill |

#### Scoring & Cutoff
| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Breakout Cutoff Hour / Minute | Int | 12:00 | After this time, new breakouts are ignored if none occurred |
| Profit Points | Int | 100 | Points for a profitable breakout day |
| Loss Points Per $1 | Int | 100 | Points deducted for each started $1 beyond the opposite OR boundary |
| Maximum Loss Points | Int | 1500 | Maximum deduction for one session |

#### Session Status Colours
| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Untradable Day Colour | Colour | Yellow | Width-error or VIX-untradable days |
| Profit Colour | Colour | Green | Profitable breakout days |
| Loss Colour | Colour | Red | Failed breakout days |
| Error Colour | Colour | Blue | No breakout during the session |

#### Table
| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Show Statistics Table | Boolean | true | Display/hide the statistics table |
| Show Backtest | Boolean | true | Sessions, Profit, Loss, Error, Untradable, Points columns |
| Table Location / Text Size | String | Top Right / Small | Table placement and sizing |

### Recommended Settings

**For Stock Market (US):**
- Opening Range Period: 60 minutes
- Timezone: America/New_York
- Market Hours: 0930-1600

**For Forex (24/7):**
- Opening Range Period: 60–120 minutes
- Enable Custom Range for your preferred session window
- Timezone: Use the matching IANA timezone

**For Futures:**
- Opening Range Period: 30–90 minutes
- Enable Custom Range to match contract hours
- Timezone: America/Chicago for Chicago-based futures

## 🔔 Setting Up Alerts

1. Right-click on the chart and select **Add Alert**
2. Under **Condition**, choose this indicator
3. Select one of the available alert conditions:
   - **ORB High Breakout** — first confirmed 1-minute close above ORH on a tradable day
   - **ORB Low Breakout** — first confirmed 1-minute close below ORL on a tradable day
   - **Any ORB Breakout** — either high or low breakout
4. On charts above 1 minute, set **Frequency** to **Once Per Bar** to receive the first available one-minute event without waiting for the chart bar to close
5. Configure notification preferences and expiration

Alerts include dynamic placeholders (`{{ticker}}`, `{{close}}`, `{{interval}}`) in the default message. Alerts do not fire on untradable days or after the breakout cutoff when no breakout has occurred.

## 🛠️ Troubleshooting

### Common Issues

**Lines Not Appearing:**
- Verify the chart timeframe is intraday (less than 1 day)
- Confirm the opening range period has completed for the current session
- Check that sufficient session bars exist on the chart

**No Statistics:**
- Ensure sufficient historical data is available
- Enable **Show Statistics Table** and **Show Backtest** in Table Columns
- Check the **1m From** table value; the oldest partial one-minute session is deliberately excluded

**Alerts Not Working:**
- Select an alert condition from the indicator (ORB High/Low/Any Breakout)
- Use **Once Per Bar** when the chart timeframe is above 1 minute
- Confirm the day is tradable (width and VIX thresholds met)
- Re-create alerts if you updated the indicator (alert titles may have changed)

**Table Not Displaying:**
- Ensure "Show Statistics Table" is enabled
- Check table location settings
- Verify at least one column is enabled in Table Columns settings

## 📊 Understanding the Statistics

The indicator tracks session outcomes with colour-coded visual feedback:

### Session Categories

1. **Untradable Days** (yellow): Opening range width below threshold, daily VIX open above threshold, or required VIX open unavailable — excluded from profit/loss/error percentages
2. **Profit Days** (green): Breakout occurred with favourable close relative to the range
3. **Loss Days** (red): Breakout occurred but the market-hours close crossed the opposite OR boundary
4. **Error Days** (blue): No breakout before session end (or cutoff with no breakout)

### Breakout Detection

Breakouts are detected when price **closes beyond ORH or ORL on a confirmed 1-minute bar** during Market Hours. Gap opens above/below the range count on the first qualifying one-minute close. Signal Bias affects arrows only; it does not change scoring.

### Points

- Profit: `+100` by default.
- High-first loss distance: `ORL - market close`.
- Low-first loss distance: `market close - ORH`.
- Each started `$1` of adverse distance deducts 100 points: `$0.01–$1.00 = -100`, `$1.01–$2.00 = -200`.
- Losses are capped at `-1500` for `$15` or more.
- A high-first session remains a profit when the final close is at or above ORL. A low-first session remains a profit when the final close is at or below ORH.

### Table Columns (Backtest)

| Column | Description |
|--------|-------------|
| Sessions | Total sessions processed |
| Profit / Loss / Error | Count and **percentage of tradable days** (excludes untradable) |
| Untradable | Count of width-error and VIX-filtered days |
| Points | Finalized sessions plus a non-mutating active-session preview once an outcome is classifiable |
| 1m From | First complete session covered by available one-minute intrabars |

### Enhanced Analytics

- **First Breakout Priority**: When both high and low are hit, profit/loss uses whichever broke first
- **Dynamic Range Fill**: Area between OR lines coloured by session outcome
- **Points System**: Configurable profit points and capped per-dollar loss penalties

### One-Minute Coverage

`request.security_lower_tf()` supplies the one-minute bars used by the scoring engine. TradingView currently limits all non-professional plans, including Basic, to the most recent **100,000 intrabars** per request. A higher chart timeframe can load more chart candles, but it cannot extend exact one-minute scoring beyond this limit. The indicator:

- displays the first complete scored date in **1m From**;
- excludes the oldest partial session;
- never substitutes coarse chart OHLC for unavailable one-minute data.

The chart must contain bars spanning the configured Opening Range and Market Hours. Requesting an extended-session ticker cannot create host-chart periods that TradingView did not load.

## ⚠️ Important Notes

1. **Timeframe Compatibility**: Use an intraday chart timeframe from 1 minute to less than 1 day.
2. **Calculation Timeframe**: OR values, breakouts, and scoring always use available confirmed 1-minute intrabars.
3. **Opening Range Timing**: Default mode begins at the Market Hours start; Custom Range provides an explicit override.
4. **Timezone**: Use an IANA identifier such as `America/New_York` so historical and future DST changes are applied.
5. **Market Hours**: Breakouts outside this session are ignored, and its last confirmed one-minute close finalizes the outcome.
6. **VIX Availability**: Missing daily VIX open data, including an OR that starts before the VIX daily session, marks the session untradable instead of using a previous or future value.
7. **History Limit**: Non-professional TradingView plans currently provide at most 100,000 requested one-minute intrabars.
8. **Performance**: Large line/label counts with historical data enabled may impact chart performance.
9. **Daily Bias Signals**: Use chart-bar extended-target crossovers and may fire later than the initial breakout; scoring remains one-minute based.

## ⚠️ Disclaimer

This indicator is for educational and informational purposes only. It does not constitute financial advice. Trading involves risk, and past performance does not guarantee future results. Always conduct your own research and consider consulting with a financial advisor before making trading decisions.

## 🤝 Contributing

This indicator is part of an open-source project. Contributions, bug reports, and feature requests are welcome through the project repository.

## 📄 License

This project is licensed under the [Mozilla Public License 2.0](https://www.mozilla.org/MPL/2.0/). See the [LICENSE](../LICENSE) file for details.

---

*For support and updates, please refer to the project repository or TradingView script comments.*
