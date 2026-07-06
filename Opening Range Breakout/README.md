# Opening Range Breakout (ORB) Indicator

Opening Range Breakout Indicator is a TradingView Pine Script indicator that identifies and tracks opening range breakouts. The motivation for this script stems from the limitation of many broker's charting software. They only limit to preset indicators and drawings, which are not frequently updated or lack customisation options that aid users' experience. I found that a custom TradingView script can resolve this gap in my workflow.

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
2. Copy the contents of `opening-range-breakout-indicator-script`
3. Paste into the Pine Editor
4. Click "Add to Chart"
5. Configure your desired settings in the indicator inputs
