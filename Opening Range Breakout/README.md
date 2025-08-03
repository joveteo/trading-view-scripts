# Opening Range Breakout (ORB) Indicator

A comprehensive TradingView Pine Script indicator that identifies and tracks opening range breakouts with customizable duration, advanced statistics tracking, dynamic visual feedback, and comprehensive session trend analysis.

> **✅ LATEST UPDATE:** Enhanced with customizable session colors, table visibility controls, improved breakout logic, and Pine Script v6 compliance - fully functional and optimized!

## 📋 Overview

The Opening Range Breakout indicator captures the high and low of the first N minutes after market open and draws horizontal lines to track potential breakouts. This tool is particularly useful for options traders looking to capture premium decay by opening vertical spreads on the other side of the opening range.

## ✨ Features

### Core Functionality
- **Customizable Duration**: Set opening range from 1 to 480 minutes
- **Automatic Session Detection**: Works with any market session and timezone
- **Real-time Tracking**: Monitors breakouts as they happen
- **Enhanced Breakout Logic**: Handles multiple breakouts with first-signal priority
- **Statistical Analysis**: Tracks success rates and patterns over time

### Visual Elements & Customization
- **Dynamic Range Fill**: Color-coded area between opening range lines based on session status
- **Customizable Session Colors**: Full control over width error, profit, loss, and error day colors
- **Session Trend Indicators**: SMA, EMA, RMA, WMA, and Anchor VWAP options
- **Outcome Labels**: Clear day markers (W/P/L/E) with custom color coding
- **Flexible Table Display**: Show/hide statistics table for cleaner charts
- **Range Lines**: Customizable colors and transparency for high/low lines

### Advanced Analytics & Statistics
- **Performance Categorization**: Width error, profit, loss, and error day tracking
- **Enhanced Statistics Table**: Color-coordinated metrics with custom colors
- **Percentage Breakdowns**: Detailed success rate analysis with visual feedback
- **First Breakout Priority**: Accurate profit/loss calculation when both levels are hit
- **Mobile-Friendly**: Optional table hiding for mobile chart viewing

### Session Trend Analysis
- **Multiple Moving Averages**: SMA, EMA, RMA, WMA with customizable periods
- **Anchor VWAP**: Session-based VWAP anchored to daily opening price
- **Trend Direction Indicators**: Visual confirmation of session bias
- **Customizable Colors**: Match trend indicators to your color scheme

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

#### Session Status Colors
| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Width Error Color | Color | Yellow | Color for days with opening range < 0.2% of open price |
| Profit Color | Color | Green | Color for profitable breakout days |
| Loss Color | Color | Red | Color for loss breakout days |
| Error Color | Color | Blue | Color for days with no breakout |

#### Session Trend Indicators
| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Show SMA/EMA/RMA/WMA | Boolean | false | Enable various moving averages |
| MA Lengths | Integer | 20 | Period for moving average calculations |
| Show Anchor VWAP | Boolean | false | Display VWAP anchored to daily open |
| Indicator Colors | Color | Various | Customizable colors for trend indicators |

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

## 📊 Understanding the Statistics

The indicator tracks four key session outcomes with color-coded visual feedback:

### 📋 Session Categories

1. **🟡 Width Error Days**: Opening range width < 0.2% of opening price (insufficient volatility)
2. **🟢 Profit Days**: Breakout occurred with favorable price movement beyond the range
3. **🔴 Loss Days**: Breakout occurred but price reversed unfavorably
4. **🔵 Error Days**: No breakout occurred during the session

### 📈 Enhanced Analytics

- **First Breakout Priority**: When both high and low are hit, profit/loss calculated from first signal
- **Dynamic Range Fill**: Area between OR lines colored based on session outcome
- **Color-Coordinated Table**: Statistics table uses matching custom colors for easy identification
- **Performance Percentages**: Detailed breakdown with visual color feedback

### 💡 Strategic Insights

These statistics help traders understand:
- **Market Volatility Patterns**: Identify high/low volatility periods
- **Breakout Success Rates**: Optimize entry timing and position sizing
- **Range Efficiency**: Find optimal opening range duration for different instruments
- **Session Bias**: Recognize directional tendencies in specific market conditions

## 🔔 Setting Up Alerts

1. Right-click on the indicator in your chart
2. Select "Add Alert"
3. Choose from available alert conditions:
   - ORB High Breakout
   - ORB Low Breakout
   - Any ORB Breakout
4. Configure notification preferences
5. Set alert frequency as needed

## 🎯 Recommended Trading Actions

> **⚠️ IMPORTANT DISCLAIMER**: The following are educational examples only. Always implement proper risk management with stop losses and take profits. See [DISCLAIMER.md](../DISCLAIMER.md) for full legal disclaimers. The author is not liable for any trading decisions or outcomes.

### 📈 Breakout Scenarios & Suggested Responses

#### 🔴 Opening Range High Breakout
**Potential Action**: Consider selling put spreads or put options
- **Logic**: Upward momentum suggests bullish continuation
- **Risk Management**: Set stop loss below opening range low
- **Take Profit**: Target 1-2x opening range width above breakout

#### 🔵 Opening Range Low Breakout  
**Potential Action**: Consider selling call spreads or call options
- **Logic**: Downward momentum suggests bearish continuation
- **Risk Management**: Set stop loss above opening range high
- **Take Profit**: Target 1-2x opening range width below breakout

#### 🟡 Width Error Days
**Potential Action**: Avoid trading or use range-bound strategies
- **Logic**: Insufficient volatility for meaningful breakouts
- **Alternative**: Consider iron condors or strangles

### 📊 Statistical-Based Decisions

- **High Profit Rate Markets**: More aggressive position sizing
- **High Error Rate Markets**: Focus on range-bound strategies
- **Consistent Breakout Direction**: Bias trades toward historical tendency

## 🛡️ Critical Risk Management

### ✅ Essential Requirements
- **Stop Losses**: Always use stops at opening range boundaries
- **Position Sizing**: Never risk more than 1-2% of account per trade
- **Take Profits**: Set realistic targets based on historical range data
- **Time Limits**: Close positions before market close or set time
- **Volatility Awareness**: Adjust strategies based on width error frequency

### ⛔ Trading Warnings
- **Not Financial Advice**: These are educational examples only
- **Individual Responsibility**: All trading decisions are your own
- **Risk Disclosure**: Trading involves substantial risk of loss
- **Professional Advice**: Consult licensed advisors for personalized guidance

## 📈 Usage Strategies by Trader Type

### For Options Traders
- **Vertical Spreads**: Use breakout signals for directional spread entries
- **Premium Collection**: Sell options on the opposite side of breakouts
- **Statistics Optimization**: Monitor success rates to refine opening range duration
- **Alert-Based Timing**: Set alerts to catch early breakout opportunities

### For Day Traders
- **Support/Resistance**: Use range boundaries as key levels
- **Momentum Trading**: Follow breakout direction with proper stops
- **Scalping Opportunities**: Trade bounces off opening range levels
- **Trend Confirmation**: Use session indicators to confirm directional bias

### For Swing Traders
- **Daily Bias**: Use opening range breakouts to establish daily market sentiment
- **Position Sizing**: Scale positions based on opening range width and volatility
- **Regime Recognition**: Monitor breakout frequency for market condition changes
- **Multi-Day Patterns**: Track consecutive breakout directions for longer-term bias

## 🔧 Technical Requirements

- **TradingView Pro/Pro+/Premium**: Required for alerts and advanced features
- **Intraday Timeframes**: Chart must show intraday data for accurate range calculation
- **Market Hours**: Indicator works best during regular trading hours
- **Historical Data**: Minimum 30 days recommended for meaningful statistics

## ⚠️ Important Notes

1. **Timeframe Compatibility**: Ensure your chart timeframe allows viewing of intraday price action
2. **Market Hours**: The indicator automatically detects market sessions but verify timezone settings
3. **Data Quality**: Statistics improve with more historical data
4. **Performance**: Large line counts may impact chart performance on lower-end devices

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

## 📋 Recent Enhancements

- **Enhanced Color System**: Full customization of session status colors with dynamic visual feedback
- **Table Visibility Control**: Show/hide statistics table for mobile-friendly viewing
- **Improved Breakout Logic**: First-signal priority for accurate profit/loss calculation when both levels are hit
- **Session Trend Analysis**: Multiple moving averages and Anchor VWAP for comprehensive market analysis
- **Pine Script v6 Compliance**: Fully updated and optimized for latest TradingView standards

## 🤝 Contributing

This indicator is part of an open-source project. Contributions, bug reports, and feature requests are welcome through the project repository.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## ⚠️ Disclaimer

This indicator is for educational and informational purposes only. It does not constitute financial advice. Trading involves risk, and past performance does not guarantee future results. Always conduct your own research and consider consulting with a financial advisor before making trading decisions.

---

*For support and updates, please refer to the project repository or TradingView script comments.*