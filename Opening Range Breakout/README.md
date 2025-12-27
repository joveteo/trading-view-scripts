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
The Opening Range Breakout indicator captures the high and low of the first N minutes after market open and draws horizontal lines to view potential breakouts. A triangle arrow will be shown when a breakout is identified at the candle close. Caveat is that multiple breakout may occure and therefore multiple arrow will be shown. 

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
2. Copy the contents of `opening_range_breakout.pine`
3. Paste into the Pine Editor
4. Click "Add to Chart"
5. Configure your desired settings in the indicator inputs

## ⚙️ Configuration

### Input Parameters

#### Core Settings
| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Opening Range Duration | Integer | 60 | Duration in minutes for the opening range (1-480) |
| Trading Session | Session | 0930-1600 | Market session times (HHMM-HHMM format) |
| Session Timezone | String | America/New_York | Timezone for the trading session |
| Show Historical Data | Boolean | true | Display data from previous sessions |

#### Visual Controls
| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Show Statistics Table | Boolean | true | Display/hide statistics table for mobile compatibility |
| Show Opening Range Lines | Boolean | true | Display range lines on chart |
| Line Transparency | Integer | 88 | Transparency percentage for range lines (0-100) |

#### Session Status Colours
| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Width Error Colour | Colour | Yellow | Colour for days with opening range < 0.2% of open price |
| Profit Colour | Colour | Green | Colour for profitable breakout days |
| Loss Colour | Colour | Red | Colour for loss breakout days |
| Error Colour | Colour | Blue | Colour for days with no breakout |

#### Session Trend Indicators
| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Show SMA/EMA/RMA/WMA | Boolean | false | Enable various moving averages |
| MA Lengths | Integer | 20 | Period for moving average calculations |
| Show Anchor VWAP | Boolean | false | Display VWAP anchored to daily open |
| Indicator Colours | Colour | Various | Customisable colours for trend indicators |

### Recommended Settings

**For Stock Market (US):**
- Duration: 30-60 minutes
- Session: 0930-1600
- Timezone: America/New_York

**For Forex (24/7):**
- Duration: 60-120 minutes
- Session: Custom based on your preferred market hours
- Timezone: Match your broker's timezone

**For Futures:**
- Duration: 30-90 minutes
- Session: Match specific contract hours
- Timezone: America/Chicago (for most US futures)

## 🔔 Setting Up Alerts

1. Right-click on the indicator in your chart
2. Select "Add Alert"
3. Choose from available alert conditions:
   - ORB High Breakout
   - ORB Low Breakout
   - Any ORB Breakout
4. Configure notification preferences
5. Set alert frequency as needed

## 🛠️ Troubleshooting

### Common Issues

**Lines Not Appearing:**
- Check that "Show Opening Range Lines" is enabled
- Verify timeframe allows intraday viewing
- Confirm trading session matches your market

**No Statistics:**
- Ensure sufficient historical data is available
- Check that "Show Statistics" is enabled
- Verify the indicator has been running for multiple days

**Alerts Not Working:**
- Confirm "Enable Breakout Alerts" is checked
- Verify TradingView alert settings
- Check that you have a TradingView Pro account

**Table Not Displaying:**
- Ensure "Show Statistics Table" is enabled
- Check table location settings
- Verify at least one column is enabled in Table Columns settings

## 📊 Understanding the Statistics

The indicator tracks four key session outcomes with colour-coded visual feedback:

### 📋 Session Categories

1. **🟡 Width Error Days**: Opening range width < 0.2% of opening price (insufficient volatility)
2. **🟢 Profit Days**: Breakout occurred with favourable price movement beyond the range
3. **🔴 Loss Days**: Breakout occurred but price reversed unfavourably
4. **🔵 Error Days**: No breakout occurred during the session

### 📈 Enhanced Analytics

- **First Breakout Priority**: When both high and low are hit, profit/loss calculated from first signal
- **Dynamic Range Fill**: Area between OR lines coloured based on session outcome
- **Colour-Coordinated Table**: Statistics table uses matching custom colours for easy identification
- **Performance Percentages**: Detailed breakdown with visual colour feedback



## ⚠️ Important Notes

1. **Timeframe Compatibility**: Ensure your chart timeframe allows viewing of intraday price action
2. **Market Hours**: The indicator automatically detects market sessions but verify timezone settings
3. **Data Quality**: Statistics improve with more historical data
4. **Performance**: Large line counts may impact chart performance on lower-end devices
5. **Reprinting**: This indicator reprints, actions should be taken after bar close

## ⚠️ Disclaimer

This indicator is for educational and informational purposes only. It does not constitute financial advice. Trading involves risk, and past performance does not guarantee future results. Always conduct your own research and consider consulting with a financial advisor before making trading decisions.

## 🤝 Contributing

This indicator is part of an open-source project. Contributions, bug reports, and feature requests are welcome through the project repository.

## 📄 License

This project is licensed under the [Mozilla Public License 2.0](https://www.mozilla.org/MPL/2.0/). See the [LICENSE](../LICENSE) file for details.

---

*For support and updates, please refer to the project repository or TradingView script comments.*
