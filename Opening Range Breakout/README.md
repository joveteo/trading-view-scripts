# Opening Range Breakout (ORB) Indicator

Opening Range Breakout Indicator is a TradingView Pine Script indicator that identifies and tracks opening range breakouts. The motivation for this script stems from the limitation of many broker's charting software. They only limit to preset indicators and drawings, which are not frequently updated or lack customisation options that aid users' experience. I found that a custom TradingView script can resolve this gap in my workflow

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
The Opening Range Breakout indicator captures the high and low of the first N minutes after market open and draws horizontal lines to view potential breakouts. A triangle arrow is shown when a breakout is confirmed at bar close. With **No Bias** mode, one arrow fires per direction on the first close beyond ORH/ORL. With **Daily Bias** mode, signals may be delayed until an extended target is reached.

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
- **Automatic Session Detection**: Works with any market session and timezone
- **Real-time Tracking**: Monitors breakouts as they happen
- **Enhanced Breakout Logic**: Handles multiple breakouts with first-signal priority
- **Statistical Analysis**: Tracks success rates and patterns over time

### Visual Elements & Customisation
- **Dynamic Range Fill**: Colour-coded area between opening range lines based on session status
- **Customisable Session Colours**: Full control over width error, profit, loss, and error day colours
- **Session Trend Indicators**: SMA, EMA, RMA, WMA, and Anchor VWAP options
- **Flexible Table Display**: Show/hide statistics table for cleaner charts
- **Range Lines**: Customisable colours and transparency for high/low lines

### Advanced Analytics & Statistics
- **Performance Categorisation**: Width error, profit, loss, and error day tracking
- **Enhanced Statistics Table**: Colour-coordinated metrics with custom colours
- **Percentage Breakdowns**: Detailed success rate analysis with visual feedback
- **First Breakout Priority**: Accurate profit/loss calculation when both levels are hit
- **Mobile-Friendly**: Optional table hiding for mobile chart viewing

### Session Trend Analysis
- **Multiple Moving Averages**: SMA, EMA, RMA, WMA with customisable periods
- **Anchor VWAP**: Session-based VWAP anchored to daily opening price
- **Trend Direction Indicators**: Visual confirmation of session bias
- **Customisable Colours**: Match trend indicators to your colour scheme

## 🚀 Installation

1. Open TradingView and navigate to the Pine Editor
2. Copy the contents of `opening_range_breakout`
3. Paste into the Pine Editor
4. Click "Add to Chart"
5. Configure your desired settings in the indicator inputs

## ⚙️ Configuration

### Input Parameters

#### Opening Range Period
| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Opening Range Period | Timeframe | 60 | Duration for calculating the opening range (e.g. 60 = first hour) |
| Use Custom Range | Boolean | false | Override chart session with a custom time session |
| Custom Session | Session | 0930-1030 | Custom opening range window (HHMM-HHMM) when enabled |
| Timezone | String | UTC-5 | Timezone for custom session and cutoff |
| Market Hours | Session | 0930-1600 | Table ORH/ORL visibility and market-close countdown only |
| Opening Range Width Threshold % | Float | 0.2 | Minimum OR width as % of session open; below = untradable |
| VIX Untradable Threshold | Float | 20.0 | Daily VIX open above this marks the day untradable |

**Session behavior:** By default, the opening range follows the **chart session** plus the Opening Range Period timeframe. Enable **Use Custom Range** to define an explicit session window.

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
| Loss Tier 1/2/3 Points | Int | -500 / -1000 / -1500 | Points deducted by adverse move tier |
| Loss Distance Tier 1/2 | Float | 5 / 10 | Distance thresholds for loss tiers |

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

#### Session Trend Indicators
| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| SMA / EMA / RMA / WMA | Boolean | false | Session-reset adaptive moving averages |
| MA Lengths | Integer | 20 | Period for each enabled MA |
| Anchor VWAP | Boolean | true | Session VWAP using close × volume, anchored to session open |

### Recommended Settings

**For Stock Market (US):**
- Opening Range Period: 60 minutes
- Timezone: UTC-5 (Eastern)
- Enable Custom Range with 0930-1030 if chart session differs from RTH

**For Forex (24/7):**
- Opening Range Period: 60–120 minutes
- Enable Custom Range for your preferred session window
- Timezone: Match your broker's timezone

**For Futures:**
- Opening Range Period: 30–90 minutes
- Enable Custom Range to match contract hours
- Timezone: UTC-6 (Chicago) for most US futures

## 🔔 Setting Up Alerts

1. Right-click on the chart and select **Add Alert**
2. Under **Condition**, choose this indicator
3. Select one of the available alert conditions:
   - **ORB High Breakout** — first confirmed bar close above ORH on a tradable day
   - **ORB Low Breakout** — first confirmed bar close below ORL on a tradable day
   - **Any ORB Breakout** — either high or low breakout
4. Set **Frequency** to **Once Per Bar Close** for reliable end-of-bar signals
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
- Verify the indicator has processed multiple sessions

**Alerts Not Working:**
- Select an alert condition from the indicator (ORB High/Low/Any Breakout)
- Set frequency to **Once Per Bar Close**
- Confirm the day is tradable (width and VIX thresholds met)
- Re-create alerts if you updated the indicator (alert titles may have changed)

**Table Not Displaying:**
- Ensure "Show Statistics Table" is enabled
- Check table location settings
- Verify at least one column is enabled in Table Columns settings

## 📊 Understanding the Statistics

The indicator tracks session outcomes with colour-coded visual feedback:

### Session Categories

1. **Untradable Days** (yellow): Opening range width below threshold, or daily VIX open above threshold — excluded from profit/loss/error percentages
2. **Profit Days** (green): Breakout occurred with favourable close relative to the range
3. **Loss Days** (red): Breakout occurred but close reversed unfavourably
4. **Error Days** (blue): No breakout before session end (or cutoff with no breakout)

### Breakout Detection

Breakouts are detected when price **closes beyond ORH or ORL** on a confirmed bar. Gap opens above/below the range count as breakouts on the first qualifying bar close. Signals (No Bias) and alerts use the same rule. Daily Bias mode delays signal arrows until an extended target crossover.

### Table Columns (Backtest)

| Column | Description |
|--------|-------------|
| Sessions | Total sessions processed |
| Profit / Loss / Error | Count and **percentage of tradable days** (excludes untradable) |
| Untradable | Count of width-error and VIX-filtered days |
| Points | Running score from configurable profit/loss tiers |

### Enhanced Analytics

- **First Breakout Priority**: When both high and low are hit, profit/loss uses whichever broke first
- **Dynamic Range Fill**: Area between OR lines coloured by session outcome
- **Points System**: Configurable profit points and tiered loss penalties by adverse move distance



## ⚠️ Important Notes

1. **Timeframe Compatibility**: Use an intraday chart timeframe (less than 1 day)
2. **Opening Range Timing**: Default mode uses the **chart session** + Opening Range Period; enable Custom Range for explicit control
3. **Market Hours Input**: Controls table ORH/ORL display and countdown only — not opening range timing
4. **Data Quality**: Statistics improve with more historical data
5. **Performance**: Large line/label counts with historical data enabled may impact chart performance
6. **Bar Close**: Breakouts, signals (No Bias), and alerts fire on **confirmed bar close** — wait for the bar to close before acting
7. **Daily Bias Signals**: Use extended-target crossovers and may fire later than the initial breakout

## ⚠️ Disclaimer

This indicator is for educational and informational purposes only. It does not constitute financial advice. Trading involves risk, and past performance does not guarantee future results. Always conduct your own research and consider consulting with a financial advisor before making trading decisions.

## 🤝 Contributing

This indicator is part of an open-source project. Contributions, bug reports, and feature requests are welcome through the project repository.

## 📄 License

This project is licensed under the [Mozilla Public License 2.0](https://www.mozilla.org/MPL/2.0/). See the [LICENSE](../LICENSE) file for details.

---

*For support and updates, please refer to the project repository or TradingView script comments.*
