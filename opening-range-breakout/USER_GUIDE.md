# Opening Range Breakout (ORB) - User Guide

## Quick Start Guide

### 1. Installation Steps

1. **Open TradingView**
   - Go to [TradingView.com](https://tradingview.com)
   - Log into your account

2. **Access Pine Editor**
   - Click on "Pine Editor" at the bottom of the screen
   - If not visible, go to Chart → Pine Editor

3. **Install the Indicator**
   - Copy the entire code from `opening_range_breakout.pine`
   - Paste it into the Pine Editor
   - Click "Add to Chart"
   - The indicator should now appear on your chart

### 2. Initial Configuration

**Essential Settings to Check:**
- Set your chart to an intraday timeframe (5min, 15min, 1h)
- Verify the trading session matches your market
- Adjust the opening range duration to your preference

## Detailed Setup Instructions

### Chart Requirements
- **Timeframe**: Use intraday timeframes (1min to 4h work best)
- **Symbol**: Works with stocks, ETFs, futures, forex
- **Data**: Ensure you have historical intraday data available
- **Account**: TradingView Basic account minimum (Pro+ recommended for alerts)

### Input Configuration

#### Opening Range Duration
```
Default: 60 minutes
Range: 1-480 minutes
Recommendation: 
- Stocks: 30-60 minutes
- Forex: 60-120 minutes
- Futures: 30-90 minutes
```

#### Trading Session
```
Default: 0930-1600 (US Stock Market)
Format: HHMM-HHMM

Common Sessions:
- US Stocks: 0930-1600
- Forex (London): 0800-1700
- Futures (ES): 0930-1615
- Crypto: 0000-2359 (24/7)
```

#### Session Timezone
```
Default: America/New_York

Common Timezones:
- US Eastern: America/New_York
- US Central: America/Chicago
- London: Europe/London
- Tokyo: Asia/Tokyo
- Sydney: Australia/Sydney
```

### Visual Settings

#### Line Transparency
- **0%**: Completely opaque lines
- **50%**: Moderately transparent
- **88%**: Highly transparent (default)
- **100%**: Invisible lines

#### Show/Hide Options
- **Show Opening Range Lines**: Toggle range lines visibility
- **Show Statistics**: Toggle statistics table display

## Using the Indicator

### Understanding the Display

#### Range Lines
- **Green Line**: Opening range high (resistance level)
- **Red Line**: Opening range low (support level)
- **Line Extension**: Automatically extends through the trading session

#### Breakout Signals
- **Green Triangle Up**: Price broke above opening range high
- **Red Triangle Down**: Price broke below opening range low
- **Signal Timing**: Appears on the bar where breakout occurs

#### Statistics Table
Located on the right side of the chart showing:
- **Total Days**: Number of days analyzed
- **Stayed Within Range**: Days with no breakouts (percentage)
- **Crossed Both Ends**: Days with breakouts on both sides (percentage)
- **Other Outcomes**: Days with single-side breakouts

### Reading the Data

#### In the Data Window
The indicator provides these values:
- **ORB High**: Current opening range high value
- **ORB Low**: Current opening range low value
- **Breakout Status**: Whether high/low has been crossed

#### Understanding Statistics
- **High Success Rate** (staying within range): Indicates low volatility periods
- **High Both-Sides Rate**: Indicates high volatility, trending markets
- **Balanced Rates**: Normal market conditions

## Setting Up Alerts

### Step-by-Step Alert Setup

1. **Right-click on the indicator name** in the chart
2. **Select "Add Alert"** from the context menu
3. **Choose Alert Type:**
   - "ORB High Breakout" - Only high breakouts
   - "ORB Low Breakout" - Only low breakouts  
   - "Any ORB Breakout" - Both high and low breakouts

4. **Configure Alert Settings:**
   - **Frequency**: "Once per bar" (recommended)
   - **Expiration**: Set based on your needs
   - **Sound**: Choose notification sound
   - **Popup**: Enable for desktop notifications
   - **Email/Webhook**: Configure if desired

5. **Test Your Alert:**
   - Wait for a breakout to occur
   - Verify you receive the notification

### Alert Message Examples
- "Price broke above Opening Range High: 425.67"
- "Price broke below Opening Range Low: 423.12"
- "Opening Range Breakout Detected"

## Trading Strategies

### Basic ORB Strategy
1. **Wait for range establishment** (after opening range period)
2. **Monitor for breakouts** using alerts or visual signals
3. **Enter trades** in the direction of the breakout
4. **Use range boundaries** as stop-loss levels

### Options Premium Decay Strategy
1. **Identify the opening range** early in the session
2. **Wait for direction** to be established
3. **Sell vertical spreads** on the opposite side of the range
4. **Monitor for range violations** that might threaten the position

### Swing Trading Application
1. **Use longer opening ranges** (2-4 hours)
2. **Combine with higher timeframe analysis**
3. **Look for failed breakouts** as reversal signals
4. **Use statistics** to gauge market regime

## Troubleshooting

### Common Issues and Solutions

#### "No Lines Appearing"
**Cause**: Incorrect timeframe or session settings
**Solution**: 
- Switch to intraday timeframe (15min recommended)
- Check session times match your market
- Verify "Show Opening Range Lines" is enabled

#### "Statistics Not Updating"
**Cause**: Insufficient historical data or new installation
**Solution**:
- Wait for several trading sessions to pass
- Ensure chart has adequate historical data
- Check "Show Statistics" is enabled

#### "Alerts Not Working"
**Cause**: Incorrect alert setup or account limitations
**Solution**:
- Verify TradingView account supports alerts
- Check alert conditions are properly configured
- Ensure "Enable Breakout Alerts" is checked
- Test with "Any ORB Breakout" condition first

#### "Wrong Session Times"
**Cause**: Timezone mismatch or incorrect session format
**Solution**:
- Verify timezone matches your market
- Use HHMM-HHMM format (e.g., 0930-1600)
- Check TradingView's built-in session templates

#### "Lines Don't Extend Properly"
**Cause**: Chart zoom level or display settings
**Solution**:
- Zoom out to see full line extension
- Check line transparency settings
- Refresh the chart if needed

### Performance Optimization

#### For Slower Devices
- Reduce opening range duration
- Disable statistics if not needed
- Use higher chart timeframes (30min vs 5min)
- Limit number of historical bars loaded

#### For Better Accuracy
- Use 5-15 minute chart timeframes
- Ensure clean data feed
- Allow sufficient warm-up period (30+ days)
- Monitor during regular market hours only

## Best Practices

### Setup Recommendations
1. **Start with default settings** and adjust gradually
2. **Test on different timeframes** to find optimal setup
3. **Use consistent session times** across different symbols
4. **Monitor statistics** to validate effectiveness

### Usage Tips
1. **Combine with volume analysis** for better breakout confirmation
2. **Consider market context** (trending vs ranging)
3. **Use multiple timeframes** for broader perspective
4. **Document your results** to refine strategy

### Risk Management
1. **Set appropriate position sizes** based on range width
2. **Use stop-losses** at range boundaries
3. **Monitor for false breakouts** especially in low volume
4. **Adjust strategy** based on market volatility regimes

## Advanced Features

### Customizing for Different Markets

#### Forex Markets
- Use 24-hour session (0000-2359)
- Longer opening ranges (2-4 hours)
- Consider major session overlaps
- Adjust for weekend gaps

#### Futures Markets
- Match contract-specific hours
- Consider overnight sessions
- Account for rollover dates
- Monitor for gap openings

#### Cryptocurrency
- 24/7 operation possible
- Consider exchange-specific hours
- Higher volatility periods
- Weekend trading activity

### Integration with Other Indicators
- **Volume Profile**: Confirm breakout significance
- **Moving Averages**: Trend direction context
- **RSI/MACD**: Momentum confirmation
- **Support/Resistance**: Additional level confluence

---

## Support and Updates

For technical support or feature requests:
- Check the GitHub repository for updates
- Review TradingView script comments
- Consult the troubleshooting section above
- Contact the development team through official channels

*Remember: This tool is for educational purposes. Always conduct proper risk management and consider consulting with financial advisors for investment decisions.*