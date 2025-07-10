# Opening Range Breakout (ORB) Indicator

A comprehensive TradingView Pine Script indicator that identifies and tracks opening range breakouts with customizable duration, statistics tracking, and alert functionality.

## 📋 Overview

The Opening Range Breakout indicator captures the high and low of the first N minutes after market open and draws horizontal lines to track potential breakouts. This tool is particularly useful for options traders looking to capture premium decay by opening vertical spreads on the other side of the opening range.

## ✨ Features

### Core Functionality
- **Customizable Duration**: Set opening range from 1 to 480 minutes
- **Automatic Session Detection**: Works with any market session and timezone
- **Real-time Tracking**: Monitors breakouts as they happen
- **Statistical Analysis**: Tracks success rates and patterns over time

### Visual Elements
- **Range Lines**: Green line for high, red line for low (88% transparent by default)
- **Breakout Signals**: Triangle markers when price crosses range boundaries
- **Statistics Display**: Real-time table showing performance metrics
- **Customizable Transparency**: Adjust line transparency from 0-100%

### Analytics & Statistics
- **Total Days Tracked**: Complete count of analyzed trading sessions
- **Success Rate**: Percentage of days price stayed within the range
- **Both Sides Crossed**: Days where price exceeded both high and low
- **Performance Percentages**: Detailed breakdown with percentages

### Alert System
- **Sound Alerts**: Optional audio notifications on breakouts
- **Multiple Alert Types**: Separate alerts for high/low breakouts
- **Customizable Messages**: Clear breakout notifications with price levels

## 🚀 Installation

1. Open TradingView and navigate to the Pine Editor
2. Copy the contents of `opening_range_breakout.pine`
3. Paste into the Pine Editor
4. Click "Add to Chart"
5. Configure your desired settings in the indicator inputs

## ⚙️ Configuration

### Input Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Opening Range Duration | Integer | 60 | Duration in minutes for the opening range (1-480) |
| Show Opening Range Lines | Boolean | true | Display range lines on chart |
| Show Statistics | Boolean | true | Display statistics table |
| Line Transparency | Integer | 88 | Transparency percentage for range lines (0-100) |
| Enable Breakout Alerts | Boolean | true | Enable sound alerts for breakouts |
| Trading Session | Session | 0930-1600 | Market session times (HHMM-HHMM format) |
| Session Timezone | String | America/New_York | Timezone for the trading session |

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

The indicator tracks three key metrics:

1. **Stayed Within Range**: Days where price never broke above the high or below the low
2. **Crossed Both Ends**: Days where price broke both the high and low during the session
3. **Other Outcomes**: Days with partial breakouts (only one side crossed)

These statistics help traders understand:
- Market volatility patterns
- Success rates for range-based strategies
- Optimal duration settings for different instruments

## 🔔 Setting Up Alerts

1. Right-click on the indicator in your chart
2. Select "Add Alert"
3. Choose from available alert conditions:
   - ORB High Breakout
   - ORB Low Breakout
   - Any ORB Breakout
4. Configure notification preferences
5. Set alert frequency as needed

## 📈 Usage Strategies

### For Options Traders
- Use breakout signals to time vertical spread entries
- Monitor statistics to optimize opening range duration
- Set alerts to catch breakouts early in the session

### For Day Traders
- Identify key support/resistance levels early in the session
- Use range boundaries for entry/exit signals
- Track breakout momentum for trend following

### For Swing Traders
- Identify daily volatility patterns
- Use opening range as baseline for position sizing
- Monitor breakout frequency for market regime changes

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

## 📋 Version History

- **v1.0**: Initial release with core ORB functionality
- **v1.1**: Added statistics tracking and performance metrics
- **v1.2**: Enhanced alert system with multiple breakout types
- **v1.3**: Improved session detection and timezone handling

## 🤝 Contributing

This indicator is part of an open-source project. Contributions, bug reports, and feature requests are welcome through the project repository.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## ⚠️ Disclaimer

This indicator is for educational and informational purposes only. It does not constitute financial advice. Trading involves risk, and past performance does not guarantee future results. Always conduct your own research and consider consulting with a financial advisor before making trading decisions.

---

*For support and updates, please refer to the project repository or TradingView script comments.*